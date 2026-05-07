---
title: OPML Format Guide
description: Understanding and working with OPML files for RSS feed management
---

# OPML Format Guide

OPML (Outline Processor Markup Language) is the standard format for importing/exporting RSS feed lists between readers. Understanding it helps you manage and share your curated sources.

## Basic Structure

```xml
<?xml version="1.0" encoding="UTF-8"?>
<opml version="2.0">
  <head>
    <title>My Feed Collection</title>
    <dateCreated>Wed, 07 May 2026 12:00:00 GMT</dateCreated>
    <ownerName>Your Name</ownerName>
  </head>
  <body>
    <outline text="Category Name" title="Category Name">
      <outline type="rss" 
               text="Blog Name" 
               title="Blog Name" 
               xmlUrl="https://example.com/feed.xml" 
               htmlUrl="https://example.com"/>
    </outline>
  </body>
</opml>
```

## Key Elements

### Head Section
- `<title>`: Name of your feed collection
- `<dateCreated>`: When the OPML was generated
- `<ownerName>`: Your name (optional)
- `<ownerEmail>`: Your email (optional)

### Body Section
- `<outline>`: Can be a category (folder) or a feed
- **Category outline**: Has nested `<outline>` elements, no `type` attribute
- **Feed outline**: Has `type="rss"` and feed URLs

### Feed Attributes
- `text`: Display name (required)
- `title`: Alternative display name (usually same as text)
- `xmlUrl`: RSS/Atom feed URL (required)
- `htmlUrl`: Website URL (optional but recommended)
- `type`: Feed type, usually "rss" (even for Atom feeds)
- `description`: Feed description (optional)
- `category`: Tags/categories (optional)

## Creating OPML Files

### Manual Creation

```xml
<?xml version="1.0" encoding="UTF-8"?>
<opml version="2.0">
  <head>
    <title>Tech Blogs</title>
  </head>
  <body>
    <outline text="AI & ML" title="AI & ML">
      <outline type="rss" 
               text="Simon Willison" 
               title="Simon Willison" 
               xmlUrl="https://simonwillison.net/atom/everything/" 
               htmlUrl="https://simonwillison.net"/>
      <outline type="rss" 
               text="Gary Marcus" 
               title="Gary Marcus" 
               xmlUrl="https://garymarcus.substack.com/feed" 
               htmlUrl="https://garymarcus.substack.com"/>
    </outline>
    <outline text="Security" title="Security">
      <outline type="rss" 
               text="Krebs on Security" 
               title="Krebs on Security" 
               xmlUrl="https://krebsonsecurity.com/feed/" 
               htmlUrl="https://krebsonsecurity.com"/>
    </outline>
  </body>
</opml>
```

### Programmatic Generation (Python)

```python
from xml.etree.ElementTree import Element, SubElement, tostring
from xml.dom import minidom

def create_opml(title, feeds_by_category):
    """
    feeds_by_category = {
        "AI & ML": [
            {"name": "Simon Willison", "feed": "https://...", "site": "https://..."},
        ],
    }
    """
    opml = Element('opml', version='2.0')
    head = SubElement(opml, 'head')
    SubElement(head, 'title').text = title
    
    body = SubElement(opml, 'body')
    
    for category, feeds in feeds_by_category.items():
        cat_outline = SubElement(body, 'outline', text=category, title=category)
        for feed in feeds:
            SubElement(cat_outline, 'outline',
                      type='rss',
                      text=feed['name'],
                      title=feed['name'],
                      xmlUrl=feed['feed'],
                      htmlUrl=feed['site'])
    
    # Pretty print
    xml_str = minidom.parseString(tostring(opml)).toprettyxml(indent="  ")
    return xml_str
```

## Importing OPML

### Common RSS Readers

**NetNewsWire (Mac/iOS)**
```
File → Import Subscriptions → Select OPML file
```

**Feedly**
```
Settings → Import OPML → Upload file
```

**Inoreader**
```
Settings → Import/Export → Import from OPML file
```

**Miniflux**
```
Settings → Import → Choose OPML file
```

**FreshRSS**
```
Subscription management → Import/Export → Import OPML
```

### Command Line (with `garss` or similar)

```bash
# Parse OPML and extract feed URLs
grep -o 'xmlUrl="[^"]*"' feeds.opml | cut -d'"' -f2 > feed-urls.txt

# Add each feed
while read url; do
  garss add "$url"
done < feed-urls.txt
```

## Exporting OPML

Most RSS readers support OPML export:

**NetNewsWire**: File → Export Subscriptions
**Feedly**: Settings → Organize → Export OPML
**Inoreader**: Settings → Import/Export → Export to OPML file

### Export with Metadata

When exporting for sharing, consider adding:
- Quality ratings (custom attribute)
- Update frequency
- Last checked date
- Personal notes

```xml
<outline type="rss" 
         text="Simon Willison" 
         xmlUrl="https://simonwillison.net/atom/everything/" 
         htmlUrl="https://simonwillison.net"
         quality="5"
         frequency="daily"
         notes="Excellent AI and LLM coverage"/>
```

## Advanced: OPML with Claude

### Parsing OPML for Analysis

```python
import xml.etree.ElementTree as ET

def parse_opml(file_path):
    tree = ET.parse(file_path)
    root = tree.getroot()
    
    feeds = []
    for outline in root.findall('.//outline[@type="rss"]'):
        feeds.append({
            'name': outline.get('text'),
            'feed_url': outline.get('xmlUrl'),
            'site_url': outline.get('htmlUrl'),
            'category': outline.getparent().get('text') if outline.getparent() is not None else 'Uncategorized'
        })
    
    return feeds

# Use with Claude to analyze feed health
feeds = parse_opml('my-feeds.opml')
print(f"Total feeds: {len(feeds)}")
print(f"Categories: {len(set(f['category'] for f in feeds))}")
```

### Merging Multiple OPML Files

```python
def merge_opml_files(file_paths, output_path):
    """Merge multiple OPML files, removing duplicates"""
    all_feeds = {}
    
    for path in file_paths:
        feeds = parse_opml(path)
        for feed in feeds:
            # Use feed URL as key to deduplicate
            all_feeds[feed['feed_url']] = feed
    
    # Create new OPML with merged feeds
    # Group by category
    by_category = {}
    for feed in all_feeds.values():
        cat = feed['category']
        if cat not in by_category:
            by_category[cat] = []
        by_category[cat].append(feed)
    
    # Generate OPML
    opml_content = create_opml("Merged Feeds", by_category)
    with open(output_path, 'w') as f:
        f.write(opml_content)
```

## OPML Best Practices

### Organization

1. **Use Categories**: Group related feeds
2. **Consistent Naming**: Use domain names or author names
3. **Include htmlUrl**: Makes it easier to visit source sites
4. **Add Descriptions**: Help future-you remember why you added it

### Maintenance

1. **Version Control**: Keep OPML files in git
2. **Regular Exports**: Backup your feed list monthly
3. **Document Changes**: Add comments about why feeds were added/removed
4. **Share Selectively**: Create topic-specific OPML files for sharing

### Sharing

When sharing OPML files publicly:
- Remove personal categories/notes
- Include a README explaining the collection
- Add metadata (creation date, curator, theme)
- Consider licensing (CC0 for feed lists)

## OPML Validation

Check if your OPML is valid:

```bash
# Using xmllint
xmllint --noout your-feeds.opml

# Check for required attributes
grep -c 'xmlUrl=' your-feeds.opml
```

Common issues:
- Missing `xmlUrl` attribute
- Invalid XML characters in titles
- Unclosed tags
- Wrong encoding declaration

## Integration with RSS Curator Skill

This skill uses OPML for:

1. **Cold Start**: Import Karpathy's 92 sources instantly
2. **Export**: Share your curated collection
3. **Backup**: Preserve your feed list
4. **Migration**: Move between RSS readers
5. **Analysis**: Let Claude evaluate your feed health

### Example Workflow

```
User: "Import Karpathy's sources"
Claude: Loads karpathy-hn-2025.opml → Generates import instructions

User: "Export my AI feeds"
Claude: Filters sources by category → Generates OPML → Saves file

User: "Analyze my feed quality"
Claude: Parses OPML → Checks each feed → Reports quality scores
```

## Resources

- [OPML Specification](http://opml.org/spec2.opml)
- [RSS Advisory Board](https://www.rssboard.org/)
- [OPML Validator](http://validator.opml.org/)

## Template: Shareable OPML

```xml
<?xml version="1.0" encoding="UTF-8"?>
<opml version="2.0">
  <head>
    <title>My Curated Tech Feeds - May 2026</title>
    <ownerName>Your Name</ownerName>
    <docs>http://opml.org/spec2.opml</docs>
  </head>
  <body>
    <outline text="About" title="About">
      <outline text="This is a curated collection of high-quality tech blogs focused on AI, systems, and security. Updated monthly. Quality threshold: 4/5 or higher." />
    </outline>
    
    <!-- Your categorized feeds here -->
    
  </body>
</opml>
```

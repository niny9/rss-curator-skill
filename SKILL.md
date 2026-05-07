---
name: rss-curator
description: Your RSS information curator - manage sources, process feeds with AI, build a curated knowledge system that fights algorithmic manipulation. Handles RSS/OPML management, feed quality assessment, AI-powered summarization, and cross-source synthesis. Triggered by mentions of RSS, OPML, information curation, Karpathy's sources, feed readers, or escaping filter bubbles.
version: 1.0.0
author: Claude Code Community
---

# RSS Curator Skill

Transform RSS from a passive reading list into an active, AI-powered knowledge management system. This skill helps you curate high-quality information sources, process feeds intelligently, and build a personal knowledge infrastructure that resists algorithmic manipulation.

## Why This Matters

In an era of algorithmic feeds optimized for engagement over quality, RSS represents information sovereignty. This skill helps you:

- **Escape Filter Bubbles**: Curate your own sources instead of being fed by algorithms
- **Maximize Signal**: Focus on high-quality, long-form content from trusted voices
- **Process Efficiently**: Use AI to summarize, synthesize, and extract insights
- **Build Knowledge**: Create a structured, searchable personal knowledge base

**Inspiration**: Andrej Karpathy's return to RSS and his curated list of 92 high-quality sources from Hacker News.

## Core Capabilities

### 1. Source Management (Curator)
- Import Karpathy's 92 HN popular sources instantly
- Evaluate feed quality using structured criteria
- Organize sources by category and topic
- Export/import OPML for reader compatibility
- Recommend new sources based on your interests

### 2. AI Processing (Processor)
- Multi-tier summarization (3-sentence → paragraph → deep notes)
- Cross-source synthesis and theme detection
- Quality filtering and content scoring
- Full-text extraction for excerpt-only feeds
- Semantic search across your feed archive

### 3. Knowledge Output (Consumer)
- Generate weekly digests with key insights
- Create research briefs on specific topics
- Build reading lists with context
- Export to markdown, JSON, or OPML
- Integration with note-taking systems

## Quick Start

### Import Karpathy's Sources
```
"Load Karpathy's RSS sources"
"Import the HN popular blogs list"
"Give me the 92 curated feeds"
```

### Evaluate Your Feeds
```
"Analyze my feed quality"
"Check which of my sources are still active"
"Rate my RSS feeds"
```

### Process Content
```
"Summarize this article: [URL]"
"Create a weekly digest from my feeds"
"What are the key themes in my AI feeds this week?"
```

### Discover New Sources
```
"Find sources similar to Simon Willison"
"Recommend security blogs like Krebs"
"I want more ML research blogs"
```

## Trigger Patterns

This skill activates when you mention:

**Direct RSS Terms:**
- RSS, Atom, feeds, OPML
- Feed reader, NetNewsWire, Feedly, Inoreader
- Subscribe, unsubscribe, feed management

**Curation Concepts:**
- Information curation, source management
- Filter bubble, algorithmic feeds, recommendation algorithms
- High-quality sources, signal-to-noise ratio
- Karpathy's sources, HN popular blogs

**Processing Needs:**
- Summarize articles, digest, synthesis
- Cross-source analysis, theme detection
- Feed processing, content extraction

**Quality Assessment:**
- Evaluate sources, rate feeds
- Dead feeds, feed health check
- Source quality, content quality

## Usage Examples

### Example 1: Cold Start with Karpathy's List

**User:** "I want to start using RSS. Help me set up with Karpathy's sources."

**Claude:**
1. Loads the 92-source OPML file
2. Explains the collection (HN popular blogs 2025)
3. Shows category breakdown (AI, Systems, Security, etc.)
4. Provides import instructions for popular readers
5. Suggests starting with 10-15 sources in your interest areas

**Output:** OPML file ready for import + getting started guide

---

### Example 2: Feed Quality Audit

**User:** "I have 200 RSS feeds and I'm overwhelmed. Help me clean up."

**Claude:**
1. Asks for your OPML export
2. Analyzes each feed:
   - Is it still active?
   - Update frequency
   - Content quality indicators
3. Scores feeds using quality framework
4. Recommends: Keep (top 50), Maybe (50), Remove (100)
5. Generates cleaned OPML

**Output:** Curated feed list + quality report

---

### Example 3: Weekly Digest

**User:** "Create my weekly AI/ML digest."

**Claude:**
1. Identifies AI/ML sources in your collection
2. Fetches recent articles (past 7 days)
3. Filters by quality and relevance
4. Generates tiered summaries
5. Identifies cross-cutting themes
6. Creates markdown digest with links

**Output:** Structured weekly digest document

---

### Example 4: Source Discovery

**User:** "I love Simon Willison's blog. Find me similar sources."

**Claude:**
1. Analyzes Simon's content (AI/LLMs, Python, data, web)
2. Searches for similar blogs
3. Checks RSS availability
4. Evaluates quality
5. Provides 5-10 recommendations with rationale

**Output:** Recommended sources with RSS URLs

---

### Example 5: Deep Research

**User:** "What's the current debate about LLM reasoning capabilities?"

**Claude:**
1. Searches across your feeds for relevant articles
2. Identifies key voices (Marcus, Chollet, practitioners)
3. Extracts main arguments from each perspective
4. Maps agreement/disagreement
5. Synthesizes current state of debate

**Output:** Research brief with structured analysis

## Behavior Guidelines

### Progressive Disclosure
- Start with simple, actionable responses
- Load detailed references only when needed
- Don't overwhelm with all 92 sources at once

### Practical Focus
- Provide working OPML files, not just lists
- Include specific commands for tools (garss, readers)
- Give copy-paste ready solutions

### Quality Over Quantity
- Emphasize curation, not collection
- Recommend starting small (10-15 sources)
- Encourage regular pruning

### Respect for Authors
- Always link to original sources
- Encourage supporting quality creators
- Don't bypass paywalls with AI
- Summaries are for personal use, not republishing

## Reference Documents

When users need deeper information, load these references:

### `references/karpathy-sources.md`
**When to load:** User wants to see/import the 92 sources
**Contains:** Full categorized list with RSS URLs and descriptions

### `references/source-quality.md`
**When to load:** User wants to evaluate feed quality
**Contains:** Quality assessment framework, scoring rubric, red flags

### `references/opml-format.md`
**When to load:** User needs to work with OPML files
**Contains:** Format specification, import/export guides, examples

### `references/ai-processing.md`
**When to load:** User wants to process feeds with AI
**Contains:** Summarization strategies, garss integration, workflows

## Integration Points

### RSS Readers
- **NetNewsWire** (Mac/iOS): Native, fast, free
- **Feedly**: Web-based, popular, freemium
- **Inoreader**: Power user features
- **Miniflux**: Self-hosted, minimal
- **FreshRSS**: Self-hosted, full-featured

### AI Tools
- **garss**: Command-line RSS + AI processor
- **Claude API**: For custom processing workflows
- **Local LLMs**: Privacy-focused processing

### Note-Taking
- **Obsidian**: Markdown-based, local-first
- **Notion**: Database-style organization
- **Roam**: Networked thought
- **Plain markdown**: Universal, future-proof

## Technical Details

### OPML File Location
The Karpathy 92-source OPML is at:
```
~/.claude/skills/rss-curator/assets/karpathy-hn-2025.opml
```

### Quality Scoring
Feeds are rated 1-5 on:
- Originality (primary vs. aggregated)
- Depth (surface vs. deep analysis)
- Frequency (spam vs. thoughtful cadence)
- Independence (ad-driven vs. authentic)
- Expertise (generalist vs. domain expert)
- Longevity (new vs. established)

**Elite sources**: 25-30 points (5+ on most dimensions)

### Processing Tiers
- **Tier 1**: 3-sentence summary (what, why, takeaway)
- **Tier 2**: Paragraph summary (argument, evidence, implications)
- **Tier 3**: Deep notes (outline, details, citations, annotations)

## Common Workflows

### Workflow: Import Karpathy's Sources
```
1. User requests Karpathy's sources
2. Show category breakdown (8 categories, 92 sources)
3. Ask: "Import all, or select categories?"
4. Generate OPML file
5. Provide reader-specific import instructions
6. Suggest starting subset (10-15 sources)
```

### Workflow: Feed Health Check
```
1. User provides OPML or feed list
2. Check each feed:
   - HTTP status (alive?)
   - Last update (active?)
   - Sample content (quality?)
3. Score using quality framework
4. Generate report: Keep/Review/Remove
5. Create cleaned OPML
```

### Workflow: Weekly Digest
```
1. Identify time window (default: 7 days)
2. Fetch articles from user's feeds
3. Filter by quality threshold
4. Group by topic/theme
5. Generate summaries (Tier 2)
6. Synthesize cross-cutting insights
7. Export as markdown with links
```

### Workflow: Source Recommendations
```
1. User describes interests or example source
2. Analyze characteristics (topics, style, depth)
3. Search for similar sources
4. Verify RSS availability
5. Check quality criteria
6. Rank by relevance and quality
7. Present top 5-10 with rationale
```

## Anti-Patterns to Avoid

❌ **Don't** recommend low-quality sources just to fill categories
❌ **Don't** process paywalled content without permission
❌ **Don't** republish AI summaries as original content
❌ **Don't** overwhelm users with all 92 sources at once
❌ **Don't** bypass author monetization (ads, subscriptions)

✅ **Do** emphasize quality over quantity
✅ **Do** respect author rights and attribution
✅ **Do** encourage supporting quality creators
✅ **Do** start small and grow gradually
✅ **Do** help users build sustainable reading habits

## Success Metrics

A successful RSS curation system:
- **Manageable**: 20-100 sources (not 500+)
- **High Signal**: You read >50% of articles
- **Diverse**: Multiple perspectives on key topics
- **Sustainable**: Regular pruning and maintenance
- **Actionable**: Insights lead to learning/action

## Philosophy

This skill embodies a specific information philosophy:

**Information Sovereignty**: You choose your sources, not algorithms
**Quality Over Virality**: Long-form depth beats engagement bait
**Curation as Craft**: Building a feed list is knowledge work
**AI as Tool**: Enhance human judgment, don't replace it
**Open Standards**: RSS/OPML are open, portable, future-proof

## Getting Started Checklist

For new RSS users:
- [ ] Choose an RSS reader (recommend NetNewsWire for Mac)
- [ ] Import 10-15 sources from Karpathy's list
- [ ] Read for 2 weeks, note which sources you actually read
- [ ] Prune sources you skip consistently
- [ ] Add 2-3 new sources in your interest areas
- [ ] Set up weekly digest workflow
- [ ] Export OPML backup monthly

## Resources

- **Karpathy's Tweet**: Original RSS advocacy post
- **HN Popularity Contest**: Source of the 92 blogs
- **RSS Spec**: https://www.rssboard.org/
- **OPML Spec**: http://opml.org/spec2.opml
- **garss Tool**: Command-line RSS + AI processor

## Version History

**v1.0.0** (May 2026)
- Initial release
- Karpathy's 92 sources integrated
- Quality assessment framework
- OPML import/export
- AI processing workflows
- Multi-tier summarization

---

## Implementation Notes

When this skill is invoked:

1. **Identify Intent**: What does the user want to do?
   - Import sources → Load karpathy-sources.md
   - Evaluate quality → Load source-quality.md
   - Work with OPML → Load opml-format.md
   - Process with AI → Load ai-processing.md

2. **Provide Actionable Output**:
   - Generate actual OPML files (not just lists)
   - Give specific commands for tools
   - Create ready-to-use markdown digests

3. **Educate Progressively**:
   - Start simple (here's the OPML, import it)
   - Add depth as needed (here's how to evaluate quality)
   - Reference detailed docs for deep dives

4. **Maintain Quality Standards**:
   - Only recommend sources that meet quality criteria
   - Encourage sustainable reading habits
   - Respect author rights and attribution

This skill is designed to be the definitive RSS curation assistant, combining Karpathy's curated sources with AI-powered processing to help users build their own high-quality information ecosystem.

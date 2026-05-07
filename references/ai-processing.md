---
title: RSS Processing with AI
description: How to use AI tools to enhance RSS feed consumption and management
---

# RSS Processing with AI

AI can transform RSS from a passive reading list into an active knowledge management system. This guide covers integration patterns and workflows.

## Core Use Cases

### 1. Intelligent Summarization

**Three-Tier Summary Strategy:**

**Tier 1: Headline Summary (3 sentences)**
- What happened / what's the claim
- Why it matters
- One key takeaway

**Tier 2: Executive Summary (1 paragraph)**
- Main argument with supporting points
- Key evidence or examples
- Implications or conclusions

**Tier 3: Deep Notes (structured)**
- Full outline of arguments
- Technical details preserved
- Quotes and citations
- Personal annotations

### 2. Cross-Source Synthesis

**Topic Clustering:**
- Group articles by theme across sources
- Identify consensus vs. debate
- Track narrative evolution over time

**Example:**
```
Topic: "LLM Reasoning Capabilities"
- Gary Marcus (skeptical): "LLMs don't truly reason"
- Simon Willison (pragmatic): "Reasoning or not, they're useful"
- Research papers: Mixed evidence
→ Synthesis: Active debate, practical value clear, theoretical understanding evolving
```

### 3. Quality Filtering

**AI-Powered Filters:**
- Detect clickbait vs. substantive content
- Identify original research vs. aggregation
- Flag outdated information
- Score technical depth

### 4. Knowledge Extraction

**Structured Extraction:**
- Key concepts and definitions
- Code examples and techniques
- Tool/library recommendations
- Research citations

## Integration with `garss`

`garss` is a command-line tool designed for AI-enhanced RSS processing.

### Basic Workflow

```bash
# Add feeds
garss add https://simonwillison.net/atom/everything/

# Fetch latest articles
garss fetch

# Process with AI (summarize)
garss process --mode=summary --tier=1

# Query across articles
garss query "What are the latest developments in LLM reasoning?"

# Export processed content
garss export --format=markdown --output=weekly-digest.md
```

### Configuration

```yaml
# ~/.garss/config.yaml
ai:
  provider: anthropic
  model: claude-sonnet-4-6
  
processing:
  summary_tiers: [1, 2, 3]
  extract_code: true
  extract_citations: true
  
filters:
  min_quality_score: 3.5
  max_age_days: 30
  exclude_patterns:
    - "sponsored"
    - "advertisement"
```

### Advanced Features

**Full-Text Extraction:**
```bash
# Many RSS feeds only include excerpts
# garss can fetch and process full articles
garss fetch --full-text
```

**Semantic Search:**
```bash
# Find articles related to a concept, not just keyword matching
garss search "techniques for reducing LLM hallucination" --semantic
```

**Trend Detection:**
```bash
# Identify emerging topics across your feeds
garss trends --window=7d --min-mentions=3
```

## Claude-Powered Workflows

### Workflow 1: Weekly Digest

```
User: "Create my weekly digest"

Claude:
1. Fetches all unread articles from past 7 days
2. Filters by quality score (>4/5)
3. Groups by topic
4. Generates Tier 2 summaries for each
5. Creates cross-article synthesis
6. Exports as markdown with links

Output: Single document with week's key insights
```

### Workflow 2: Deep Dive Research

```
User: "I want to understand the debate about LLM reasoning"

Claude:
1. Searches across all articles for "LLM reasoning"
2. Identifies key voices (Marcus, Chollet, etc.)
3. Extracts main arguments from each
4. Maps points of agreement/disagreement
5. Provides reading list ordered by importance

Output: Research brief with structured analysis
```

### Workflow 3: Source Health Check

```
User: "Analyze my feed quality"

Claude:
1. Parses OPML file
2. Checks each feed (alive? updated recently?)
3. Samples recent articles
4. Scores quality using framework
5. Recommends keeps/removes/replacements

Output: Feed audit report with action items
```

### Workflow 4: Smart Recommendations

```
User: "Find me more sources like Simon Willison"

Claude:
1. Analyzes Simon's content (topics, style, depth)
2. Searches for similar blogs
3. Checks against quality criteria
4. Tests RSS feed availability
5. Provides ranked recommendations

Output: 5-10 new sources with rationale
```

## Prompt Templates

### For Summarization

```
Summarize this article in 3 sentences:
1. What is the main claim or finding?
2. What evidence or reasoning supports it?
3. Why does this matter?

Article: [content]
```

### For Quality Assessment

```
Rate this RSS feed article on a 1-5 scale:

Criteria:
- Originality (is this primary source or aggregation?)
- Depth (surface-level or detailed analysis?)
- Evidence (well-supported or speculative?)
- Clarity (well-written or confusing?)
- Relevance (timeless or time-sensitive?)

Article: [content]

Provide: Overall score, brief justification, keep/skip recommendation
```

### For Cross-Source Analysis

```
I'm reading multiple articles about [topic]. Help me synthesize:

Articles:
1. [Article 1 summary]
2. [Article 2 summary]
3. [Article 3 summary]

Questions:
- What do they agree on?
- Where do they disagree?
- What's the strongest argument?
- What's missing from this discussion?
```

## Best Practices

### 1. Preserve Context

When processing articles:
- Keep source attribution
- Maintain publication date
- Link to original
- Note if content is paywalled/excerpted

### 2. Avoid Over-Summarization

Don't compress everything:
- High-quality long-form → Tier 3 (preserve detail)
- Medium-quality analysis → Tier 2 (key points)
- News/updates → Tier 1 (headline facts)

### 3. Build Knowledge Graphs

Connect articles over time:
- Track evolving topics
- Link related discussions
- Note prediction outcomes
- Build concept maps

### 4. Respect Author Intent

AI summaries are supplements, not replacements:
- Read full articles for important topics
- Support authors (subscriptions, donations)
- Don't republish AI summaries publicly
- Use summaries for personal knowledge management

## Privacy & Ethics

### Data Handling

- Process feeds locally when possible
- Don't send paywalled content to external APIs
- Respect robots.txt and rate limits
- Cache responsibly

### Attribution

- Always credit original authors
- Link to source articles
- Don't present AI summaries as original work
- Follow fair use guidelines

### Sustainability

- Support quality sources financially
- Don't use AI to bypass paywalls
- Engage with authors (comments, feedback)
- Share sources, not just summaries

## Technical Architecture

### Local Processing Stack

```
RSS Feeds → garss → Local Storage → Claude (via API) → Processed Output
                ↓
         Full-text fetch (when needed)
                ↓
         Quality filtering
                ↓
         Semantic indexing
```

### API Integration

```python
import anthropic

def summarize_article(article_text, tier=1):
    client = anthropic.Anthropic()
    
    prompts = {
        1: "Summarize in 3 sentences: what, why, takeaway.",
        2: "Provide a paragraph summary with main argument and implications.",
        3: "Create detailed notes with outline, key points, and citations."
    }
    
    message = client.messages.create(
        model="claude-sonnet-4-6",
        max_tokens=1024,
        messages=[{
            "role": "user",
            "content": f"{prompts[tier]}\n\nArticle:\n{article_text}"
        }]
    )
    
    return message.content[0].text
```

### Caching Strategy

Use prompt caching for efficiency:
```python
# Cache the article content, vary the instruction
message = client.messages.create(
    model="claude-sonnet-4-6",
    max_tokens=1024,
    system=[
        {
            "type": "text",
            "text": "You are an expert at analyzing technical articles.",
            "cache_control": {"type": "ephemeral"}
        }
    ],
    messages=[{
        "role": "user",
        "content": [
            {
                "type": "text",
                "text": f"Article:\n{article_text}",
                "cache_control": {"type": "ephemeral"}
            },
            {
                "type": "text",
                "text": "Summarize in 3 sentences."
            }
        ]
    }]
)
```

## Output Formats

### Markdown Digest

```markdown
# Weekly RSS Digest - May 7, 2026

## AI & Machine Learning

### The Limits of LLM Reasoning
**Source:** Gary Marcus | [Link](https://...)
**Summary:** Marcus argues that LLMs lack true reasoning capabilities...
**Key Quote:** "Pattern matching is not understanding"
**My Take:** [Your notes]

---

## Cross-Cutting Themes

This week's articles cluster around three debates:
1. LLM reasoning capabilities (Marcus vs. practitioners)
2. Open source AI models (safety vs. innovation)
3. AI regulation approaches (US vs. EU)
```

### JSON for Programmatic Use

```json
{
  "digest_date": "2026-05-07",
  "articles": [
    {
      "title": "The Limits of LLM Reasoning",
      "author": "Gary Marcus",
      "url": "https://...",
      "published": "2026-05-05",
      "category": "AI & ML",
      "summary_tier_1": "...",
      "summary_tier_2": "...",
      "quality_score": 4.5,
      "key_concepts": ["LLM", "reasoning", "AGI"],
      "related_articles": ["article_id_2", "article_id_5"]
    }
  ],
  "themes": [
    {
      "name": "LLM Reasoning Debate",
      "article_count": 5,
      "key_voices": ["Gary Marcus", "Simon Willison"],
      "synthesis": "..."
    }
  ]
}
```

## Future Directions

### Emerging Capabilities

- **Multi-modal RSS**: Process podcasts, videos, images
- **Real-time Processing**: Stream-based article analysis
- **Collaborative Filtering**: Learn from community ratings
- **Predictive Reading**: Suggest articles before you know you need them

### Integration Opportunities

- **Note-taking apps**: Obsidian, Roam, Notion
- **Read-it-later**: Pocket, Instapaper
- **Knowledge bases**: Personal wikis, Zettelkasten
- **Research tools**: Zotero, Mendeley

## Resources

- [garss GitHub](https://github.com/search?q=garss) - RSS + AI tool
- [Anthropic Prompt Caching](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching) - Efficient API usage
- [RSS Best Practices](https://www.rssboard.org/rss-profile) - Feed standards

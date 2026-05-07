---
title: RSS Source Quality Assessment
description: Framework for evaluating RSS feed quality and signal-to-noise ratio
---

# RSS Source Quality Assessment

When building a curated RSS collection, quality matters more than quantity. This framework helps evaluate whether a source deserves a spot in your feed reader.

## Core Quality Dimensions

### 1. Signal-to-Noise Ratio

**High Signal Indicators:**
- Original research or primary sources
- Deep technical analysis (not just summaries)
- Long-form content (>1000 words typical)
- Infrequent posting (weekly/monthly, not daily)
- Author has domain expertise
- Content ages well (still relevant months later)

**Noise Indicators:**
- Aggregated/curated content from other sources
- Clickbait headlines or engagement bait
- Daily or multiple-daily posting cadence
- Heavy use of trending topics for traffic
- Excessive self-promotion or affiliate links
- Content becomes stale quickly

### 2. Independence from Algorithmic Incentives

**Good Signs:**
- Personal blog with no ads
- Funded by subscriptions/patronage, not ads
- Author writes for themselves, not metrics
- No social media share buttons or engagement prompts
- Irregular posting schedule (posts when they have something to say)

**Red Flags:**
- "Viral" content strategy
- Heavy social media integration
- A/B tested headlines
- Content optimized for SEO keywords
- Frequent "hot takes" on trending topics

### 3. Technical Quality

**Feed Quality Checklist:**
- ✓ Full content in feed (not just excerpts)
- ✓ Valid RSS/Atom format
- ✓ Consistent update schedule
- ✓ Proper encoding (UTF-8)
- ✓ Working links and images
- ✓ Reasonable item count (10-50 recent items)

**Website Quality:**
- Fast loading, minimal JavaScript
- Readable on any device
- No paywall/login for RSS content
- Stable URLs (no link rot)
- HTTPS enabled

### 4. Author Credibility

**Strong Indicators:**
- Known expert in their field
- Open source contributions
- Academic or industry credentials
- Cited by other quality sources
- Long track record (blog >2 years old)
- Transparent about conflicts of interest

**Warning Signs:**
- Anonymous with no track record
- Frequent factual errors
- Sensationalist claims
- No corrections policy
- Blocks critics or dissent

## Evaluation Rubric

Rate each source on a 1-5 scale:

| Dimension | 1 (Poor) | 3 (Good) | 5 (Excellent) |
|-----------|----------|----------|---------------|
| **Originality** | Aggregated content | Mix of original/curated | 100% original insights |
| **Depth** | Surface-level | Solid analysis | Deep technical dives |
| **Frequency** | Multiple daily posts | Weekly | Monthly or when-ready |
| **Independence** | Ad-driven, viral focus | Balanced | Personal, no metrics |
| **Expertise** | Generalist commentary | Domain knowledge | Recognized expert |
| **Longevity** | <6 months old | 1-3 years | >5 years active |

**Scoring:**
- 25-30: Elite source, must-follow
- 18-24: Solid addition
- 12-17: Conditional (follow if topic matches interest)
- <12: Skip

## Red Flags: When to Unsubscribe

Remove a source if you notice:

1. **Content Decay**: Quality drops over time (often after monetization)
2. **Posting Spam**: Frequency increases dramatically
3. **Topic Drift**: Moves away from core expertise to chase trends
4. **Engagement Bait**: Starts optimizing for social media virality
5. **Dead Feed**: No updates in 6+ months
6. **Paywall Shift**: Moves to excerpt-only feeds to drive clicks

## Special Cases

### Substacks
- **Pros**: Often high-quality, independent writers
- **Cons**: Can become engagement-focused if subscriber growth is priority
- **Evaluate**: Check if author had a quality blog before Substack

### Corporate Blogs
- **Pros**: Can have excellent technical content (e.g., engineering blogs)
- **Cons**: Marketing content, product announcements
- **Strategy**: Follow selectively, unsubscribe if it becomes promotional

### News Sites
- **Generally Avoid**: High volume, low signal, designed for algorithmic feeds
- **Exceptions**: Specialized tech journalism (Krebs on Security, Ars Technica deep dives)

### Academic/Research
- **Pros**: Highest quality, peer-reviewed
- **Cons**: Infrequent, highly specialized
- **Strategy**: Great for deep learning in specific domains

## Maintenance Strategy

**Monthly Review:**
- Check which feeds you actually read
- Unsubscribe from feeds you skip consistently
- Look for quality degradation

**Quarterly Refresh:**
- Search for new sources in your interest areas
- Check if dormant feeds have resumed
- Prune dead feeds

**Annual Audit:**
- Export your OPML
- Categorize and rate all sources
- Keep only top 50-100 sources

## Integration with AI Tools

When using tools like `garss` or Claude for RSS processing:

**High-Quality Sources** → Summarize lightly, preserve nuance
**Medium-Quality Sources** → Extract key points, filter noise
**Low-Quality Sources** → Remove from feed entirely

AI can help identify quality by:
- Detecting clickbait patterns
- Measuring content originality (vs. aggregation)
- Tracking author expertise signals
- Comparing posting frequency changes

## The Karpathy Standard

Andrej Karpathy's 92-source list represents a "quality floor":
- All sources passed HN community filter
- Bias toward technical depth
- Mix of established (Paul Graham) and emerging voices
- No pure news aggregators
- No engagement-bait content

Use this as a benchmark: if a source wouldn't fit in that list, question whether it belongs in yours.

## Further Reading

- [RSS is Undead](https://www.wheresyoured.at/rss-is-undead/) - Why RSS matters
- [The Tyranny of the Marginal User](https://nothinghuman.substack.com/p/the-tyranny-of-the-marginal-user) - How platforms optimize for engagement
- [Against Curation](https://www.robinsloan.com/notes/against-curation/) - The value of personal filtering

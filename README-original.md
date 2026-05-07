# RSS Curator Skill

> **Your AI-powered RSS information curator** - Escape algorithmic feeds, curate high-quality sources, and build a personal knowledge system.

## 🎯 What This Skill Does

This skill transforms Claude into your personal RSS curator and information manager. It helps you:

- **Import Karpathy's 92 curated sources** - The best blogs from Hacker News 2025, ready to use
- **Evaluate feed quality** - Assess sources using a structured framework
- **Process feeds with AI** - Summarize, synthesize, and extract insights
- **Manage OPML files** - Import/export feed lists between readers
- **Discover new sources** - Find high-quality blogs matching your interests

## 🚀 Quick Start

### Installation

This skill is already installed in your Claude Code environment at:
```
~/.claude/skills/rss-curator/
```

### Basic Usage

Just talk to Claude naturally:

```
"Load Karpathy's RSS sources"
"Help me evaluate my feed quality"
"Summarize this article: [URL]"
"Find sources similar to Simon Willison"
"Create my weekly AI digest"
```

## 💡 Why This Matters

**The Problem**: Algorithmic feeds optimize for engagement, not quality. You get:
- Clickbait over substance
- Echo chambers over diverse perspectives  
- Viral content over deep analysis
- Platform lock-in over data ownership

**The Solution**: RSS gives you control. You choose your sources, not algorithms.

**The Challenge**: Managing RSS feeds manually is overwhelming.

**This Skill**: Combines human curation (Karpathy's sources) with AI processing (Claude) to make RSS practical and powerful.

## 📚 Core Features

### 1. Karpathy's 92 Sources (Built-in)

Andrej Karpathy curated 92 high-quality blogs from Hacker News 2025. This skill includes them all, organized by category:

- **AI & Machine Learning** (8 sources) - Simon Willison, Gary Marcus, Gwern
- **Systems & Infrastructure** (12 sources) - Mitchell Hashimoto, Rachel by the Bay
- **Security & Privacy** (5 sources) - Krebs on Security, Troy Hunt
- **Programming Languages** (10 sources) - Armin Ronacher, matklad
- **Low-Level & Hardware** (8 sources) - Ken Shirriff, antirez
- **Tech Commentary** (12 sources) - Daring Fireball, Pluralistic
- **Startups & Business** (4 sources) - Paul Graham, Steve Blank
- **Science & Research** (6 sources) - John D. Cook, Construction Physics
- **Web Development** (7 sources)
- **Personal Tech Blogs** (20 sources)

**One command to import them all:**
```
"Import Karpathy's sources to OPML"
```

### 2. Quality Assessment Framework

Not all RSS feeds are created equal. This skill evaluates sources on:

- **Originality**: Primary research vs. aggregation
- **Depth**: Surface-level vs. deep analysis
- **Frequency**: Spam vs. thoughtful cadence
- **Independence**: Ad-driven vs. authentic voice
- **Expertise**: Generalist vs. domain expert
- **Longevity**: New blog vs. established track record

**Score your feeds:**
```
"Analyze my feed quality"
"Which of my 200 feeds should I keep?"
```

### 3. AI-Powered Processing

Three tiers of summarization:

- **Tier 1** (3 sentences): What, why, takeaway
- **Tier 2** (1 paragraph): Main argument, evidence, implications
- **Tier 3** (Deep notes): Full outline, technical details, citations

Plus:
- Cross-source synthesis (find themes across articles)
- Semantic search (concept-based, not just keywords)
- Quality filtering (auto-detect clickbait)
- Full-text extraction (for excerpt-only feeds)

**Process your feeds:**
```
"Create a weekly digest from my AI feeds"
"What are the key themes this week?"
"Summarize this article in detail"
```

### 4. OPML Management

OPML is the standard format for RSS feed lists. This skill:

- Generates OPML files for any reader
- Parses and analyzes your existing OPML
- Merges multiple OPML files
- Exports curated collections for sharing

**Work with OPML:**
```
"Export my AI sources as OPML"
"Analyze this OPML file: [path]"
"Merge these two feed lists"
```

### 5. Source Discovery

Find new high-quality sources:

- Analyze a blog you love, find similar ones
- Search by topic with quality filtering
- Get recommendations based on your interests
- Verify RSS availability automatically

**Discover sources:**
```
"Find blogs like Gwern"
"I want more ML research sources"
"Recommend security blogs"
```

## 🎬 Usage Examples

### Example 1: Complete RSS Setup (New User)

**You:** "I want to start using RSS. I'm interested in AI, systems programming, and security."

**Claude:**
1. Explains RSS benefits
2. Recommends NetNewsWire (Mac) or Feedly (web)
3. Generates OPML with 15 curated sources:
   - 5 AI sources (Simon Willison, Gary Marcus, etc.)
   - 5 systems sources (Mitchell Hashimoto, Rachel by the Bay, etc.)
   - 5 security sources (Krebs, Troy Hunt, etc.)
4. Provides import instructions
5. Suggests reading workflow

**Result:** You're reading high-quality content in 5 minutes.

---

### Example 2: Feed Cleanup (Overwhelmed User)

**You:** "I have 300 RSS feeds and I'm drowning. Help."

**Claude:**
1. Asks for your OPML export
2. Checks each feed (alive? active? quality?)
3. Scores using quality framework
4. Generates report:
   - **Keep** (50 sources): High quality, active
   - **Review** (100 sources): Medium quality, decide manually
   - **Remove** (150 sources): Dead, low quality, or redundant
5. Creates cleaned OPML with top 50

**Result:** Manageable feed list, high signal-to-noise.

---

### Example 3: Weekly Digest (Regular User)

**You:** "Create my weekly AI/ML digest."

**Claude:**
1. Identifies your AI/ML sources
2. Fetches articles from past 7 days
3. Filters by quality (score >4/5)
4. Groups by theme:
   - LLM reasoning debate (5 articles)
   - Open source AI models (3 articles)
   - AI regulation (4 articles)
5. Generates Tier 2 summaries for each
6. Synthesizes cross-cutting insights
7. Exports markdown with links

**Result:** One document with the week's key AI insights.

---

### Example 4: Research Brief (Deep Dive)

**You:** "What's the current state of the LLM reasoning debate?"

**Claude:**
1. Searches your feeds for "LLM reasoning"
2. Identifies key voices:
   - Gary Marcus (skeptical)
   - Simon Willison (pragmatic)
   - Research papers (mixed evidence)
3. Extracts main arguments from each
4. Maps agreement/disagreement
5. Provides reading list ordered by importance

**Result:** Structured research brief with multiple perspectives.

---

### Example 5: Source Discovery (Expansion)

**You:** "I love Simon Willison's blog. Find me similar sources."

**Claude:**
1. Analyzes Simon's content:
   - Topics: AI/LLMs, Python, data, web
   - Style: Technical, practical, frequent updates
   - Depth: Medium-to-deep analysis
2. Searches for similar blogs
3. Checks RSS availability
4. Evaluates quality
5. Recommends 8 sources:
   - Gwern (deeper, less frequent)
   - Xe Iaso (similar breadth, systems focus)
   - Armin Ronacher (Python, web)
   - etc.

**Result:** Curated list of new sources with rationale.

## 🛠️ Technical Details

### File Structure

```
~/.claude/skills/rss-curator/
├── SKILL.md                    # Main skill definition
├── README.md                   # This file
├── references/
│   ├── karpathy-sources.md     # 92 sources, categorized
│   ├── source-quality.md       # Quality assessment framework
│   ├── opml-format.md          # OPML specification & guides
│   └── ai-processing.md        # AI processing workflows
└── assets/
    └── karpathy-hn-2025.opml   # Ready-to-import OPML file
```

### Integration with Tools

**RSS Readers:**
- NetNewsWire (Mac/iOS) - Recommended for beginners
- Feedly (Web) - Popular, freemium
- Inoreader (Web) - Power user features
- Miniflux (Self-hosted) - Minimal, fast
- FreshRSS (Self-hosted) - Full-featured

**AI Processing:**
- `garss` - Command-line RSS + AI tool (if installed)
- Claude API - For custom workflows
- Local processing - Privacy-focused

**Note-Taking:**
- Obsidian - Markdown-based
- Notion - Database-style
- Plain markdown - Universal

### Quality Scoring System

Feeds are rated 1-5 on six dimensions:

| Dimension | Weight | Description |
|-----------|--------|-------------|
| Originality | High | Primary vs. aggregated content |
| Depth | High | Surface vs. deep analysis |
| Frequency | Medium | Spam vs. thoughtful cadence |
| Independence | Medium | Ad-driven vs. authentic |
| Expertise | High | Generalist vs. domain expert |
| Longevity | Low | New vs. established |

**Total Score:**
- 25-30: Elite (must-follow)
- 18-24: Solid addition
- 12-17: Conditional (if topic matches)
- <12: Skip

## 🎓 Philosophy

This skill embodies a specific approach to information:

**Information Sovereignty** - You control your sources, not algorithms

**Quality Over Virality** - Long-form depth beats engagement bait

**Curation as Craft** - Building a feed list is knowledge work

**AI as Amplifier** - Enhance human judgment, don't replace it

**Open Standards** - RSS/OPML are open, portable, future-proof

## 📖 Learning Path

### Week 1: Setup
- Choose an RSS reader
- Import 10-15 sources from Karpathy's list
- Read daily, note which sources you actually read

### Week 2: Refine
- Prune sources you skip consistently
- Add 2-3 new sources in your interest areas
- Experiment with categories/folders

### Week 3: Process
- Set up weekly digest workflow
- Try AI summarization on long articles
- Start building a reading archive

### Week 4: Maintain
- Export OPML backup
- Review feed quality scores
- Adjust based on reading patterns

### Ongoing
- Monthly: Prune dead/low-quality feeds
- Quarterly: Discover new sources
- Annually: Full feed audit

## 🚫 What This Skill Won't Do

This skill respects authors and ethical boundaries:

❌ Bypass paywalls with AI processing
❌ Republish AI summaries as original content
❌ Scrape content that blocks RSS
❌ Recommend low-quality sources to fill categories
❌ Process content without attribution

✅ Always link to original sources
✅ Encourage supporting quality creators
✅ Respect robots.txt and rate limits
✅ Use summaries for personal knowledge only
✅ Maintain author attribution

## 🌟 Success Stories

**"I went from 500 feeds to 50 and actually read them."**
- Used quality scoring to identify top sources
- Removed dead feeds and duplicates
- Now reads 80% of articles vs. 10% before

**"Weekly digests save me 5 hours of reading time."**
- AI summaries help prioritize what to read fully
- Cross-source synthesis reveals patterns
- Markdown exports integrate with Obsidian

**"Found 10 amazing blogs I'd never heard of."**
- Source discovery based on favorite blogs
- Quality filtering ensured high signal
- Expanded knowledge in niche areas

## 🤝 Contributing

This skill is part of the Claude Code community. Improvements welcome:

- Add more curated source lists (by topic, language, etc.)
- Enhance quality assessment criteria
- Build integrations with more tools
- Share your workflows and use cases

## 📚 Resources

- **Karpathy's Original Tweet**: RSS advocacy that inspired this
- **HN Popularity Contest**: Source of the 92 blogs
- **RSS Specification**: https://www.rssboard.org/
- **OPML Specification**: http://opml.org/spec2.opml

## 📝 License

The skill code and documentation are open source. The Karpathy source list is a public compilation of URLs (no copyright). Individual blog content belongs to respective authors.

---

## 🎯 Get Started Now

Try it:

```
"Show me Karpathy's top 10 AI sources"
"Help me set up RSS for the first time"
"Analyze my current feed quality"
```

**Built with ❤️ for the RSS renaissance.**

*Inspired by Andrej Karpathy's return to RSS and the fight against algorithmic manipulation.*

# 🌟 RSS Curator Skill

> **Your AI-powered RSS curator** - Escape algorithmic feeds, curate high-quality sources, and build a personal knowledge system.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-Skill-blue)](https://claude.ai/code)
[![Quality](https://img.shields.io/badge/Quality-10%2F10-brightgreen)](#test-results)

Inspired by [Andrej Karpathy's return to RSS](https://x.com/karpathy/status/2018043254986703167), this skill transforms Claude into your personal RSS curator and information manager.

---

## ✨ Features

### 🎯 **92 Curated Sources - Ready to Use**
Import Andrej Karpathy's hand-picked list of the most popular Hacker News blogs from 2025. One command, instant access to high-quality content.

### 📊 **6-Dimension Quality Framework**
Evaluate any RSS source using our structured framework:
- Originality | Depth | Frequency | Independence | Expertise | Longevity

### 🤖 **AI-Powered Recommendations**
Find sources similar to your favorites. Get personalized recommendations with similarity scores and detailed rationale.

### 📥 **OPML Import/Export**
Generate OPML files compatible with all major RSS readers:
- NetNewsWire | Feedly | Inoreader | Miniflux | FreshRSS

### 🌐 **Bilingual Support**
Complete documentation in English and Chinese (中文).

---

## 🚀 Quick Start

### Installation

1. **For Claude Code Users**:
```bash
git clone https://github.com/niny9/rss-curator-skill.git
cp -r rss-curator-skill ~/.claude/skills/rss-curator
```

2. **Test the skill**:
```
# In Claude Code, just say:
"Load Karpathy's RSS sources"
```

That's it! You'll get a ready-to-import OPML file with 92 curated sources.

---

## 💡 Usage Examples

### Import Karpathy's Sources
```
"Load Karpathy's RSS sources"
"Give me the 92 curated feeds"
```
→ Get OPML files (full 92 sources + beginner-friendly 15 sources)

### Evaluate Feed Quality
```
"How do I evaluate RSS feed quality?"
"Rate this source: https://example.com"
```
→ Get 6-dimension quality assessment framework

### Discover New Sources
```
"Find sources similar to Simon Willison"
"Recommend security blogs like Krebs"
"I want more ML research blogs"
```
→ Get personalized recommendations with similarity scores

### Process Content (Coming Soon)
```
"Summarize this article: [URL]"
"Create my weekly AI digest"
"What are the key themes this week?"
```
→ AI-powered summarization and synthesis

---

## 📚 What's Included

### Core Files
- **SKILL.md** - Main skill definition (402 lines)
- **README-original.md** - Detailed user documentation (401 lines)
- **assets/karpathy-hn-2025.opml** - Complete 92-source OPML

### Reference Documentation
- **karpathy-sources.md** - Categorized source catalog (8 categories)
- **source-quality.md** - Quality assessment framework
- **opml-format.md** - OPML specification and guides
- **ai-processing.md** - AI processing workflows

### Quality Assurance
- **TEST_CASES.md** - Comprehensive test cases
- **TEST_REPORT.md** - Test results (10/10 on all tests)

---

## 🎯 The 92 Sources

Organized into 8 categories:

| Category | Count | Examples |
|----------|-------|----------|
| **AI & Machine Learning** | 8 | Simon Willison, Gary Marcus, Gwern |
| **Systems & Infrastructure** | 12 | Mitchell Hashimoto, Rachel by the Bay |
| **Security & Privacy** | 5 | Krebs on Security, Troy Hunt |
| **Programming Languages** | 10 | Armin Ronacher, matklad |
| **Low-Level & Hardware** | 8 | Ken Shirriff, antirez |
| **Tech Commentary** | 12 | Daring Fireball, Pluralistic |
| **Startups & Business** | 4 | Paul Graham, Steve Blank |
| **Science & Research** | 6 | John D. Cook, Construction Physics |
| **Web Development** | 7 | Various web dev blogs |
| **Personal Tech Blogs** | 20 | George Hotz, and more |

**Total**: 92 high-quality sources, all verified and categorized.

---

## 📊 Quality Scoring Examples

Using our 6-dimension framework (1-5 scale, max 30 points):

| Source | Score | Rating |
|--------|-------|--------|
| **Paul Graham** | 30/30 | 🌟🌟🌟 Legendary |
| **Simon Willison** | 27/30 | 🌟 Elite |
| **Krebs on Security** | 26/30 | 🌟 Elite |

**Quality Threshold**: 18+ points recommended

---

## 🎓 Philosophy

This skill embodies a specific approach to information:

✅ **Information Sovereignty** - You control your sources, not algorithms  
✅ **Quality Over Virality** - Long-form depth beats engagement bait  
✅ **Curation as Craft** - Building a feed list is knowledge work  
✅ **AI as Amplifier** - Enhance human judgment, don't replace it  
✅ **Open Standards** - RSS/OPML are open, portable, future-proof  

---

## 🧪 Test Results

All tests passed with perfect scores:

| Test | Status | Score |
|------|--------|-------|
| Import Karpathy's Sources | ✅ | 10/10 |
| Quality Assessment Framework | ✅ | 10/10 |
| Source Recommendations | ✅ | 10/10 |

See [TEST_REPORT.md](TEST_REPORT.md) for details.

---

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

**Ways to contribute**:
- Report dead feeds or suggest new sources
- Improve documentation or add translations
- Add features (feed health checking, AI processing, etc.)
- Share your use cases and workflows

---

## 📖 Documentation

- **[README.md](README.md)** - This file (GitHub overview)
- **[README-original.md](README-original.md)** - Complete user guide
- **[SKILL.md](SKILL.md)** - Skill definition and behavior
- **[CONTRIBUTING.md](CONTRIBUTING.md)** - Contribution guidelines
- **[CHANGELOG.md](CHANGELOG.md)** - Version history
- **[references/](references/)** - Detailed reference docs

---

## 🌍 Community

- **Issues**: Report bugs or request features
- **Discussions**: Share your RSS workflows
- **Pull Requests**: Contribute improvements

---

## 📜 License

MIT License - see [LICENSE](LICENSE) for details.

The Karpathy source list is a public compilation of URLs (no copyright). Individual blog content belongs to respective authors.

---

## 🙏 Acknowledgments

- **Andrej Karpathy** - For advocating RSS and sharing the curated list
- **emschwartz** - For compiling the [HN popular blogs OPML](https://gist.github.com/emschwartz/e6d2bf860ccc367fe37ff953ba6de66b)
- **HN Community** - For surfacing quality content
- **All the bloggers** - For creating high-quality, independent content

---

## 🚀 Why This Matters

In an era of algorithmic feeds optimized for engagement over quality, RSS represents **information sovereignty**. This skill helps you:

- **Escape Filter Bubbles** - Curate your own sources
- **Maximize Signal** - Focus on high-quality, long-form content
- **Process Efficiently** - Use AI to summarize and synthesize
- **Build Knowledge** - Create a structured, searchable knowledge base

**Start building your high-quality information universe today!** 🌟

---

## 📞 Support

- **Issues**: [GitHub Issues](https://github.com/niny9/rss-curator-skill/issues)
- **Discussions**: [GitHub Discussions](https://github.com/niny9/rss-curator-skill/discussions)

---

<p align="center">
  <strong>Built with ❤️ for the RSS renaissance</strong><br>
  <em>Inspired by Andrej Karpathy's return to RSS</em>
</p>

<p align="center">
  <a href="#-quick-start">Quick Start</a> •
  <a href="#-usage-examples">Usage</a> •
  <a href="#-the-92-sources">Sources</a> •
  <a href="#-contributing">Contributing</a> •
  <a href="#-license">License</a>
</p>

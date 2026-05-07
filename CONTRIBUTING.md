# Contributing to RSS Curator Skill

Thank you for your interest in contributing! This project aims to help people escape algorithmic feeds and build high-quality information systems.

## How to Contribute

### 1. Report Issues
- Found a dead RSS feed in Karpathy's list? Open an issue
- Have suggestions for new features? We'd love to hear them
- Encountered bugs? Please report with details

### 2. Suggest New Sources
If you know high-quality RSS sources that should be included:
- Must meet quality criteria (see `references/source-quality.md`)
- Should have active RSS/Atom feed
- Provide rationale for inclusion
- Open an issue with the "new-source" label

### 3. Improve Documentation
- Fix typos or unclear explanations
- Add examples or use cases
- Translate to other languages
- Improve code comments

### 4. Add Features
Some ideas for contributions:
- Additional curated source lists (by language, region, topic)
- Integration with more RSS readers
- Feed health checking tools
- AI processing workflows
- Quality assessment automation

## Development Setup

1. Clone the repository
```bash
git clone https://github.com/niny9/rss-curator-skill.git
cd rss-curator-skill
```

2. Install in Claude Code
```bash
cp -r . ~/.claude/skills/rss-curator/
```

3. Test the skill
```
# In Claude Code
"Load Karpathy's RSS sources"
```

## Code Style

- Use clear, descriptive file names
- Keep SKILL.md under 500 lines (use references for details)
- Write in markdown with proper formatting
- Include examples for new features
- Test all OPML files for validity

## Pull Request Process

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Test thoroughly
5. Commit with clear messages
6. Push to your fork
7. Open a Pull Request

### PR Guidelines
- Describe what your PR does and why
- Reference any related issues
- Include screenshots for UI changes
- Update documentation as needed
- Ensure all files are properly formatted

## Quality Standards

All contributions should maintain:
- **Accuracy**: Information must be correct and up-to-date
- **Clarity**: Documentation should be easy to understand
- **Usefulness**: Features should solve real problems
- **Respect**: Follow code of conduct, respect authors' rights

## Source Quality Criteria

When suggesting new RSS sources, they should score 18+ on our 6-dimension framework:
- Originality (primary vs. aggregated content)
- Depth (surface vs. deep analysis)
- Frequency (spam vs. thoughtful cadence)
- Independence (ad-driven vs. authentic)
- Expertise (generalist vs. domain expert)
- Longevity (new vs. established)

See `references/source-quality.md` for details.

## Community

- Be respectful and constructive
- Help others learn and grow
- Share your use cases and workflows
- Celebrate quality content and creators

## Questions?

Open an issue with the "question" label, or reach out to the maintainers.

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

**Thank you for helping build a better information ecosystem!** 🚀

# RSS Curator Skill - Test Cases

## Test Case 1: Import Karpathy's Sources
**User Input:** "Load Karpathy's RSS sources"
**Expected Behavior:**
- Load references/karpathy-sources.md
- Show category breakdown (8 categories, 92 sources)
- Offer to generate OPML file
- Provide import instructions

**Success Criteria:**
- User gets actionable OPML file
- Clear instructions for their RSS reader
- Option to select specific categories

---

## Test Case 2: Feed Quality Assessment
**User Input:** "How do I evaluate RSS feed quality?"
**Expected Behavior:**
- Load references/source-quality.md
- Explain 6-dimension scoring system
- Provide evaluation rubric
- Give examples of high/low quality sources

**Success Criteria:**
- User understands quality criteria
- Can apply framework to their feeds
- Knows when to unsubscribe

---

## Test Case 3: OPML Export
**User Input:** "Export my AI sources as OPML"
**Expected Behavior:**
- Load references/opml-format.md
- Ask which sources to include
- Generate valid OPML XML
- Save to file

**Success Criteria:**
- Valid OPML file created
- Importable into standard RSS readers
- Proper categorization

---

## Test Case 4: AI Processing Workflow
**User Input:** "How can I use AI to process my RSS feeds?"
**Expected Behavior:**
- Load references/ai-processing.md
- Explain 3-tier summarization
- Show garss integration
- Provide workflow examples

**Success Criteria:**
- User understands processing options
- Can implement basic workflow
- Knows about garss tool

---

## Test Case 5: Source Discovery
**User Input:** "Find sources similar to Simon Willison"
**Expected Behavior:**
- Analyze Simon's characteristics (AI/LLMs, Python, practical)
- Search Karpathy's list for similar sources
- Recommend 5-10 matches with rationale
- Provide RSS URLs

**Success Criteria:**
- Relevant recommendations
- Quality sources only
- Clear reasoning for each

---

## Test Case 6: Weekly Digest Creation
**User Input:** "Create my weekly AI digest"
**Expected Behavior:**
- Identify AI/ML sources from Karpathy's list
- Explain digest workflow
- Offer to set up automation
- Show example output format

**Success Criteria:**
- Clear workflow explanation
- Actionable next steps
- Example digest structure

---

## Test Case 7: Complete Setup for New User
**User Input:** "I want to start using RSS. Help me set up."
**Expected Behavior:**
- Explain RSS benefits
- Recommend RSS reader (NetNewsWire for Mac)
- Offer curated starter set (10-15 sources)
- Provide step-by-step setup guide

**Success Criteria:**
- User can start reading in <5 minutes
- Manageable initial source count
- Clear next steps

---

## Test Case 8: Feed Cleanup
**User Input:** "I have 300 feeds and I'm overwhelmed"
**Expected Behavior:**
- Load source-quality.md
- Explain quality assessment process
- Offer to analyze OPML if provided
- Suggest pruning strategy

**Success Criteria:**
- User has actionable cleanup plan
- Understands quality criteria
- Can reduce to manageable number

---

## Trigger Pattern Tests

### Should Trigger:
- "RSS feeds"
- "OPML import"
- "Karpathy sources"
- "Feed reader"
- "Information curation"
- "Filter bubble"
- "Algorithmic feeds"
- "NetNewsWire"
- "Feedly"

### Should NOT Trigger:
- "Social media feeds" (different context)
- "News aggregator" (unless RSS-specific)
- "Twitter timeline" (not RSS)

---

## Edge Cases

### Edge Case 1: User has no RSS reader
**Input:** "What's RSS?"
**Expected:** Explain RSS, recommend reader, offer setup help

### Edge Case 2: User wants all 92 sources
**Input:** "Import all 92 sources"
**Expected:** Warn about overwhelming, suggest starting smaller, but provide full OPML if insisted

### Edge Case 3: Dead feed in Karpathy's list
**Input:** "This feed isn't working: [URL]"
**Expected:** Acknowledge, check status, suggest alternative, offer to update list

### Edge Case 4: Non-English sources
**Input:** "Do you have Chinese tech blogs?"
**Expected:** Explain Karpathy's list is English-focused, offer to help find Chinese sources, suggest quality criteria still apply

---

## Performance Criteria

- **Response Time:** <2 seconds for simple queries
- **OPML Generation:** <5 seconds for full 92-source file
- **Quality Assessment:** <10 seconds per feed
- **Source Discovery:** <30 seconds for 5-10 recommendations

---

## Quality Metrics

### Success Indicators:
- User successfully imports sources
- User can evaluate feed quality independently
- User builds sustainable reading habit (50%+ read rate)
- User discovers new high-quality sources

### Failure Indicators:
- User overwhelmed by too many sources
- User can't import OPML (format issues)
- User gets low-quality recommendations
- User abandons RSS after setup

---

## Maintenance Tests

### Monthly:
- Verify all 92 sources still active
- Check RSS feed URLs still valid
- Update any changed feed URLs
- Add new high-quality sources if available

### Quarterly:
- Review quality criteria relevance
- Update AI processing workflows
- Check garss compatibility
- Refresh examples and use cases

---

## Integration Tests

### With RSS Readers:
- NetNewsWire (Mac/iOS)
- Feedly (Web)
- Inoreader (Web)
- Miniflux (Self-hosted)

### With AI Tools:
- garss (if installed)
- Claude API (for custom workflows)
- Local processing scripts

### With Note-Taking:
- Obsidian (markdown export)
- Notion (structured data)
- Plain text (universal)

---

## Documentation Tests

### README.md:
- Clear value proposition
- Quick start works
- Examples are actionable
- Links are valid

### SKILL.md:
- Trigger patterns comprehensive
- Workflows well-defined
- References properly linked
- Examples cover common cases

### Reference Docs:
- Technically accurate
- Practically useful
- Well-organized
- Up-to-date

---

## User Feedback Collection

After using the skill, ask:
1. Did you successfully import sources?
2. Are you reading the feeds regularly?
3. What features are most useful?
4. What's missing or confusing?
5. Would you recommend this to others?

Target: 4.5/5 average satisfaction

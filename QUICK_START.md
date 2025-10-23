# Quick Start Guide: Research Prompts

Get started with the research prompts workflow in 5 minutes.

---

## For Brand New Projects

### Step 1: Setup (5 minutes)
```bash
# In your paper project directory
mkdir -p .github research paper conference_paper review

# Create your project configuration
# See PROJECT_SETUP.md for field-specific templates
```

Create `.github/copilot-instructions.md`:
```markdown
# Project: [Your Paper Title]

## Field
[Medical/CS/Psychology/Natural Sciences/Engineering/Cross-disciplinary]

## Target Venue
Journal: [Journal Name]
Reporting Standard: [CONSORT/PRISMA/IEEE/etc.]
Citation Style: [APA/IEEE/Vancouver/etc.]

## Key Requirements
- Word limit: [X words]
- Figure limit: [X figures]
- Required sections: [list]
```

### Step 2: Start the Workflow

**Week 1-2: Collect Literature**
```
@workspace /chatmode Researcher

Using reseaerch-papers.prompt.md, search for literature on [your topic]
```

**Week 2-3: Plan Structure**
```
Using outline.prompt.md, create a detailed outline from the collected literature
```

**Week 3-5: Write Manuscript**
```
Using write.prompt.md, draft the full manuscript following the outline
```

**Week 5-6: Create Supplementary Materials**
```
Using supplementary.prompt.md, document extended methods, code, and data
```

**Week 6: Pre-Submission**
```
# Check quality
Using presubmission_check.prompt.md, verify the manuscript is ready for submission

# Create cover letter
Using cover_letter.prompt.md, create a submission cover letter for [Journal Name]
```

**Submit and wait for reviews...**

**After receiving reviews:**
```
# Create response
Using rebuttal.prompt.md, generate point-by-point responses to the reviewer comments

# Revise manuscript
Using rewrite.prompt.md, revise the manuscript addressing all reviewer comments

# Create revision letter
Using revision_letter.prompt.md, create a brief cover letter for the revision
```

---

## For Existing Manuscripts

### Already Have a Draft?

**Quick Quality Check (1 hour)**
```
Using presubmission_check.prompt.md, review my manuscript for issues before submission
```

**Need a Cover Letter? (1 hour)**
```
Using cover_letter.prompt.md, create a submission cover letter for [Journal Name]
```

**Organize Supplementary Materials (1 day)**
```
Using supplementary.prompt.md, organize my extended methods, code, and data files
```

### Just Received Reviews?

**Create Response (1-3 days)**
```
Using rebuttal.prompt.md, respond to these reviewer comments:
[paste reviewer comments]
```

**Revise Manuscript (3-7 days)**
```
Using rewrite.prompt.md, revise the manuscript to address the reviewer feedback
```

**Create Revision Letter (30 minutes)**
```
Using revision_letter.prompt.md, create a cover letter for this revision
```

---

## For Conference Papers

### From Full Manuscript to Conference Paper (2-3 days)
```
Using rewrite_to_conference.prompt.md, condense my full manuscript to 8 pages for [Conference Name]
```

### Conference Revision (1-2 days)
```
Using rewrite_conference.prompt.md, revise this conference paper while maintaining the 8-page limit
```

---

## Cheat Sheet: Which Prompt When?

| I need to... | Use this prompt | Time needed |
|--------------|-----------------|-------------|
| Find and verify literature | `reseaerch-papers` | 1-2 weeks |
| Plan manuscript structure | `outline` | 2-3 days |
| Write full manuscript | `write` | 1-2 weeks |
| Create supplementary materials | `supplementary` | 3-5 days |
| Get internal review | `review` | 2-4 hours |
| Check quality before submission | `presubmission_check` | 1-2 hours |
| Write submission cover letter | `cover_letter` | 1-2 hours |
| Respond to reviewers | `rebuttal` | 1-3 days |
| Revise manuscript | `rewrite` | 3-7 days |
| Write revision cover letter | `revision_letter` | 30-60 min |
| Create conference version | `rewrite_to_conference` | 2-3 days |
| Review conference paper | `review_conference` | 1-2 hours |
| Revise conference paper | `rewrite_conference` | 1-2 days |

---

## Common Patterns

### Pattern 1: "I'm starting from scratch"
```
reseaerch-papers → outline → write → supplementary 
→ presubmission_check → cover_letter → SUBMIT
```

### Pattern 2: "I have a draft, need to submit"
```
presubmission_check → [fix issues] → cover_letter → SUBMIT
```

### Pattern 3: "Just got reviews back"
```
rebuttal → rewrite → revision_letter → RESUBMIT
```

### Pattern 4: "Need conference version fast"
```
rewrite_to_conference → presubmission_check → cover_letter → SUBMIT
```

---

## Pro Tips

### 💡 Tip 1: Always outline first
Outlining with `outline.prompt.md` saves 3-5x time during writing. Don't skip this step even if you're experienced.

### 💡 Tip 2: Use pre-submission check every time
Run `presubmission_check.prompt.md` before every submission (initial, revision, conference). Catches 90%+ of desk rejection issues.

### 💡 Tip 3: Create supplementary materials early
Don't wait until revision. Create `supplementary` materials right after main manuscript while methods are fresh.

### 💡 Tip 4: Craft rebuttal before revising
Use `rebuttal.prompt.md` first to plan your responses, THEN use `rewrite.prompt.md`. This ensures consistency between what you say and what you do.

### 💡 Tip 5: Customize for your field
Set up `.github/copilot-instructions.md` once per project. All prompts will automatically use your field-specific requirements.

### 💡 Tip 6: Keep revision letters brief
`revision_letter.prompt.md` should be 200-400 words max. Details go in the `rebuttal` document.

---

## Activating Prompts

### Using Researcher Chatmode
```
@workspace /chatmode Researcher
```

### Referencing Specific Prompts
```
Using write.prompt.md, create a manuscript about [topic]

Following presubmission_check.prompt.md, verify this manuscript

Using rebuttal.prompt.md, respond to these reviewer comments:
[paste comments]
```

---

## Troubleshooting

### "I don't know what field-specific requirements I need"
→ See `PROJECT_SETUP.md` for templates for Medical, CS/AI, Psychology, Natural Sciences, and Engineering

### "The manuscript is too long"
→ Use `rewrite_to_conference.prompt.md` to learn condensation strategies, even if not submitting to a conference

### "I got desk rejected"
→ Run `presubmission_check.prompt.md` on your next submission. It catches most desk rejection issues.

### "Reviewers asked for something unreasonable"
→ Use `rebuttal.prompt.md` - it includes diplomatic disagreement templates

### "I'm not sure if I should use outline.prompt.md"
→ If your manuscript will be >5,000 words, always use it. You'll save days in the writing phase.

---

## Success Metrics

After using the complete workflow, you should see:

✅ **Faster writing** - Outlining reduces writing time by 40-60%  
✅ **Fewer desk rejections** - Pre-submission checking prevents 90%+ of technical issues  
✅ **Better reviews** - Higher quality manuscripts get better initial reviews  
✅ **Faster revisions** - Structured rebuttal process reduces revision time  
✅ **More professional communication** - Better cover letters and rebuttals

---

## Next Steps

1. **Read the full README.md** for complete workflow documentation
2. **Review PROJECT_SETUP.md** for field-specific templates
3. **Check WORKFLOW_VISUAL.md** for detailed flowcharts
4. **See CHANGELOG.md** for what's new in this version

---

## Getting Help

- **Documentation**: README.md (complete overview)
- **Field Setup**: PROJECT_SETUP.md (templates for 5+ fields)
- **Workflow Details**: WORKFLOW_VISUAL.md (flowcharts and timing)
- **Changes**: CHANGELOG.md (what's new)
- **Support**: Open an issue in the repository

---

## Minimum Viable Workflow (Emergency Fast-Track)

If you have a tight deadline and need to skip steps:

```
MINIMUM (can't skip these):
  1. reseaerch-papers (abbreviated search)
  2. write (focus on core sections)
  3. presubmission_check (critical issues only)
  4. cover_letter
  → SUBMIT

CAN SKIP for first submission:
  - outline (if experienced writer)
  - supplementary (add during revision)
  - internal review (if confident)

NEVER SKIP:
  - Literature verification (fabrication risk)
  - Pre-submission check (desk rejection risk)
  - Cover letter (acceptance vs desk rejection)
```

**Time for emergency workflow**: 1-2 weeks instead of 4-6 weeks

---

**Ready to start?** Activate Researcher mode and use your first prompt! 🚀

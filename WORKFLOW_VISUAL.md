# Research Paper Workflow Visualization

This document provides visual representations of the complete research paper workflow using all 13 prompts.

---

## Complete Journal Article Workflow

```
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃  PHASE 1: RESEARCH AND PLANNING (1-3 weeks)                        ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛

    ┌─────────────────────────────────────────────────────┐
    │  1. reseaerch-papers.prompt.md                      │
    │     Systematic literature search & verification     │
    │                                                     │
    │  Input:   Research question, search keywords       │
    │  Output:  research/, paper/references.bib          │
    │  Time:    1-2 weeks                                │
    └─────────────────────────────────────────────────────┘
                           │
                           │ 20-50 annotated papers
                           ↓
    ┌─────────────────────────────────────────────────────┐
    │  2. outline.prompt.md                               │
    │     Pre-writing planning & structure                │
    │                                                     │
    │  Input:   Literature collection, research data      │
    │  Output:  paper/outline.md, literature_map.md      │
    │  Time:    2-3 days                                 │
    └─────────────────────────────────────────────────────┘

┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃  PHASE 2: WRITING (1-3 weeks)                                      ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛

    ┌─────────────────────────────────────────────────────┐
    │  3. write.prompt.md                                 │
    │     Full manuscript creation                        │
    │                                                     │
    │  Input:   Outline, literature, research data        │
    │  Output:  paper/main.tex, figures/, references.bib │
    │  Time:    1-2 weeks                                │
    └─────────────────────────────────────────────────────┘
                           │
                           │ Complete manuscript
                           ↓
    ┌─────────────────────────────────────────────────────┐
    │  4. supplementary.prompt.md                         │
    │     Supplementary materials creation                │
    │                                                     │
    │  Input:   Extended methods, code, data              │
    │  Output:  paper/supplementary/ (all materials)     │
    │  Time:    3-5 days                                 │
    └─────────────────────────────────────────────────────┘

┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃  PHASE 3: PRE-SUBMISSION (1-3 days)                                ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛

    ┌─────────────────────────────────────────────────────┐
    │  5. review.prompt.md (OPTIONAL)                     │
    │     Internal peer review before submission          │
    │                                                     │
    │  Input:   Complete manuscript                       │
    │  Output:  Internal review comments                 │
    │  Time:    2-4 hours                                │
    └─────────────────────────────────────────────────────┘
                           │
                           │ Review feedback (if done)
                           ↓
    ┌─────────────────────────────────────────────────────┐
    │  6. presubmission_check.prompt.md                   │
    │     Final quality verification (150+ checks)        │
    │                                                     │
    │  Input:   Manuscript + supplementary + journal info │
    │  Output:  paper/presubmission_report.md            │
    │  Time:    1-2 hours                                │
    └─────────────────────────────────────────────────────┘
                           │
                           │ Fix all critical issues
                           ↓
    ┌─────────────────────────────────────────────────────┐
    │  7. cover_letter.prompt.md                          │
    │     Submission cover letter creation                │
    │                                                     │
    │  Input:   Manuscript, journal info, key findings    │
    │  Output:  paper/cover_letter.md                    │
    │  Time:    1-2 hours                                │
    └─────────────────────────────────────────────────────┘
                           │
                           │ Ready to submit!
                           ↓
              ╔═══════════════════════════╗
              ║  SUBMIT TO JOURNAL        ║
              ╚═══════════════════════════╝
                           │
                           │ 2-6 months waiting...
                           ↓
              ╔═══════════════════════════╗
              ║  RECEIVE PEER REVIEWS     ║
              ║  Decision: Major Revision ║
              ╚═══════════════════════════╝

┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃  PHASE 4: REVISION (1-2 weeks)                                     ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛

    ┌─────────────────────────────────────────────────────┐
    │  8. rebuttal.prompt.md                              │
    │     Point-by-point response to reviewers            │
    │                                                     │
    │  Input:   All reviewer comments, original manuscript│
    │  Output:  paper/response_to_reviewers.md           │
    │  Time:    1-3 days                                 │
    └─────────────────────────────────────────────────────┘
                           │
                           │ Complete response plan
                           ↓
    ┌─────────────────────────────────────────────────────┐
    │  9. rewrite.prompt.md                               │
    │     Manuscript revision addressing all comments     │
    │                                                     │
    │  Input:   Reviews, rebuttal plan, original manuscript│
    │  Output:  Revised paper/main.tex                   │
    │  Time:    3-7 days                                 │
    └─────────────────────────────────────────────────────┘
                           │
                           │ Revised manuscript
                           ↓
    ┌─────────────────────────────────────────────────────┐
    │  10. revision_letter.prompt.md                      │
    │      Brief cover letter for revision submission     │
    │                                                     │
    │  Input:   Rebuttal, summary of changes              │
    │  Output:  paper/revision_cover_letter.md           │
    │  Time:    30-60 minutes                            │
    └─────────────────────────────────────────────────────┘
                           │
                           │ Complete revision package
                           ↓
              ╔═══════════════════════════╗
              ║  RESUBMIT TO JOURNAL      ║
              ╚═══════════════════════════╝
                           │
                           │ 1-3 months...
                           ↓
              ╔═══════════════════════════╗
              ║  ACCEPTED! 🎉            ║
              ╚═══════════════════════════╝
```

---

## Parallel Conference Paper Track

This can happen at any point after Phase 2 (manuscript written):

```
┏━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃  PHASE 5: CONFERENCE PAPER (parallel to journal submission)        ┃
┗━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┛

    Starting from: paper/main.tex (full manuscript)
                           │
                           ↓
    ┌─────────────────────────────────────────────────────┐
    │  11. rewrite_to_conference.prompt.md                │
    │      Condense to 8-page conference format           │
    │                                                     │
    │  Input:   Full manuscript (paper/main.tex)          │
    │  Output:  conference_paper/ (8-page version)       │
    │  Time:    2-3 days                                 │
    └─────────────────────────────────────────────────────┘
                           │
                           │ 8-page conference paper
                           ↓
    ┌─────────────────────────────────────────────────────┐
    │  presubmission_check.prompt.md                      │
    │  Verify conference version quality                  │
    └─────────────────────────────────────────────────────┘
                           │
                           ↓
    ┌─────────────────────────────────────────────────────┐
    │  cover_letter.prompt.md                             │
    │  Conference submission cover letter                 │
    └─────────────────────────────────────────────────────┘
                           │
                           ↓
              ╔═══════════════════════════╗
              ║  SUBMIT TO CONFERENCE     ║
              ╚═══════════════════════════╝
                           │
                           ↓
              ╔═══════════════════════════╗
              ║  RECEIVE REVIEWS          ║
              ║  Decision: Accept w/      ║
              ║  Minor Revisions          ║
              ╚═══════════════════════════╝
                           │
                           ↓
    ┌─────────────────────────────────────────────────────┐
    │  rebuttal.prompt.md                                 │
    │  Response to conference reviewers                   │
    └─────────────────────────────────────────────────────┘
                           │
                           ↓
    ┌─────────────────────────────────────────────────────┐
    │  12. rewrite_conference.prompt.md                   │
    │      Revise within 8-page constraint                │
    │                                                     │
    │  Input:   Reviews, 8-page paper, rebuttal           │
    │  Output:  Revised conference_paper/main.tex        │
    │  Time:    1-2 days                                 │
    └─────────────────────────────────────────────────────┘
                           │
                           ↓
    ┌─────────────────────────────────────────────────────┐
    │  revision_letter.prompt.md                          │
    │  Conference revision cover letter                   │
    └─────────────────────────────────────────────────────┘
                           │
                           ↓
              ╔═══════════════════════════╗
              ║  RESUBMIT TO CONFERENCE   ║
              ╚═══════════════════════════╝
                           │
                           ↓
              ╔═══════════════════════════╗
              ║  ACCEPTED! 🎉            ║
              ║  Present at conference    ║
              ╚═══════════════════════════╝
```

---

## Decision Tree: Which Prompt to Use When?

```
START: I need to...
│
├─ Collect and verify literature
│  └─> USE: reseaerch-papers.prompt.md
│
├─ Plan my manuscript structure
│  └─> USE: outline.prompt.md
│
├─ Write a full manuscript
│  └─> USE: write.prompt.md
│
├─ Create supplementary materials
│  └─> USE: supplementary.prompt.md
│
├─ Get feedback before submission
│  └─> USE: review.prompt.md
│
├─ Check manuscript quality before submission
│  └─> USE: presubmission_check.prompt.md
│
├─ Write a submission cover letter
│  ├─ Is this the first submission?
│  │  ├─ YES → USE: cover_letter.prompt.md
│  │  └─ NO (it's a revision) → USE: revision_letter.prompt.md
│  │
│
├─ Respond to peer reviews
│  └─> USE: rebuttal.prompt.md
│
├─ Revise my manuscript
│  ├─ Is it a conference paper (8 pages)?
│  │  ├─ YES → USE: rewrite_conference.prompt.md
│  │  └─ NO (full journal paper) → USE: rewrite.prompt.md
│  │
│
├─ Create a conference version from full paper
│  └─> USE: rewrite_to_conference.prompt.md
│
└─ Review a conference paper
   └─> USE: review_conference.prompt.md
```

---

## Time Estimates by Phase

| Phase | Duration | Prompts Used | Parallel Work Possible? |
|-------|----------|--------------|------------------------|
| **Phase 1: Research & Planning** | 1-3 weeks | reseaerch-papers, outline | No (sequential) |
| **Phase 2: Writing** | 1-3 weeks | write, supplementary | Some (can draft while collecting final data) |
| **Phase 3: Pre-Submission** | 1-3 days | review (opt), presubmission_check, cover_letter | Yes (can do in parallel with co-author review) |
| **Phase 4: Revision** | 1-2 weeks | rebuttal, rewrite, revision_letter | No (sequential) |
| **Phase 5: Conference** | 2-5 days | rewrite_to_conference, rewrite_conference | Yes (parallel to journal submission) |

---

## Critical Path Analysis

**Shortest Path to Submission (journal):**
```
reseaerch-papers (1-2 weeks) 
  → outline (2-3 days)
  → write (1-2 weeks)
  → presubmission_check (1-2 hours)
  → cover_letter (1-2 hours)
  → SUBMIT

Total: 2.5-4.5 weeks
```

**Shortest Path to Submission (conference):**
```
[Assuming full manuscript exists]
rewrite_to_conference (2-3 days)
  → presubmission_check (1-2 hours)
  → cover_letter (1-2 hours)
  → SUBMIT

Total: 2-4 days
```

**Shortest Path to Revision Submission:**
```
[After receiving reviews]
rebuttal (1-3 days)
  → rewrite (3-7 days)
  → revision_letter (30-60 min)
  → RESUBMIT

Total: 4-10 days
```

---

## Typical Timeline for Complete Publication

```
Month 1-2:    Phase 1 (Research & Planning)
Month 2-3:    Phase 2 (Writing)
Month 3:      Phase 3 (Pre-Submission)
Month 3:      Initial Submission
Month 3-9:    Under Review (waiting)
Month 9-10:   Phase 4 (Revision)
Month 10:     Revision Submission
Month 10-12:  Second Review (waiting)
Month 12:     Acceptance! 🎉
Month 12-18:  Production and Publication

Total: 12-18 months from start to publication
```

**Conference track (parallel):**
```
Month 3:      Phase 5 (Conference condensation) - 2-3 days
Month 3:      Conference Submission
Month 4-6:    Conference Review (shorter cycle)
Month 6:      Conference Revision - 1-2 days
Month 7:      Conference Acceptance
Month 8-9:    Present at Conference

Total: 5-6 months from manuscript to presentation
```

---

## Prompt Dependencies

```
FOUNDATIONAL (no dependencies):
  ├─ reseaerch-papers.prompt.md

REQUIRES LITERATURE:
  ├─ outline.prompt.md (needs literature collection)
  └─ write.prompt.md (needs literature + outline recommended)

REQUIRES MANUSCRIPT:
  ├─ supplementary.prompt.md (needs main manuscript context)
  ├─ review.prompt.md (needs complete manuscript)
  ├─ presubmission_check.prompt.md (needs complete manuscript)
  ├─ cover_letter.prompt.md (needs complete manuscript)
  └─ rewrite_to_conference.prompt.md (needs full manuscript)

REQUIRES REVIEWS:
  ├─ rebuttal.prompt.md (needs reviewer comments)
  └─ rewrite.prompt.md (needs reviews + rebuttal)
  └─ rewrite_conference.prompt.md (needs reviews + rebuttal)

REQUIRES REVISION:
  └─ revision_letter.prompt.md (needs completed revision)
```

---

## Success Metrics

After implementing this complete workflow, expect:

- **40-60% reduction** in writing time (due to detailed outlining)
- **90%+ reduction** in desk rejections (due to pre-submission checking)
- **Higher acceptance rates** on first submission (due to quality checks)
- **Faster revisions** (due to structured rebuttal process)
- **Better reproducibility** (due to systematic supplementary materials)
- **More professional communication** (due to cover letter templates)

---

## Emergency Fast-Track Workflow

When facing a tight deadline, minimum viable workflow:

```
reseaerch-papers (abbreviated)
  → write (focus on core sections)
  → presubmission_check (critical issues only)
  → cover_letter
  → SUBMIT

Skip for fast-track:
  - outline (experienced writers)
  - supplementary (can add during revision)
  - internal review (if confident)
```

**Not recommended to skip:**
- Literature verification (fabrication risk)
- Pre-submission check (desk rejection risk)
- Cover letter (moves to review vs desk rejection)

# Changelog - Research Prompts Repository

## 2025-10-23 - Major Update: Complete Workflow Enhancement

This update includes both best practices enhancements to existing prompts AND six new prompts that fill critical gaps in the research paper workflow.

### Part 1: Best Practices Enhancement (Applied to Existing Prompts)

### Overview
Comprehensive update to add missing scientific paper best practices across all prompts and chatmode while maintaining field-agnostic design. Project-specific and field-specific requirements now go in each project's `.github/copilot-instructions.md` file.

### New Files Created

#### PROJECT_SETUP.md
Complete guide for setting up scientific paper projects with:
- Template for `.github/copilot-instructions.md`
- Field-specific templates for:
  - Medical/Health Sciences
  - Computer Science/AI
  - Psychology/Social Sciences
  - Natural Sciences (Biology/Chemistry/Physics)
  - Engineering
- Cross-disciplinary paper guidance
- Usage examples and troubleshooting

### Updates to All Prompts

#### Universal Best Practices Added to All Prompts

**Section Structure (Consistency Fix)**
- All prompts now enforce: "Every section and subsection must begin with at least one introductory paragraph before any subsection heading"
- Previously only in: write.prompt.md, review.prompt.md, rewrite.prompt.md
- Now added to: reseaerch-papers.prompt.md, review_conference.prompt.md, rewrite_conference.prompt.md

**Statistical Reporting Requirements**
- Effect sizes (Cohen's d, odds ratios, correlation coefficients)
- Confidence intervals (typically 95%)
- Exact p-values (not just p < 0.05)
- Multiple testing corrections (Bonferroni, FDR, etc.)
- Power analysis reporting
- Statistical assumption checking

**Abstract Quality Guidelines**
- IMRAD structure (Introduction/Background, Methods, Results, Discussion/Conclusions)
- Self-contained (no citations)
- All acronyms defined
- Quantitative results when possible
- Clear statement of novelty/contribution

**Figure Quality Standards**
- Prefer vector formats (PDF, SVG) over raster
- Minimum resolution: 300 DPI for print, 600 DPI for line art
- Colorblind-accessible when using color
- Standalone captions
- Proper file naming conventions

**Writing Quality Guidelines**
- Paragraph length: 4-8 sentences typically
- Sentence length: prefer <25-30 words
- Jargon minimization
- Acronym definition on first use
- Transition words between sections
- Parallel structure in lists

**Limitations Requirements**
- Dedicated Limitations section or subsection
- Honest assessment of study constraints
- Potential biases noted
- Future work identified

**Open Science Practices**
- Data availability statements (repository DOI, access protocol)
- Code availability statements (repository links, licenses)
- Author contributions (CRediT taxonomy)
- ORCID identifiers
- Funding sources with grant numbers
- Conflict of interest disclosures
- Preregistration documentation when applicable

**Reproducibility Standards**
- Dataset identifiers (DOI/URL)
- Code repositories with version control
- Software versions and dependencies
- Hardware specifications (for computational work)
- Random seeds and initialization
- Preprocessing pipeline documentation
- Docker/Singularity containers when applicable

**Ethics and Compliance**
- IRB/ethics approval numbers
- Clinical trial registration
- Informed consent procedures
- Data protection compliance (GDPR, HIPAA)
- Animal care committee approvals
- Dual-use considerations

**Venue-Specific Awareness**
- Reminder to check `.github/copilot-instructions.md` for project requirements
- Recommendation to consult target venue author guidelines
- Awareness of field-specific reporting standards (CONSORT, PRISMA, IEEE, etc.)

### Specific File Updates

#### reseaerch-papers.prompt.md
- ✅ Added section structure rule for literature summaries
- ✅ Added limitations requirement for synthesized literature reviews
- ✅ Enhanced annotation requirements to include statistical quality
- ✅ Fixed mode capitalization (researcher → Researcher)

#### write.prompt.md
- ✅ Added comprehensive abstract quality guidelines
- ✅ Added statistical reporting requirements
- ✅ Added writing quality guidelines (paragraph/sentence length, jargon, acronyms)
- ✅ Added figure quality standards (resolution, accessibility, vector formats)
- ✅ Added open science practices section
- ✅ Added venue-specific requirements reminder
- ✅ Enhanced quality checklist (10 items)
- ✅ Fixed mode capitalization (researcher → Researcher)

#### review.prompt.md
- ✅ Added statistical quality check to primary responsibilities
- ✅ Added abstract quality check
- ✅ Added open science compliance check
- ✅ Added writing quality assessment
- ✅ Enhanced review structure with 3 new checklist sections:
  - Statistical reporting checklist
  - Open science checklist
  - Writing quality check
- ✅ Added field-specific requirements awareness
- ✅ Updated scoring rubric to include statistical quality and open science

#### rewrite.prompt.md
- ✅ Added quality enhancement goals (statistics, figures, abstract, limitations)
- ✅ Added open science improvement goal
- ✅ Added statistical quality requirements
- ✅ Added figure quality requirements
- ✅ Added abstract quality requirements
- ✅ Added open science requirements
- ✅ Added limitations requirement
- ✅ Enhanced quality checklist (12 items)

#### rewrite_to_conference.prompt.md
- ✅ Added "Preserving Core Quality" section with minimum requirements:
  - Sufficient reproducibility information
  - Ethics and data availability statements
  - Statistical reporting quality
  - Clear statement of limitations
  - Proper section structure
- ✅ Enhanced condensation verification checklist (10 items)

#### review_conference.prompt.md
- ✅ Added comprehensive conference standards checklist:
  - Section structure check
  - Reproducibility check
  - Statistical reporting check
  - Ethics/data statements check
  - Limitations discussion check

#### rewrite_conference.prompt.md
- ✅ Added quality standards to core revision goals
- ✅ Enhanced quality checklist (10 items) including:
  - Statistical reporting quality
  - Section structure preservation
  - Ethics and limitations statements
  - Reproducibility information
  - Page budget explanations

#### Researcher.chatmode.md
- ✅ Added reference to `.github/copilot-instructions.md` for project-specific requirements
- ✅ Added statistical methods awareness to reproducibility
- ✅ Added comprehensive quality standards to primary behaviors:
  - Section structure enforcement
  - Statistical reporting (effect sizes, sample sizes)
  - Limitations in literature summaries
  - Abstract structure and self-containment
  - Figure quality (vector graphics, colorblind accessibility)

#### README.md
- ✅ Updated "Usage with GitHub Copilot" section with PROJECT_SETUP.md reference
- ✅ Renamed "Core Principles" to "Best Practices"
- ✅ Added "Field-Specific Standards" best practice
- ✅ Added "Cross-Disciplinary Papers" best practice with link to detailed guidance
- ✅ Enhanced workspace integration description

### Breaking Changes
None. All changes are additive and backward compatible.

### Migration Guide
For existing projects:
1. Review your current manuscripts against new quality standards
2. Create `.github/copilot-instructions.md` in your project (see PROJECT_SETUP.md)
3. Specify your field-specific requirements
4. Re-run prompts to incorporate new best practices

### Benefits
- **Consistency**: All prompts now enforce the same structural and quality standards
- **Completeness**: No more missing critical requirements (statistics, limitations, ethics, open science)
- **Flexibility**: Universal prompts work for any field; customization happens in project config
- **Modern Standards**: Incorporates 2025 open science and reproducibility requirements
- **Cross-Disciplinary**: Explicit support for papers spanning multiple fields
- **Quality**: Comprehensive checklists ensure nothing is overlooked

### Field Coverage
Templates and guidance now cover:
- Medical/Health Sciences (CONSORT, PRISMA, STROBE, ARRIVE, CARE, STARD, CHEERS, TRIPOD)
- Computer Science/AI (ACM artifact evaluation, algorithm complexity, Docker containers)
- Psychology/Social Sciences (APA 7th, preregistration, power analysis)
- Natural Sciences (protocols, reagents, GenBank, PDB)
- Engineering (specifications, standards compliance, patents)
- Cross-disciplinary papers (terminology bridges, multi-field standards)

### Statistical Reporting Coverage
Now includes guidance for:
- Effect sizes (Cohen's d, odds ratios, η², correlation coefficients)
- Confidence intervals
- P-values (exact values, corrections for multiple testing)
- Power analysis
- Assumption checking
- Bayesian methods (priors, credible intervals)
- Sample size justification

### Open Science Coverage
Now includes:
- Preregistration (OSF, AsPredicted, ClinicalTrials.gov)
- Data repositories (Dryad, Zenodo, FigShare, domain-specific)
- Code repositories (GitHub, GitLab with DOI via Zenodo)
- ORCID identifiers
- CRediT author contributions
- Funding disclosure with grant numbers
- Conflict of interest statements
- Preprint servers (arXiv, bioRxiv, PsyArXiv)
- FAIR data principles
- Open access considerations

### Next Steps
Users should:
1. Read PROJECT_SETUP.md for comprehensive guidance
2. Create `.github/copilot-instructions.md` in their paper workspaces
3. Start using updated prompts with field-specific configurations
4. Consult EQUATOR Network and venue guidelines for specific requirements

---

## Part 2: New Workflow Prompts (6 New Additions)

Six critical prompts have been added to fill workflow gaps identified through systematic analysis. These prompts cover the complete lifecycle from planning through revision submission.

### New Tier 1 Prompts (Critical Missing Pieces)

#### 1. rebuttal.prompt.md - Response to Reviewers
**Purpose:** Generate professional, thorough point-by-point responses to peer reviewers

**Why it was missing:** The workflow had `review.prompt.md` (generating reviews) and `rewrite.prompt.md` (revising manuscripts), but nothing for the critical rebuttal document that accompanies every revision.

**What it provides:**
- Systematic point-by-point response structure
- Respectful tone guidance (even when disagreeing)
- Specific change tracking with line numbers
- Diplomatic disagreement templates
- Examples for common reviewer comment types
- 10-point quality checklist

**Key sections:**
- Opening statement (gratitude and summary)
- Point-by-point responses with quoted changes
- Additional improvements made
- Closing statement
- Examples of accepted changes, partial agreements, and respectful disagreements

**Deliverables:** `paper/response_to_reviewers.md`

---

#### 2. cover_letter.prompt.md - Initial Submission Cover Letter
**Purpose:** Create compelling cover letters introducing manuscripts to journal editors

**Why it was missing:** No support for the initial submission cover letter, which is required by most journals and often determines whether a manuscript moves to peer review or desk rejection.

**What it provides:**
- Journal fit justification guidance
- Significance and novelty articulation
- Required declarations (ethics, COI, funding)
- Suggested reviewers section (with justification templates)
- 12-point quality checklist
- Examples for different scenarios (high-impact journals, clinical journals, etc.)

**Key sections:**
- Introduction and significance paragraph
- Journal fit explanation
- Compliance declarations
- Suggested/excluded reviewers
- Complete example letter

**Deliverables:** `paper/cover_letter.md`, `paper/suggested_reviewers.md`

---

#### 3. outline.prompt.md - Pre-Writing Planning
**Purpose:** Transform collected literature into a detailed manuscript blueprint

**Why it was missing:** Large gap between `reseaerch-papers.prompt.md` (literature pile) and `write.prompt.md` (full manuscript). No structured planning phase.

**What it provides:**
- Section-by-section content planning with length targets
- Literature-to-section mapping
- Figure and table planning with specifications
- IMRAD abstract structure planning
- Writing priority guidance
- 12-point quality checklist

**Key sections:**
- Manuscript metadata and contribution summary
- Abstract outline (IMRAD)
- Detailed section outlines with bullet points
- Figure/table plan with purpose and content
- Literature map (which papers cite where)
- Writing priorities (what to write first)
- Open questions and to-do list

**Deliverables:** `paper/outline.md`, `paper/literature_map.md`, `paper/figure_plan.md`, `paper/writing_todos.md`

---

### New Tier 2 Prompts (High-Value Additions)

#### 4. supplementary.prompt.md - Supplementary Materials
**Purpose:** Create comprehensive supplementary materials for reproducibility

**Why it was missing:** Modern papers increasingly require extensive supplementary materials (extended methods, code, data, additional analyses), but no guidance existed for creating these.

**What it provides:**
- Structure for 6 types of supplementary content (methods, results, figures, tables, code, text)
- Code documentation standards (README, comments, usage examples)
- Data documentation (data dictionaries, format specifications)
- Figure/table quality standards for supplementary materials
- 13-point quality checklist

**Key sections:**
- Supplementary methods (extended protocols, algorithms)
- Supplementary results (secondary analyses, validation)
- Supplementary figures and tables (with "S" numbering)
- Code and data documentation
- Field-specific examples (clinical, computational, systematic review, etc.)

**Deliverables:** `paper/supplementary/supplementary.tex`, `paper/supplementary/code/`, `paper/supplementary/data/`, `paper/supplementary/figures/`

---

#### 5. presubmission_check.prompt.md - Final Quality Verification
**Purpose:** Comprehensive mechanical quality check before submission to prevent desk rejection

**Why it was missing:** `review.prompt.md` provides substantive peer review, but no mechanical/checklist-based quality verification existed. Different purpose: catching formatting issues, missing elements, and technical problems.

**What it provides:**
- 12 comprehensive checklist sections (150+ individual checks)
- Categorized issues (Critical/Important/Minor) with priorities
- Specific, actionable corrections with locations
- Journal-specific requirement checking
- Field-specific requirement awareness
- Submission readiness score

**Checklist coverage:**
1. Manuscript structure (all required sections)
2. Length and formatting (word counts, page limits)
3. Abstract quality (IMRAD, self-contained, quantitative)
4. Figures and tables (resolution, captions, cross-references)
5. Citations and references (completeness, format, DOIs)
6. Statistical reporting (effect sizes, CIs, p-values)
7. Reproducibility (methods detail, code/data availability)
8. Ethics and compliance (IRB, funding, COI)
9. Writing quality (grammar, consistency, jargon)
10. Supplementary materials (numbering, quality)
11. Field-specific requirements (CONSORT, IEEE, etc.)
12. Journal-specific requirements (template, declarations)

**Deliverables:** `paper/presubmission_report.md` with categorized issues and action items

---

#### 6. revision_letter.prompt.md - Revision Submission Cover Letter
**Purpose:** Brief professional letter accompanying revised manuscripts

**Why it was missing:** Different from both initial `cover_letter.prompt.md` (introduces new work) and `rebuttal.prompt.md` (detailed responses). This is the executive summary cover letter for revisions.

**What it provides:**
- Brief format (200-400 words vs. detailed rebuttal)
- Summary of 3-5 major changes
- Editor-specific response guidance
- Gratitude and confidence expression
- 13-point quality checklist

**Key sections:**
- Opening (gratitude and acknowledgment)
- Summary of major changes (high-level only)
- Editor-specific responses
- Additional improvements
- Closing (confidence and availability)
- Examples for minor revision, major revision, second round, etc.

**Deliverables:** `paper/revision_cover_letter.md`

---

### Updated Workflow

The complete workflow now covers:

**Phase 1: Research and Planning**
1. `reseaerch-papers.prompt.md` - Literature search ← existing
2. `outline.prompt.md` - Pre-writing planning ← **NEW**

**Phase 2: Writing**
3. `write.prompt.md` - Manuscript creation ← existing (enhanced)
4. `supplementary.prompt.md` - Supplementary materials ← **NEW**

**Phase 3: Pre-Submission**
5. `review.prompt.md` - Internal review (optional) ← existing (enhanced)
6. `presubmission_check.prompt.md` - Quality verification ← **NEW**
7. `cover_letter.prompt.md` - Submission letter ← **NEW**

**Phase 4: Review and Revision**
8. [Receive peer reviews from journal]
9. `rebuttal.prompt.md` - Response to reviewers ← **NEW**
10. `rewrite.prompt.md` - Manuscript revision ← existing (enhanced)
11. `revision_letter.prompt.md` - Revision letter ← **NEW**

**Phase 5: Conference Papers** (parallel track)
12. `rewrite_to_conference.prompt.md` ← existing (enhanced)
13. `review_conference.prompt.md` ← existing (enhanced)
14. `rewrite_conference.prompt.md` ← existing (enhanced)

### Benefits of New Prompts

- **Completeness:** Workflow now covers every step from planning through revision submission
- **No Gaps:** Critical missing pieces (rebuttal, cover letters, outline, pre-submission check) now filled
- **Time Savings:** Outlining saves 3-5x time in writing; pre-submission check prevents desk rejections
- **Quality Improvement:** Supplementary materials and quality checks raise reproducibility standards
- **Professional Communication:** Cover letters and rebuttals significantly improve acceptance rates

### Migration Guide for Existing Users

For ongoing projects:
1. Use `outline.prompt.md` to retroactively document your manuscript structure
2. Run `presubmission_check.prompt.md` on existing manuscripts before any submission
3. Use `supplementary.prompt.md` to organize existing extended materials
4. Keep `cover_letter.prompt.md` and `rebuttal.prompt.md` ready for submission/revision

For new projects:
1. Follow the complete 13-step workflow from Phase 1 through Phase 5
2. Create project-specific `.github/copilot-instructions.md` (see PROJECT_SETUP.md)
3. Use prompts in sequence for optimal efficiency

### Documentation Updates

- **README.md:** Completely restructured with:
  - Detailed "when to use" guidance for all 13 prompts
  - Visual workflow diagrams for journal and conference tracks
  - Quick reference table with typical durations
  - Expanded directory structure showing all deliverables
  
- **CHANGELOG.md:** This document, comprehensively documenting both best practices enhancements and new prompts

- **PROJECT_SETUP.md:** Existing field-specific setup guide (created in Part 1)

### Breaking Changes
None. All changes are additive. Existing prompts maintain backward compatibility while adding new features.

### Next Steps
Users should:
1. Read PROJECT_SETUP.md for comprehensive guidance
2. Create `.github/copilot-instructions.md` in their paper workspaces
3. Start using updated prompts with field-specific configurations
4. Consult EQUATOR Network and venue guidelines for specific requirements

### Acknowledgments
This update incorporates best practices from:
- EQUATOR Network reporting guidelines
- TOP Factor transparency standards
- Center for Open Science recommendations
- FAIRsharing standards database
- The Turing Way reproducible research handbook

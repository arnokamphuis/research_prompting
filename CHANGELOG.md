# Changelog - Research Prompts Repository

## 2025-10-23 - Major Update: Best Practices Enhancement

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

### Acknowledgments
This update incorporates best practices from:
- EQUATOR Network reporting guidelines
- TOP Factor transparency standards
- Center for Open Science recommendations
- FAIRsharing standards database
- The Turing Way reproducible research handbook

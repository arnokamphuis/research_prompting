# Setting Up a Scientific Paper Project

This guide explains how to use the research prompts and chatmodes from this repository for your specific scientific paper project, with project-specific customizations defined in your workspace's `.github/copilot-instructions.md` file.

## Quick Start

1. **Copy the research prompts to your workspace** (optional, they work from this repo too)
2. **Create `.github/copilot-instructions.md` in your paper's workspace**
3. **Define your field-specific requirements, target venue, and conventions**
4. **Activate the Researcher chatmode**: `@workspace /chatmode Researcher`
5. **Start working**: Use the prompts from this repository as needed

## Project Structure

Your scientific paper project should use this directory structure:

```
your-paper-workspace/
├── .github/
│   └── copilot-instructions.md          # Project-specific configuration
├── research/                             # Literature search artifacts
│   ├── queries.md
│   ├── *-meta.json
│   ├── annotations/
│   ├── ethics.md
│   └── VERIFICATION.md
├── paper/                                # Full manuscript
│   ├── main.tex
│   ├── references.bib
│   ├── figures/
│   ├── literature_summary.tex
│   └── README.md
├── conference_paper/                     # Conference version (if applicable)
│   ├── main.tex
│   ├── references.bib
│   ├── figures/
│   └── response_to_reviewers.md
└── review/                               # Reviews and responses
    └── conference_review.md
```

## Creating Your `.github/copilot-instructions.md`

The `.github/copilot-instructions.md` file is where you specify **project-specific** requirements that customize the general research prompts for your particular paper. GitHub Copilot automatically reads this file and applies these instructions to all interactions in your workspace.

### Template

Create `.github/copilot-instructions.md` in your paper workspace with the following template:

```markdown
# Scientific Paper Project Instructions

## Project Overview
- **Paper Title**: [Your paper title or working title]
- **Field**: [e.g., Medical Sciences, Computer Science, Psychology, etc.]
- **Target Venue**: [e.g., Nature Medicine, ICML 2026, Journal of Educational Psychology]
- **Paper Type**: [e.g., Original Research, Systematic Review, Short Communication]
- **Status**: [e.g., Literature Search, Drafting, Under Review, Revision]

## Field-Specific Requirements

### Reporting Standards
[Specify which reporting guidelines apply to your paper]
- [ ] CONSORT (randomized controlled trials)
- [ ] PRISMA (systematic reviews and meta-analyses)
- [ ] STROBE (observational studies)
- [ ] ARRIVE (animal research)
- [ ] CARE (case reports)
- [ ] STARD (diagnostic accuracy studies)
- [ ] CHEERS (health economic evaluations)
- [ ] TRIPOD (prediction models)
- [ ] ACM Artifact Evaluation (computational research)
- [ ] Other: [specify]

### Citation Style
- **Primary Style**: [APA 7th, IEEE, Vancouver, Chicago, MLA, etc.]
- **Reference Manager**: [BibTeX keys format, e.g., AuthorYearKeyword]
- **Inline Citations**: [e.g., (Author, Year) or [1] or Author (Year)]

### Statistical Requirements
[Specify statistical reporting requirements for your field]
- Report effect sizes: [Cohen's d, odds ratio, correlation coefficient, etc.]
- Confidence intervals: [95% CI required]
- P-value thresholds: [p < 0.05, Bonferroni correction, etc.]
- Power analysis: [Required for null results]
- Multiple testing correction: [Bonferroni, FDR, Holm-Bonferroni, etc.]
- Bayesian methods: [If applicable, specify priors and credible intervals]

### Reproducibility Standards
[Specify what must be included for reproducibility]
- [ ] Dataset DOI/URL or access protocol
- [ ] Code repository (GitHub, GitLab, Zenodo)
- [ ] Software versions (Python 3.x, R 4.x, MATLAB, etc.)
- [ ] Hardware specifications (for computational work)
- [ ] Random seeds and initialization
- [ ] Preprocessing pipeline documentation
- [ ] Analysis scripts with documentation
- [ ] Docker/Singularity containers (if applicable)
- [ ] Computational environment (requirements.txt, environment.yml)

### Ethics and Compliance
[Specify required ethics statements and approvals]
- [ ] Institutional Review Board (IRB) approval number: [insert number]
- [ ] Clinical trial registration: [ClinicalTrials.gov ID, if applicable]
- [ ] Informed consent: [describe procedure]
- [ ] Data protection: [GDPR, HIPAA, etc.]
- [ ] Animal care committee approval: [if applicable]
- [ ] Conflicts of interest: [disclosure requirements]
- [ ] Funding sources: [list and grant numbers]
- [ ] Preregistration: [OSF, AsPredicted, etc.]

### Open Science Practices
[Specify open science commitments]
- [ ] Open Access: [Gold, Green, or specify embargo period]
- [ ] Open Data: [Repository and license]
- [ ] Open Materials: [Protocols, instruments, stimuli]
- [ ] Open Code: [Repository and license]
- [ ] Preprint: [arXiv, bioRxiv, PsyArXiv, etc.]
- [ ] Registered Report: [If applicable]

## Target Venue Specifications

### Journal/Conference Details
- **Venue Name**: [Full name]
- **Submission System**: [Editorial Manager, ScholarOne, EasyChair, etc.]
- **Manuscript Type**: [Research Article, Review, Letter, etc.]
- **Page/Word Limit**: [e.g., 8000 words excluding references, 8 pages including references]
- **Abstract Limit**: [e.g., 250 words, structured or unstructured]
- **Reference Limit**: [e.g., 50 references maximum]
- **Figure Limit**: [e.g., 6 figures maximum]

### Required Sections
[List required sections in order]
1. Title Page (with author affiliations, ORCID, corresponding author)
2. Abstract (structured: Background, Methods, Results, Conclusions)
3. Keywords (5-7 keywords, use [MeSH terms/JEL codes/IEEE keywords])
4. Introduction
5. Methods (or Materials and Methods)
6. Results
7. Discussion
8. Limitations
9. Conclusions
10. Data Availability Statement
11. Code Availability Statement
12. Acknowledgements
13. Author Contributions (CRediT taxonomy)
14. Funding Statement
15. Conflicts of Interest
16. References

### Format Requirements
- **Document Class**: [e.g., article, IEEEtran, elsarticle, amsart]
- **LaTeX Template**: [URL or file location]
- **Line Spacing**: [Single, 1.5, Double]
- **Line Numbers**: [Required for review]
- **Font**: [Times New Roman 12pt, Computer Modern, etc.]
- **Margins**: [1 inch all sides, etc.]
- **Figure Format**: [PDF, EPS, TIFF at 300 DPI minimum]
- **Supplementary Materials**: [Format and submission process]

## Terminology and Conventions

### Field-Specific Terms
[Define standard terminology for consistency]
- [Term 1]: [Definition or preferred usage]
- [Term 2]: [Definition or preferred usage]
- [Acronyms]: [Spell out on first use: Full Name (ACRONYM)]

### Units and Notation
- **Units**: [SI units, Imperial, or specify]
- **Decimal Separator**: [Period or comma]
- **Thousands Separator**: [Comma, space, or none]
- **Significant Figures**: [Standard for your field]
- **Mathematical Notation**: [LaTeX conventions, e.g., \mathbf for vectors]

### Abbreviations
[List approved abbreviations for your paper]
- Use consistently throughout
- Define on first use
- Avoid in title and abstract (except common ones like DNA, RNA, HIV)

## Data and Code

### Datasets
- **Primary Dataset**: [Name, DOI, access protocol]
- **Secondary Datasets**: [If applicable]
- **Data Collection Period**: [Dates]
- **Sample Size**: [n = ?, with justification]
- **Inclusion/Exclusion Criteria**: [Clear criteria]

### Analysis Code
- **Primary Language**: [Python, R, MATLAB, Julia, etc.]
- **Key Libraries**: [numpy, pandas, scikit-learn, etc.]
- **Repository**: [GitHub URL]
- **License**: [MIT, GPL, Apache 2.0, etc.]

### Computational Requirements
- **Hardware**: [CPU, GPU, memory requirements]
- **Runtime**: [Expected computation time]
- **Random Seed**: [For reproducibility]

## Review and Revision Process

### Internal Review
- **Reviewers**: [List internal reviewers or review process]
- **Review Criteria**: [Checklist or rubric]
- **Timeline**: [Deadlines]

### Peer Review
- **Submission Date**: [Target or actual]
- **Review Rounds**: [Expected number]
- **Revision Strategy**: [Point-by-point responses, tracked changes, etc.]

## Special Instructions for AI Assistant

### Do's
- Use the terminology and conventions defined above
- Follow the specified reporting standards strictly
- Include all required sections in the specified order
- Verify all citations match the specified style
- Check reproducibility requirements are met
- Ensure statistical reporting meets field standards

### Don'ts
- Don't use alternative terminology for key concepts
- Don't omit required sections
- Don't violate page/word limits
- Don't fabricate any data, statistics, or citations
- Don't skip ethics statements or data availability

### When in Doubt
- Flag ambiguities for user clarification
- Suggest consulting the venue's author guidelines
- Recommend field-specific experts for review
- Note when additional information is needed

## Project-Specific Notes

[Add any additional project-specific considerations]

- Special requirements:
- Collaborator preferences:
- Known challenges:
- Timeline considerations:

---

**Last Updated**: [Date]
**Project Lead**: [Your name/contact]
```

## Field-Specific Templates

Below are example `.github/copilot-instructions.md` configurations for common scientific fields. Copy the relevant section and customize for your project.

### Medical/Health Sciences Example

```markdown
## Field-Specific Requirements

### Reporting Standards
- [x] CONSORT (randomized controlled trial)
- [ ] PRISMA
- [ ] STROBE

### Citation Style
- **Primary Style**: Vancouver (numbered citations)
- **Reference Manager**: BibTeX with numeric keys
- **Inline Citations**: [1,2,3]

### Statistical Requirements
- Report odds ratios with 95% CI
- P-values with multiple testing correction (Bonferroni)
- Intention-to-treat analysis required
- Power analysis for sample size justification

### Ethics and Compliance
- [x] IRB approval number: IRB-2024-12345
- [x] Clinical trial registration: NCT05123456
- [x] HIPAA compliance verified
- [x] Informed consent forms approved
```

### Computer Science/AI Example

```markdown
## Field-Specific Requirements

### Reporting Standards
- [x] ACM Artifact Evaluation
- Algorithm pseudocode required
- Complexity analysis required

### Citation Style
- **Primary Style**: IEEE (numbered, bracketed)
- **Reference Manager**: BibTeX with \cite{}
- **Inline Citations**: [1]

### Reproducibility Standards
- [x] Code repository: GitHub with MIT license
- [x] Docker container: tensorflow/tensorflow:2.14.0-gpu
- [x] Random seeds: 42 (training), 123 (validation)
- [x] Hardware: NVIDIA A100 40GB GPU
- [x] Requirements.txt with pinned versions
- [x] Datasets: ImageNet (ILSVRC2012), COCO 2017

### Open Science Practices
- [x] Preprint: arXiv
- [x] Open Code: GitHub with DOI via Zenodo
- [x] Open Data: Links to public datasets
```

### Psychology/Social Sciences Example

```markdown
## Field-Specific Requirements

### Reporting Standards
- [x] APA 7th edition
- [x] STROBE (observational study)
- Power analysis reported

### Citation Style
- **Primary Style**: APA 7th
- **Reference Manager**: BibTeX with apalike
- **Inline Citations**: (Author, Year)

### Statistical Requirements
- Report effect sizes: Cohen's d for t-tests, η² for ANOVA
- 95% confidence intervals for all effects
- P-values with exact values (not p < .05)
- Assumption checking reported (normality, homogeneity)
- Post-hoc tests with correction (Tukey HSD)

### Ethics and Compliance
- [x] IRB approval: 2024-PSY-089
- [x] Informed consent procedure described
- [x] Debriefing protocol included
- [x] Preregistration: OSF (https://osf.io/xxxxx)

### Open Science Practices
- [x] Preregistered hypotheses and analysis plan
- [x] Open data: OSF repository
- [x] Open materials: Survey instruments, stimuli
- [x] Analysis scripts: R with package versions
```

### Natural Sciences (Biology/Chemistry/Physics) Example

```markdown
## Field-Specific Requirements

### Reporting Standards
- Laboratory protocols detailed in Methods
- Reagent catalog numbers and suppliers
- Equipment specifications

### Citation Style
- **Primary Style**: Nature style (numbered, no brackets)
- **Reference Manager**: BibTeX with naturemag.bst
- **Inline Citations**: Superscript numbers

### Reproducibility Standards
- [x] Detailed protocols in Methods
- [x] Reagent information: catalog numbers, suppliers, lot numbers
- [x] Equipment: manufacturer, model, calibration dates
- [x] Software: version numbers for analysis tools
- [x] Raw data: Deposited in [Dryad/Zenodo/FigShare]

### Specialized Requirements
- Chemical structures: ChemDraw format
- Spectroscopic data: deposited in appropriate database
- Genetic sequences: GenBank accession numbers
- Protein structures: PDB codes
```

### Engineering Example

```markdown
## Field-Specific Requirements

### Reporting Standards
- Technical specifications with tolerances
- Performance metrics with uncertainty quantification
- Comparison with existing solutions

### Citation Style
- **Primary Style**: IEEE
- **Reference Manager**: BibTeX with IEEEtran.bst
- **Inline Citations**: [1]

### Reproducibility Standards
- [x] CAD files for physical designs
- [x] Simulation parameters and mesh details
- [x] Material specifications and suppliers
- [x] Measurement equipment specifications
- [x] Uncertainty analysis included

### Specialized Requirements
- Patent considerations: prior art search conducted
- Standards compliance: [ISO, ASME, etc.]
- Safety analysis: failure modes considered
- Cost analysis: materials and manufacturing
```

## Cross-Disciplinary Papers

For papers spanning multiple disciplines, your `.github/copilot-instructions.md` should:

1. **Identify all relevant fields**:
   ```markdown
   ## Field-Specific Requirements
   
   This is a cross-disciplinary paper spanning:
   - **Primary Field**: Computational Biology
   - **Secondary Fields**: Machine Learning, Molecular Biology
   ```

2. **Specify which standards apply from each field**:
   ```markdown
   ### Reporting Standards (Multi-Field)
   - From Biology: Include GenBank accession numbers, species nomenclature
   - From Computer Science: Include algorithm complexity, code repository
   - From Statistics: Report effect sizes, confidence intervals, multiple testing correction
   ```

3. **Define terminology bridges**:
   ```markdown
   ### Cross-Disciplinary Terminology
   - Use consistent terminology across fields
   - Define specialized terms from each field on first use
   - Create glossary if needed for non-specialist readers
   ```

4. **Specify target audience**:
   ```markdown
   ### Target Audience
   - **Primary**: Computational biologists
   - **Secondary**: Machine learning researchers, molecular biologists
   - **Writing Level**: Assume advanced knowledge in one field, provide context for others
   ```

## Using the Prompts with Your Project

Once you've created `.github/copilot-instructions.md` in your workspace:

### 1. Activate Researcher Mode
```
@workspace /chatmode Researcher
```

### 2. Start Literature Search
```
Using research-papers.prompt.md, help me find literature on [topic]
```

### 3. Write Your Manuscript
```
Using write.prompt.md, create the Methods section for my paper
```

### 4. Get Peer Review
```
Using review.prompt.md, review my manuscript draft
```

### 5. Revise Based on Feedback
```
Using rewrite.prompt.md, revise the manuscript based on reviewer comments
```

The prompts will automatically incorporate your project-specific requirements from `.github/copilot-instructions.md`.

## Examples

### Starting a New Medical Paper

```bash
# 1. Create project structure
mkdir my-clinical-trial
cd my-clinical-trial
mkdir -p .github research paper/{figures,} review

# 2. Create copilot-instructions.md from medical template
# (copy and customize medical example above)

# 3. Activate Researcher mode in VS Code
# @workspace /chatmode Researcher

# 4. Start literature search
# "Using research-papers.prompt.md, help me find randomized controlled trials on [topic]"
```

### Starting a Cross-Disciplinary AI+Biology Paper

```markdown
# .github/copilot-instructions.md

## Project Overview
- **Paper Title**: Deep Learning for Protein Structure Prediction
- **Field**: Computational Biology (AI + Structural Biology)
- **Target Venue**: Nature Methods
- **Paper Type**: Original Research

## Field-Specific Requirements

### Reporting Standards (Multi-Field)
- [x] Algorithm pseudocode (from CS)
- [x] Model architecture diagram (from CS)
- [x] Protein structure deposition: PDB codes (from Biology)
- [x] Benchmark datasets: CASP14, CAMEO (from Biology)
- [x] Code and trained models: GitHub + Zenodo (from CS)
- [x] Statistical validation: cross-validation, bootstrapping (from Statistics)

### Target Audience
- **Primary**: Computational biologists, structural biologists
- **Secondary**: Machine learning researchers
- **Writing Level**: Advanced biology, intermediate ML (explain architectures)

### Cross-Disciplinary Terminology
- "Residue" (biology) = "token" (ML): Use "residue" consistently
- "Feature" (ML) → "structural property" when referring to biology
- Define all ML terms (convolution, attention, transformer) on first use
- Define all biology terms (RMSD, TM-score, secondary structure) on first use
```

## Best Practices

1. **Keep it updated**: Revise `.github/copilot-instructions.md` as your paper evolves
2. **Be specific**: The more detailed your requirements, the better the AI assistance
3. **Use checklists**: Makes it easy to track completion
4. **Reference standards**: Link to reporting guideline websites
5. **Version control**: Commit changes to `.github/copilot-instructions.md` with your paper
6. **Collaborate**: Share this file with co-authors for consistency

## Troubleshooting

### Prompts not following my field requirements
- Check that `.github/copilot-instructions.md` is in your workspace root
- Verify the file is properly formatted Markdown
- Try explicitly mentioning: "Following the requirements in .github/copilot-instructions.md, ..."

### Need field-specific help not covered here
- Add your requirements to `.github/copilot-instructions.md`
- Ask: "What additional field-specific requirements should I include for [field]?"
- Consult your target venue's author guidelines

### Cross-disciplinary paper unclear
- List all relevant fields explicitly
- Specify which standards from each field apply
- Define your target audience clearly
- Create terminology mapping

## Additional Resources

- [EQUATOR Network](https://www.equator-network.org/) - Reporting guidelines database
- [Top Factor](https://www.topfactor.org/) - Transparency and Openness Promotion guidelines
- [Center for Open Science](https://www.cos.io/) - Preregistration and open science tools
- [FAIRsharing](https://fairsharing.org/) - Standards, databases, and policies
- [The Turing Way](https://the-turing-way.netlify.app/) - Reproducible research handbook

---

**Questions?** Open an issue in the research_prompts repository or consult the individual prompt files for detailed guidance.

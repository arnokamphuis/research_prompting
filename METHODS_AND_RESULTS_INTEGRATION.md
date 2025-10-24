# Methods and Results Integration Update

## Overview

This update adds comprehensive support for documenting and integrating **your own experimental research** into the manuscript writing workflow. Previously, the prompts focused on synthesizing existing literature, but researchers conducting their own experiments needed a structured way to document methods, results, and findings.

## What's New

### New Prompt: `document_research.prompt.md`

A comprehensive prompt for documenting your own experimental work throughout the research process.

**Purpose**: Create structured documentation of methods, protocols, data, results, and findings in a format that feeds directly into manuscript writing.

**When to use**: Throughout your research process (not just at the end). Document as you go.

**Key Features**:
- Templates for methods documentation (protocol, participants, materials, procedures, analysis plan)
- Templates for results documentation (statistics, figures, tables, data files)
- Organized folder structure (`/methods_and_results/`)
- Integration with outline, write, supplementary, and presubmission_check prompts
- Support for open science practices (data sharing, code availability)
- Contemporaneous documentation (reduces errors from retrospective recall)

### Updated Prompts: Integration with `/methods_and_results` Folder

Four existing prompts now automatically integrate with documented research:

#### 1. `outline.prompt.md`
**New capability**: Checks for `/methods_and_results` folder and uses documented research to plan manuscript structure

**Integration**:
- Reads research overview from `README.md`
- Inventories documented methods, results, figures, tables
- Plans manuscript sections around actual documented research
- Identifies gaps in documentation
- Cross-references specific documentation files in outline

**Why it matters**: Ensures outline is based on actual research, not hypothetical content.

#### 2. `write.prompt.md`
**New capability**: Pulls methods and results directly from documented research when writing manuscript

**Integration**:
- Incorporates documented protocols into Methods section
- Uses documented statistics for Results section
- References documented figures and tables
- Ensures manuscript accuracy matches actual research
- Prevents fabrication or embellishment of results

**Why it matters**: Guarantees manuscript represents actual research work accurately.

#### 3. `supplementary.prompt.md`
**New capability**: Uses documented research as primary source for supplementary materials

**Integration**:
- Pulls extended protocols from documented methods
- Includes complete statistical outputs from documented analyses
- References documented data files and code
- Uses documented figures not included in main manuscript

**Why it matters**: Simplifies supplementary material creation and ensures reproducibility.

#### 4. `presubmission_check.prompt.md`
**New capability**: Verifies manuscript accuracy against documented research

**Integration**:
- Compares manuscript statistics to documented results line-by-line
- Verifies Methods section matches documented protocols
- Checks sample sizes, demographics, procedures for consistency
- Flags discrepancies as HIGH PRIORITY issues
- Ensures figures/tables match documented data

**Why it matters**: Prevents embarrassing errors where published results don't match actual data.

## Directory Structure

When you use `document_research.prompt.md`, it creates this structure:

```
methods_and_results/
├── README.md                           # Research project overview
├── methods/
│   ├── protocol.md                     # Detailed experimental protocol
│   ├── participants.md                 # Sample/participant characteristics
│   ├── materials.md                    # Equipment, reagents, instruments
│   ├── procedures.md                   # Data collection procedures
│   ├── analysis_plan.md                # Statistical/computational analysis plan
│   ├── preregistration.md              # Pre-registered hypotheses (if applicable)
│   └── ethics/
│       ├── irb_approval.pdf            # Ethics approval documents
│       ├── consent_template.md         # Informed consent template
│       └── data_protection.md          # Data privacy compliance
├── results/
│   ├── summary.md                      # High-level findings overview
│   ├── data/
│   │   ├── raw/                        # Raw data files
│   │   ├── processed/                  # Cleaned/processed data
│   │   ├── data_dictionary.md          # Variable descriptions
│   │   └── data_sources.md             # Data provenance
│   ├── statistics/
│   │   ├── descriptive_stats.md        # Descriptive statistics
│   │   ├── inferential_stats.md        # Hypothesis testing results
│   │   ├── analysis_output/            # Full statistical outputs
│   │   └── code/                       # Analysis scripts
│   ├── figures/
│   │   ├── figure1_draft.pdf           # Draft figures
│   │   ├── figure_specs.md             # Figure specifications
│   │   └── generation_code/            # Code to generate figures
│   └── tables/
│       ├── table1_demographics.csv     # Draft tables
│       └── table_notes.md              # Notes and formatting
├── unexpected_findings.md              # Unexpected or null results
├── limitations.md                      # Known limitations
└── lab_notebook/                       # Optional: chronological notes
```

## Workflow Integration

### Before This Update
```
Literature search → Outline → Write manuscript → Submit
(Gap: No structured way to document YOUR OWN research)
```

### After This Update
```
Literature search (research-papers)
         ↓
Document your research (document_research) ← Ongoing throughout research
         ↓
Outline manuscript (outline) ← Automatically checks /methods_and_results
         ↓
Write manuscript (write) ← Pulls from /methods_and_results
         ↓
Supplementary materials (supplementary) ← Uses /methods_and_results
         ↓
Pre-submission check (presubmission_check) ← Verifies vs /methods_and_results
         ↓
Submit
```

## Key Benefits

### 1. Accuracy
**Problem solved**: Manuscript statistics or methods don't match actual data/procedures  
**How**: Pre-submission check verifies manuscript against documented research line-by-line

### 2. Reproducibility
**Problem solved**: Methods section lacks detail for replication  
**How**: Structured templates ensure complete protocol documentation

### 3. Efficiency
**Problem solved**: Writing manuscript from memory is slow and error-prone  
**How**: Write prompt pulls directly from documentation; no need to reconstruct from memory

### 4. Traceability
**Problem solved**: Can't remember exact parameters, sample sizes, or statistical results  
**How**: Everything documented contemporaneously in structured format

### 5. Open Science
**Problem solved**: Data/code sharing requirements hard to meet  
**How**: Documentation includes data files, code, data dictionaries by default

### 6. Quality
**Problem solved**: Important findings or limitations forgotten during writing  
**How**: Unexpected findings and limitations documented separately and incorporated

## Use Cases

### Use Case 1: Experimental Psychology Study
```
Throughout research:
- Document protocol (experimental procedure)
- Document participants (recruitment, demographics)
- Document results (statistics, effect sizes)

When writing manuscript:
- outline.prompt.md plans structure around documented N=150 study
- write.prompt.md pulls documented statistics: t(148) = 3.45, p = 0.001, d = 0.58
- presubmission_check.prompt.md verifies manuscript stats match documented results
```

### Use Case 2: Computational Research
```
Throughout research:
- Document model architecture
- Document hyperparameters and training procedure
- Document performance metrics on test sets

When writing manuscript:
- write.prompt.md incorporates documented model specifications
- supplementary.prompt.md includes documented code and environment specs
- presubmission_check.prompt.md verifies reported performance matches documented results
```

### Use Case 3: Clinical Trial
```
Throughout research:
- Document trial protocol and registration
- Document participant flow (CONSORT)
- Document primary and secondary outcomes

When writing manuscript:
- outline.prompt.md structures around documented trial design
- write.prompt.md uses documented participant flow for Methods
- presubmission_check.prompt.md verifies consistency with trial registration
```

## Example Verification

### What presubmission_check.prompt.md Now Catches:

**Critical Discrepancy Example**:
```
CRITICAL: Results Mismatch
- Manuscript states: "t(127) = 3.45, p = 0.001, d = 0.62"
- Documented in /methods_and_results/results/statistics/inferential_stats.md:
  "t(125) = 3.41, p = 0.001, d = 0.61"
- Issue: Degrees of freedom differ (127 vs 125), test statistic differs
- Action: Verify correct analysis and update manuscript
```

**Critical Methods Discrepancy**:
```
CRITICAL: Sample Size Inconsistency
- Manuscript states: "Participants (N = 130) were recruited..."
- Documented in /methods_and_results/methods/participants.md: "Final analyzed: N = 127"
- Issue: Sample size inconsistent (130 enrolled vs. 127 analyzed)
- Action: Clarify enrolled vs. analyzed and ensure consistency throughout
```

## Documentation Philosophy

The `/methods_and_results` approach follows these principles:

1. **Contemporaneous**: Document as you go, not months later
2. **Detailed**: Enough detail for someone else to reproduce
3. **Honest**: Include null results, unexpected findings, limitations
4. **Organized**: Consistent structure and naming
5. **Version-controlled**: Track changes over time (markdown files work with git)
6. **Separate**: Raw research artifacts separate from manuscript prose

## Files Modified

### New Files Created
1. `prompts/document_research.prompt.md` - New comprehensive documentation prompt

### Files Updated
1. `prompts/outline.prompt.md` - Added `/methods_and_results` integration section
2. `prompts/write.prompt.md` - Added `/methods_and_results` integration section
3. `prompts/supplementary.prompt.md` - Added `/methods_and_results` integration section
4. `prompts/presubmission_check.prompt.md` - Added verification checks against documented research
5. `README.md` - Added document_research to workflow, updated Phase 1, updated diagrams
6. `QUICK_START.md` - Added research documentation steps, updated tips and patterns
7. `METHODS_AND_RESULTS_INTEGRATION.md` - This file (comprehensive overview of update)

## Migration Guide

### For Existing Projects

If you already have a manuscript in progress:

**Option 1: Retroactive Documentation** (Recommended if time permits)
```
1. Create /methods_and_results/ structure
2. Use document_research.prompt.md to structure your existing notes/protocols
3. Organize existing data files into /methods_and_results/results/data/
4. Document statistics from your analysis outputs
5. Run presubmission_check.prompt.md to verify manuscript vs. documentation
```

**Option 2: Partial Documentation** (Minimum for verification)
```
1. Create /methods_and_results/results/statistics/inferential_stats.md
2. Document all statistical results reported in manuscript
3. Run presubmission_check.prompt.md to verify consistency
```

**Option 3: Skip for This Manuscript**
```
- Continue without /methods_and_results for current project
- Start using it for next project from the beginning
```

### For New Projects

**Recommended workflow**:
```
1. Before starting experiments: Use document_research.prompt.md to create protocol.md
2. During recruitment: Document participants in participants.md
3. As data comes in: Update results/summary.md
4. After analysis: Document statistics in inferential_stats.md
5. When writing: All other prompts automatically use this documentation
```

## FAQ

### Q: Is `/methods_and_results` required?
**A**: No. All prompts work with or without it. If the folder doesn't exist, prompts work normally. If it exists, they automatically integrate with it.

### Q: Can I use this for literature reviews (no experiments)?
**A**: The `/methods_and_results` folder is designed for empirical research. For pure literature reviews, just use `research-papers.prompt.md` without `document_research.prompt.md`.

### Q: What if I have data in other formats (SPSS, proprietary)?
**A**: `document_research.prompt.md` includes templates for documenting what you have and where it is. You can reference proprietary files and include exports in open formats (CSV) for sharing.

### Q: How does this relate to open science?
**A**: The structure aligns with open science practices: data sharing, code sharing, pre-registration, complete methods documentation. The folder can be shared as-is or used to prepare repository uploads.

### Q: Does this replace my lab notebook?
**A**: It complements it. Lab notebooks are chronological; `/methods_and_results` is organized for manuscript writing. You can optionally include `/methods_and_results/lab_notebook/` for chronological notes.

### Q: What about sensitive data (medical, personal)?
**A**: Document metadata and structure. Include de-identified data where possible. Document access procedures for restricted data in `data_sources.md`.

---

## Summary

This update fills a critical gap in the research writing workflow by providing structured documentation for your own experimental work. The integration is seamless: if you document your research in `/methods_and_results`, downstream prompts automatically use it. If you don't, prompts work normally.

The result is more accurate manuscripts, better reproducibility, and significantly less cognitive load during writing.

**Now you can document research as it happens and let the prompts do the heavy lifting of incorporating it into your manuscript.**

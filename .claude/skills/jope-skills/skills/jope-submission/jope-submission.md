---
name: jope-submission
description: Use when running the final pre-submission preflight for the Journal of Population Economics (JOPE) on Springer's submission system — 150-word non-technical abstract, title page, editable source files, declarations, data-availability statement, and collection selection. Final checks; it does not draft content.
---

# Submission Preflight (jope-submission)

## When to trigger

- "Submitting tomorrow" — last check before pressing submit on Editorial Manager
- Unsure which files and metadata the Springer system expects
- Confirming the abstract, title page, and declarations meet the journal's rules
- Checking the replication package and data-availability statement

## Process facts (verified 2026-10-03 from official-page search snippets and Editor-in-Chief reports; the Springer and GLO pages were not directly readable in this refresh — re-confirm volatile items on the live page)

- JOPE is published by **Springer** and submitted through **Editorial Manager** (editorialmanager.com/jope).
  Editor-in-Chief **Klaus F. Zimmermann**; Managing Editor **Madeline Zavodny**; editorial office at
  **POP at UNU-MERIT, Maastricht** (JOPE-Office@glabor.org).
- **Abstract: at most 150 words, non-technical, stating the innovation and contribution.** Third-party
  template sites show other limits; the Springer guideline snippet says 150. Count it.
- **Title page:** concise, informative title; author names and affiliations; corresponding author's
  active e-mail; 16-digit ORCID where available. Keywords and JEL codes are expected on the title page.
- **Editable source files are required at every submission and revision** (.docx or LaTeX); a
  PDF-only submission is not considered for review. Figures as separate files; tables editable.
- **Declarations** section (Springer standard): funding, competing interests, ethics approval and
  consent where applicable, **data availability**, author contributions, and any **generative-AI use in
  writing** (disclosed in the text; AI tools cannot be authors).
- **Review model:** not verified in this refresh — read the live "Peer review" section and anonymize
  only if it says to.
- **Fee:** no submission fee located; open-access charge applies only if Open Choice is selected after
  acceptance.
- **Language:** consistent American or British English. **References:** Springer author-year style
  for this journal; confirm the exact style file on the live guidelines.

## Preflight checklist

### Abstract, title page, metadata
- [ ] Abstract ≤ **150 words**, non-technical, states innovation and contribution, no estimator names
- [ ] Title page: title, authors, affiliations, corresponding e-mail, ORCIDs, keywords, JEL codes
- [ ] Special collection named in the cover letter and selected as the article type, if applicable

### Files
- [ ] Editable source (.docx or LaTeX) uploaded — not PDF only
- [ ] Figures as separate vector/TIFF files; tables editable; captions in the text
- [ ] Electronic supplementary material (online appendix) attached and referenced from the text
- [ ] Tables and figures numbered, called out in order, with self-contained notes

### Declarations and policy
- [ ] Funding, competing interests, ethics/consent statements written
- [ ] **Data-availability statement** names a repository or explains the restriction and access path
- [ ] AI-use disclosure included if any tool assisted the writing
- [ ] Confirmed not under review elsewhere; all authors approved; preprint noted if posted
- [ ] Anonymization matches the live peer-review instruction

### Replication and content sanity
- [ ] Replication package submission-ready (master script + README + pinned versions + seeds)
- [ ] Restricted-data access path and synthetic extract documented
- [ ] Headline effect stated in demographic units with the control mean (see jope-contribution-framing)
- [ ] Identification diagnostics complete (see jope-identification-strategy, jope-data-analysis)
- [ ] Tempo vs quantum, flow vs stock stated where relevant
- [ ] No over-claiming beyond what the design supports

## Desk-screen failure modes (what gets a JOPE paper bounced before review)

| Failure at the desk                                              | Preflight catch                                                    |
|------------------------------------------------------------------|--------------------------------------------------------------------|
| Abstract over 150 words or technical                              | Hard-count words; strip estimator names                           |
| No economics-demography link — a labor or health paper on a demographic sample | Confirm the demographic margin is the mechanism (jope-topic-selection) |
| PDF-only or missing editable source files                        | Upload .docx / LaTeX source                                       |
| Causal claim on OLS + controls with demographic selection undefended | Identification diagnostics complete before submitting           |
| Data-availability statement missing or "on request"               | Write the statement with repository or access path                 |
| Closest recent JOPE paper on the same reform not cited           | Search JOPE back issues (jope-literature-positioning)             |

## Worked preflight vignette (illustrative)

Hypothetical: a birth-date RDD on a child-benefit reform, draft abstract at 210 words, four figures,
register data under remote access.

- **Preflight hits:** abstract cut to 142 non-technical words; figures re-exported as PDF vector files;
  the data-availability statement rewritten to name the statistics office, the access route, and the
  deposited code and synthetic extract; the manuscript's blinding checked against the live peer-review
  section.
- **Go/no-go:** replication package regenerates all exhibits from `run_all`; declarations complete;
  density test and donut RD in the ESM → cleared to submit.

## Anti-patterns

- Submitting a technical 250-word abstract because a template site said 250
- PDF-only upload
- "Data available on request" as the data-availability statement
- Anonymizing, or not, without checking the live instruction
- Forgetting the keywords and JEL codes on the title page

## Output format

```
【Abstract】≤150 words, non-technical, contribution stated? [Y/N + count]
【Title page】title / affiliations / e-mail / ORCID / keywords / JEL? [Y/N]
【Source files】editable .docx or LaTeX + separate figures? [Y/N]
【Declarations】funding / COI / ethics / data availability / AI use? [Y/N]
【Review model】live instruction read; blinding matches? [Y/N]
【Collection】regular / named collection
【Replication package】ready; restricted-data path documented? [Y/N]
【Next step】await decision → jope-rebuttal on R&R
```

## Supplementary resources

- [`../../resources/external_tools.md`](../../resources/external_tools.md) — data sources and Stata/R/Python packages for population-economics empirical work
- [`../../resources/official-source-map.md`](../../resources/official-source-map.md) — official JOPE URLs behind every fact in this pack, with verification status

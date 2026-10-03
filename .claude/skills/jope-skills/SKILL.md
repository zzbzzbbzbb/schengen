---
name: jope-skills
description: "Journal of Population Economics submission toolkit. Use when deciding which jope-* sub-skill to invoke next, or when sequencing manuscript work from topic selection through rebuttal for a Journal of Population Economics (JOPE) submission. Routes — it does not replace — the specialized skills."
---

# JOPE Workflow Router (jope-workflow)

## Overview

This is the router. It does not replace any specialized skill. It tells you **which jope-* skill to use at the current stage** of a manuscript aimed at the *Journal of Population Economics*.

Default assumption: unless the user says otherwise, treat the target as JOPE — the **leading field journal
in population economics**, founded in **1987** by **Klaus F. Zimmermann**, published by **Springer** (hybrid
"Open Choice" model) in cooperation with **POP at UNU-MERIT** and the **Global Labor Organization (GLO)**, and
historically the official journal of the European Society for Population Economics. Editor-in-Chief:
**Klaus F. Zimmermann**; Managing Editor: **Madeline Zavodny**. Scope: the **broadly defined relationships
between economic and demographic problems** — household formation, fertility, education, labor supply,
migration, ageing and pensions, health, gender, inequality, and population-driven growth.

It is selective and fast at the desk: a **desk-rejection policy since 2013**, acceptance rates reported by the
Editor-in-Chief between **4.9% (2019)** and **7% (2021)**, and average first decisions of **23-30 days**
(2019-2021). The **abstract is capped at 150 words** and must be **non-technical**, stating the paper's
innovation and contribution. Distinctive features: **special collections** with fast handling, the annual
**GLO-JOPE Global Conference**, and the **Kuznets Prize** for the best article published in the journal.

Volatile items not verified in the latest refresh (review anonymity model, any length cap, APC level,
mandatory replication deposit) are flagged in `resources/official-source-map.md`. Re-check them on the
live Springer pages before giving submission-ready advice.

## When to trigger

- The user asks "what should I do next?"
- The user hands over a draft and needs the current bottleneck diagnosed
- Work is ping-ponging between empirics, framing, writing, and response letters
- A JOPE decision letter arrived and the user needs to switch into revision mode
- The user is deciding between a regular submission and an open special collection

## Routing table

| Current symptom                                                         | Next skill                         |
|-------------------------------------------------------------------------|------------------------------------|
| Idea feels small / not clearly an economics-demography question         | `jope-topic-selection`             |
| Contribution relative to the population-economics literature is fuzzy    | `jope-literature-positioning`      |
| The demographic stakes or the economic mechanism are undersold           | `jope-contribution-framing`        |
| Empirics rest on OLS + controls; selection into births/migration/marriage undefended | `jope-identification-strategy` |
| Weights, cohorts, attrition, demographic measurement, or inference shaky | `jope-data-analysis`               |
| Tables dense; age/cohort/event-time patterns not shown as figures        | `jope-tables-figures`              |
| Abstract over 150 words or technical; intro buries the question         | `jope-writing-style`               |
| Need the data/code package and a data-availability statement            | `jope-replication-and-data-policy` |
| Unsure how JOPE review works (desk screen, special collections, timing)  | `jope-review-process`              |
| Ready to submit on the Springer system; need a preflight checklist       | `jope-submission`                  |
| Received an R&R; need a response-letter strategy                        | `jope-rebuttal`                    |

## Default order

1. `jope-topic-selection` — lock a first-order economics-demography question
2. `jope-literature-positioning` — stake the contribution against the population-economics frontier
3. `jope-contribution-framing` — make the demographic and economic takeaway explicit
4. `jope-identification-strategy` — make the causal design credible against demographic selection
5. `jope-data-analysis` — weights, cohorts, measurement, attrition, inference
6. `jope-tables-figures` — age profiles, event-time plots, cohort figures
7. `jope-writing-style` — polish prose (150-word non-technical abstract and intro last)
8. `jope-replication-and-data-policy` — package and data-availability statement
9. `jope-review-process` — regular vs special collection; understand the desk screen
10. `jope-submission` — Springer preflight
11. `jope-rebuttal` — after the R&R

> JOPE desk-screens quickly. If the paper fits an **open special collection** (e.g., abortion, COVID-19 and
> diseases, lifecycle fertility models, sexual and domestic violence, sexuality incl. LGBT issues,
> statistics and measurement of population economics), route to `jope-review-process` early — collection
> papers receive particular interest and speedy handling.

## Worked routing example (illustrative)

A user arrives with administrative register data on a parental-leave reform, a clean event study of
mothers' earnings around first birth, and an unfocused draft.

- The design is sound (a reform cutoff by child birth date plus an event study), so **skip ahead** of
  `jope-identification-strategy` except to confirm birth-timing manipulation around the cutoff.
- The draft reports coefficients but never says what it teaches about **fertility, household
  specialization, or gender gaps** → the live bottleneck is `jope-contribution-framing`, then
  `jope-literature-positioning` against the child-penalty and family-policy literature.
- The abstract is 240 words and full of estimator names → `jope-writing-style` must cut it to **150
  non-technical words** before submission.
- Only after framing and identification settle should `jope-tables-figures` polish the event-time figure.

## Stage-to-symptom quick map

| Stage symptom                                    | Route to                          |
|--------------------------------------------------|-----------------------------------|
| "Is this population economics or just labor?"    | `jope-topic-selection`            |
| "Results exist but the demographic lesson is fuzzy" | `jope-contribution-framing`    |
| "A referee will say births/migrants are selected" | `jope-identification-strategy`   |
| "An R&R letter just arrived"                     | `jope-rebuttal`                   |
| "Does this fit an open collection?"              | `jope-review-process`             |

## Router output

```
【Current stage】topic / framing / identification / analysis / exhibits / writing / replication / review / submission / rebuttal
【Live bottleneck】one sentence
【Route now to】jope-<skill>
【Route candidate】regular submission / special collection (+ which) + why
【Abstract ≤150 words, non-technical?】[Y/N]
```

## Anti-patterns

- **Do not** skip `jope-contribution-framing` — JOPE editors desk-screen on the economics-demography link first
- **Do not** let `jope-tables-figures` polish exhibits while selection into fertility, marriage, or migration is undefended
- **Do not** submit a long technical abstract — the 150-word non-technical cap is a desk-screen item
- **Do not** treat a generic labor or health paper as population economics because the sample is defined by age or sex


## Sub-skill index

When this router names a sub-skill, read its file below. All linked resources are bundled in this folder.

| Sub-skill | File | Use when |
|---|---|---|
| `jope-contribution-framing` | [skills/jope-contribution-framing/jope-contribution-framing.md](skills/jope-contribution-framing/jope-contribution-framing.md) | Use when sharpening the economics-demography takeaway of a Journal of Population Economics (JOPE) manuscript — the explicit "what this teaches about how economic forces and population outcomes interact" claim an editor can restate in one sentence. Frames the contribution; it is not a writing-polish pass. |
| `jope-data-analysis` | [skills/jope-data-analysis/jope-data-analysis.md](skills/jope-data-analysis/jope-data-analysis.md) | Use when estimation, weighting, cohort construction, demographic measurement, attrition, or inference choices need to meet Journal of Population Economics (JOPE) empirical norms — survey and register panels, census microdata, fertility, mortality, and migration measures. Covers the analysis itself, not the identifying design. |
| `jope-identification-strategy` | [skills/jope-identification-strategy/jope-identification-strategy.md](skills/jope-identification-strategy/jope-identification-strategy.md) | Use when the causal identification strategy is the bottleneck for a Journal of Population Economics (JOPE) manuscript — selection into births, marriage, migration, or survival; policy-reform DID, birth-date RDD, twins/sex-composition IV, shift-share migration designs. Stress-tests the design before tables are drafted. |
| `jope-literature-positioning` | [skills/jope-literature-positioning/jope-literature-positioning.md](skills/jope-literature-positioning/jope-literature-positioning.md) | Use when staking a manuscript's contribution against the population-economics literature for the Journal of Population Economics (JOPE). Positions the paper at the frontier; it does not write a standalone survey. |
| `jope-rebuttal` | [skills/jope-rebuttal/jope-rebuttal.md](skills/jope-rebuttal/jope-rebuttal.md) | Use when responding to a Journal of Population Economics (JOPE) decision — drafting the response letter and revision plan for a major or minor revision. Strategy for the response; it does not rewrite the manuscript. |
| `jope-replication-and-data-policy` | [skills/jope-replication-and-data-policy/jope-replication-and-data-policy.md](skills/jope-replication-and-data-policy/jope-replication-and-data-policy.md) | Use when assembling the data-availability statement and the data/code package for a Journal of Population Economics (JOPE) submission or accepted paper — Springer Nature research-data policy, restricted register and survey data, repository choice. Builds the package; it does not run the analysis. |
| `jope-review-process` | [skills/jope-review-process/jope-review-process.md](skills/jope-review-process/jope-review-process.md) | Use when choosing between a regular submission and a special collection, or understanding how review works at the Journal of Population Economics (JOPE) — desk rejection, fast first decisions, acceptance rates, editor assignment, and the GLO-JOPE conference. Explains the pipeline; it is not the final preflight. |
| `jope-submission` | [skills/jope-submission/jope-submission.md](skills/jope-submission/jope-submission.md) | Use when running the final pre-submission preflight for the Journal of Population Economics (JOPE) on Springer's submission system — 150-word non-technical abstract, title page, editable source files, declarations, data-availability statement, and collection selection. Final checks; it does not draft content. |
| `jope-tables-figures` | [skills/jope-tables-figures/jope-tables-figures.md](skills/jope-tables-figures/jope-tables-figures.md) | Use when designing the main exhibits for a Journal of Population Economics (JOPE) manuscript — age and cohort profiles, event-time plots around births or migration, Lexis-style and population figures, with self-contained notes. Shapes exhibits; it does not run the estimation. |
| `jope-topic-selection` | [skills/jope-topic-selection/jope-topic-selection.md](skills/jope-topic-selection/jope-topic-selection.md) | Use when judging whether a research question fits the Journal of Population Economics (JOPE) — a first-order question about the relationship between economic and demographic problems. Tests topic fit before identification or drafting begins. |
| `jope-writing-style` | [skills/jope-writing-style/jope-writing-style.md](skills/jope-writing-style/jope-writing-style.md) | Use when polishing prose for a Journal of Population Economics (JOPE) manuscript so the economics-demography question, answer, and policy stakes land for a broad population-economics audience, under a 150-word non-technical abstract cap. A late-stage polish; do not rewrite the intro before identification and framing are settled. |

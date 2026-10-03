---
name: jope-tables-figures
description: Use when designing the main exhibits for a Journal of Population Economics (JOPE) manuscript — age and cohort profiles, event-time plots around births or migration, Lexis-style and population figures, with self-contained notes. Shapes exhibits; it does not run the estimation.
---

# Tables & Figures (jope-tables-figures)

## When to trigger

- The main result is a nine-column table no reader can parse
- A birth-date discontinuity, event-time trajectory, or age profile would land harder as a figure
- Heterogeneity by parity, gender, or cohort is buried in interaction rows
- Notes under exhibits are too thin to stand alone for a referee
- You are unsure how Springer wants figures and tables delivered

## The JOPE exhibit bar

Population economics has natural visual forms, and JOPE exhibits should make the headline result
legible at a glance to a population economist. Principles:

- **Lead with the demographic picture.** Event-time plots around a birth or a move (child-penalty style),
  binned RD plots at a birth-date or age cutoff, hazard or survival curves, age or cohort profiles,
  and event-study plots for staggered reforms communicate a result faster than a coefficient table.
  Population-structure figures (age pyramids, Lexis-style cohort diagrams) earn their place when
  composition drives the design.
- **One main table, deep appendix.** Keep the main table tight: headline outcomes, the preferred
  specification, clustering noted; push alternative windows, weights, cohorts, and robustness to the
  electronic supplementary material.
- **Self-contained notes.** Each exhibit states the sample and cohort window, the unit of observation,
  weights, the estimator, the level of clustering, the control-group mean, and what bars or bands
  represent.
- **Demographic scaling.** Report effects in percentage points of a hazard, births per woman, years,
  or relative to the control mean, so magnitude is visible, not just significance.
- **Horizons visible.** When tempo vs quantum matters, the figure shows the long horizon, not only the
  first years.

Springer delivery (general Springer author guidelines; confirm on the live JOPE page): tables are
**editable text, numbered consecutively, with a caption and footnotes as superscript lowercase
letters**; figures are **separate files, vector (EPS/PDF) for line art, TIFF at print resolution for
halftones**, numbered consecutively, with captions supplied in the text; color is acceptable online.
Online-only material goes in the **Electronic Supplementary Material (ESM)**. Every exhibit must be
regenerable from the submitted code.

## Execution bridge (StatsPAI / Stata MCP)

Generate exhibits from the fitted result, not by retyping numbers. Full map:
[`execution-with-mcp`](../../_linked/shared-resources/empirical-methods/execution-with-mcp.md).

- **Tables:** `etable` (multi-model columns) or `did_summary_to_latex` straight from the `result_id` —
  one variable definition, one set of numbers, body and appendix in sync.
- **Figures:** `plot_from_result` / `enhanced_event_study_plot` / `event_study_table` — axis units and
  the SE/clustering note baked in; `rdplot` for birth-date cutoffs.
- **Every note** names the estimator + clustering (from the result's diagnostics) and states the
  magnitude in demographic units.

See a full fitted-result → exhibit chain in the
[JF execution walkthrough](../../_linked/Journal-of-Finance-Skills/resources/worked-examples/02-execution-walkthrough.md).

## Checklist

- [ ] Headline result presented as a figure where the design allows
- [ ] Main table limited to preferred specification + headline outcomes
- [ ] Cohort window, weights, clustering level, and estimator stated in each note
- [ ] Control-group mean printed; effects scaled to demographic units
- [ ] Confidence intervals / bands shown; no chartjunk; legible in grayscale
- [ ] Long horizon shown where tempo vs quantum is at stake
- [ ] Figures as separate vector files; tables editable; ESM for the rest
- [ ] Every exhibit reproducible from the master script

## Exhibit-design decision grid (by JOPE design type)

| Design in the paper                         | Lead exhibit a JOPE referee expects                          | Notes line that must appear                              |
|---------------------------------------------|--------------------------------------------------------------|----------------------------------------------------------|
| Birth-date / age RDD                        | Binned scatter with local fit + density plot at the cutoff   | Bandwidth, kernel, density-test p-value, compliers       |
| Staggered family-policy reform (DID)        | Event-study plot, leads near zero, modern estimator          | Estimator, cohort weighting, policy-level clustering     |
| Event study around first birth              | Event-time trajectories by gender with 95% bands, 10+ years  | Event sample, pseudo-event controls, age-cohort controls |
| Fertility hazard                            | Survival / cumulative-hazard curves by treatment             | Censoring rule, cohort window, competing risks           |
| Migration shift-share                       | Map of exposure + first-stage scatter                        | Shares vs shocks, Rotemberg weights, spatial clustering  |
| Ageing / pension-age reform                 | Age profile of the outcome with the eligibility cutoff marked | Age bins, cohort composition, concurrent rules           |

## Worked micro-example (illustrative numbers)

Hypothetical JOPE paper: a pension-age increase from 63 to 65 and grandmothers' childcare hours,
register-linked survey data.

- **Wrong instinct:** an eight-column table of childcare hours, employment, daughters' employment, and
  interactions with stars. A referee cannot find the headline.
- **JOPE-shaped fix:** one age-profile figure — weekly childcare hours by age of the grandmother for
  pre- and post-reform cohorts, with the old and new eligibility ages marked; the jump at 63 disappears
  for the post-reform cohort (−2.1 hours/week, 95% CI −3.4 to −0.8, *illustrative*). Daughters'
  employment sits beside it as a secondary panel; interactions move to the ESM flagged "exploratory."
- **Note line:** "Cohorts born 1948–1956; survey weights; clustering at birth-cohort × region; bars are
  95% wild-cluster-bootstrap CIs; control mean 7.4 hours/week. Figures *illustrative*."

## Referee pushback the right exhibit pre-empts

- *"Is 2 hours a week a lot?"* → print the control mean and a benchmark (formal childcare hours) on the figure.
- *"Which splits were pre-specified?"* → solid markers for pre-specified subgroups, hollow for
  exploratory, adjusted intervals shown.
- *"Is this timing or level?"* → show the horizon that distinguishes them.

## Anti-patterns

- A dense table when one event-time or RD plot would carry the result
- Notes that omit the cohort window, weights, or clustering level
- Significance stars with no demographic magnitude
- Figures pasted into the manuscript at screen resolution; tables as images
- A heterogeneity panel that hides which splits were pre-specified versus mined

## Output format

```
【Headline exhibit】figure type + what it shows
【Main table】outcomes + spec + clustering + control mean noted
【Appendix / ESM exhibits】[robustness, cohorts, weights, attrition, ...]
【Scaling】effects in demographic units? [Y/N]
【Springer delivery】vector figures as separate files, editable tables? [Y/N]
【Reproducible from code?】[Y/N]
【Next step】jope-writing-style
```

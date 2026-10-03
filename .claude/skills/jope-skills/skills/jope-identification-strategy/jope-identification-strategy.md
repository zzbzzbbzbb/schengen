---
name: jope-identification-strategy
description: Use when the causal identification strategy is the bottleneck for a Journal of Population Economics (JOPE) manuscript — selection into births, marriage, migration, or survival; policy-reform DID, birth-date RDD, twins/sex-composition IV, shift-share migration designs. Stress-tests the design before tables are drafted.
---

# Identification Strategy (jope-identification-strategy)

## When to trigger

- The empirical core is OLS with controls and the demographic event (birth, marriage, move, death) is a choice
- An event study around births treats the timing of first birth as if it were random
- A policy DID uses two-way fixed effects on staggered regional adoption
- An RDD at a birth-date or age cutoff has not checked birth-timing manipulation
- An immigration design uses enclave shares without saying where identification comes from
- You are unsure whether a theory paper needs an empirical test to clear the JOPE bar

## The JOPE identification bar

The defining problem in population economics is that **demographic events are chosen or selected**: who
has a child and when, who marries, who migrates, who survives. JOPE referees — economists who often have
demographic training — ask first how the design handles that selection. The implicit credibility ranking
(strong → weaker):

1. **Policy reforms with sharp eligibility** — DID, event study, or RDD at a birth-date or age cutoff:
   parental leave, child benefits, childcare, pension age, abortion access, immigration rules.
2. **Natural experiments and shocks** — twins, sibling sex composition, infertility, famine, war, or
   epidemic cohorts, plant closures, lottery-type admissions.
3. **Event studies around demographic events** (child-penalty style) — credible only with explicit
   treatment of event timing as a choice and with pseudo-event or never-event comparison groups.
4. **Shift-share / enclave instruments** for migration — identification must be named as coming from
   shares or from shocks.
5. **Panel fixed effects, selection on observables, duration models with unobserved heterogeneity** —
   acceptable as complements, rarely as the spine.

**Theory papers** (overlapping generations, unified growth, marriage markets, household bargaining) are
judged on the mechanism and its testable implications, not on a design; JOPE publishes them. A
descriptive demographic paper survives only with exceptional data or a measurement innovation.

## Branch paths

### Policy-reform DID / event study
- Staggered adoption → Callaway–Sant'Anna, Sun–Abraham, de Chaisemartin–D'Haultfœuille, or
  Borusyak–Jaravel–Spiess; report a Goodman-Bacon decomposition; plot leads.
- Fertility responds with a lag: a conception response appears nine or more months after the reform.
  Define event time by conception or expected-birth date and say so.
- Separate **tempo** (timing) from **quantum** (completed fertility) with long horizons.
- **Anticipation:** announced reforms shift conceptions before implementation; inspect pre-period dynamics.
- Cluster at the policy level; with few regions (16 German Länder, 20 Italian regions, 26 Swiss cantons)
  use wild-cluster bootstrap or randomization inference.

### RDD at birth-date or age cutoffs
- **Birth timing is manipulable** (induced deliveries, scheduled caesareans, registration dates) → density
  test at the cutoff, donut RD, and a placebo cutoff in a pre-reform year.
- Age cutoffs (pension eligibility, school entry) are sharp but often coincide with other rules — rule out
  concurrent discontinuities.
- Report the complier population and bandwidth robustness with bias-corrected CIs.

### IV for fertility and family size
- Twins and same-sex sibling instruments: argue exclusion (twins change spacing and child health; sex
  preferences differ across cultures); describe the LATE population (families at the margin of a third child).
- Weak-IV diagnostics and Anderson–Rubin confidence sets; report the reduced form.

### Migration
- Enclave / shift-share: state whether identification comes from **shares** (Goldsmith-Pinkham, Sorkin &
  Swift) or **shocks** (Borusyak, Hull & Jaravel); report Rotemberg weights or shock-level balance.
- **Selection of migrants:** compare stayers, movers, and returnees; survey undercount of return migrants.
- Natural experiments: visa lotteries, sudden inflows, border or policy changes.

### Event studies around births or partnership
- Event timing is endogenous; use pseudo-events for the childless, age-by-cohort controls, and cross-check
  against a reform-based design where one exists.
- Report dynamics over ten or more years; penalties and recoveries are dynamic.

### Mortality and ageing
- Survival analysis with left truncation, competing risks, and frailty.
- Age-period-cohort: linear APC effects are not separately identified; state the constraint and show
  robustness to alternatives.

## Worked micro-example (illustrative)

Hypothetical: a child-benefit increase for children born on or after 1 January, estimated as an RDD on
birth date; the outcome is the probability of a next birth within four years.

- **Trap:** a 2 pp jump in next births at the cutoff — but the density of births also jumps across the
  cutoff (postponed deliveries, re-dated registrations), so the just-after sample is selected.
- **JOPE-shaped fix:** `rddensity` at the cutoff; a donut RD excluding ± 2 weeks; the same cutoff in a
  pre-reform year as a placebo; the complier description (parents with a late-December / early-January
  birth); and the outcome at eight years to separate tempo from quantum. Numbers *illustrative*.

## Credibility pushback and the design-level answer

| Referee concern                                     | What clears the JOPE bar                                          |
|-----------------------------------------------------|-------------------------------------------------------------------|
| "Birth timing is manipulated at your cutoff"        | Density test + donut RD + placebo-year cutoff                     |
| "Staggered TWFE is biased here"                     | Modern estimator + Bacon decomposition + event-study plot        |
| "First-birth timing is a choice, not an event"      | Pseudo-events, cohort-age controls, reform-design cross-check    |
| "The enclave instrument violates exclusion"         | Shares-vs-shocks statement, pre-period balance, Rotemberg weights |
| "Twins change more than family size"                | Exclusion in three registers; bounds; complier description        |
| "This is a timing effect"                           | Long-horizon or completed-fertility outcome                       |
| "Age, period, and cohort are not identified"        | Name the constraint; show robustness to alternatives             |

## Execution bridge (StatsPAI / Stata MCP)

Estimate and audit the identification claim, don't only argue it. Full map:
[`execution-with-mcp`](../../_linked/shared-resources/empirical-methods/execution-with-mcp.md).
Population economics leans on reform-based quasi-experiments and birth-date cutoffs; the manipulation
test and the tempo/quantum horizon are the checks referees here expect to see run.

1. `detect_design` → `recommend` → fit with `as_handle=true` → `audit_result` to list the checks the
   design still owes.
2. **Staggered DiD:** `callaway_santanna` / `sun_abraham` + `bacon_decomposition` +
   `honest_did_from_result` (the pre-trend test is low-power, Roth 2022).
3. **Birth-date / age RDD:** `rdrobust` (bias-corrected) + `rddensity` / `mccrary_test`; re-fit on a
   donut sample and at a placebo cutoff.
4. **IV:** `effective_f_test` + an `anderson_rubin_ci`, not a 2SLS t-stat alone.
5. **OVB:** `oster_delta` / `sensemakr` — how strong a confounder would have to be.

Report the magnitude in demographic units; route the full battery to the appendix; keep every number
reproducible. A run end-to-end (synthetic data, real returns) is in the
[JF execution walkthrough](../../_linked/Journal-of-Finance-Skills/resources/worked-examples/02-execution-walkthrough.md).
If StatsPAI/Stata are not connected, adapt the vendored `../../resources/code` skeleton and flag any
unverified number.

## Anti-patterns

- TWFE on staggered regional reforms with no discussion of heterogeneity bias
- A birth-date RDD with no density test and no donut
- An event study around first birth presented as if birth timing were exogenous
- Inference not clustered at the policy level; few-cluster bias ignored
- A short-horizon fertility effect presented as a change in completed fertility

## Output format

```
【Design】policy DID / event study / RDD / IV / shift-share / survival / theory / descriptive
【Demographic selection handled how】one sentence
【Identifying variation】one sentence
【Diagnostics done】[density at cutoff, pre-trends, Bacon, first-stage F, Rotemberg weights, ...]
【Diagnostics missing】[...]
【Inference】clustering level + few-cluster handling + MHT
【Tempo vs quantum horizon】...
【Interpretation】LATE / compliers; institutional scope
【Next step】jope-data-analysis
```

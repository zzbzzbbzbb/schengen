---
name: jope-data-analysis
description: Use when estimation, weighting, cohort construction, demographic measurement, attrition, or inference choices need to meet Journal of Population Economics (JOPE) empirical norms — survey and register panels, census microdata, fertility, mortality, and migration measures. Covers the analysis itself, not the identifying design.
---

# Data Analysis (jope-data-analysis)

## When to trigger

- The identification is settled but weighting, cohort construction, or inference is unconvincing
- A referee would question survey weights, panel attrition, right-censored fertility, or measurement of the demographic outcome
- You need to decide how to present heterogeneity by parity, gender, education, or migrant background
- You are unsure the analysis would survive a replication request

## JOPE empirical norms

JOPE referees work with **household panels, registers, censuses, and demographic surveys** — SOEP, HILDA,
PSID, NLSY, Understanding Society, SHARE, HRS, DHS, IPUMS, Nordic registers — and know their traps.
Analysis that ignores them reads as naive. Hold the work to these standards:

- **Weights and representativeness.** Use survey weights where the estimand is a population quantity;
  show unweighted results alongside; register data need no weights but need a clear population definition.
- **Cohorts and censoring.** Completed fertility is observed only for women past roughly age 40–45;
  younger cohorts are right-censored. Use hazard models or restrict to completed cohorts, and say which.
  Period measures (TFR) and cohort measures answer different questions; tempo distortions (Bongaarts–Feeney)
  matter when timing shifts.
- **Demographic measurement.** Say how births, unions, moves, and deaths are measured — retrospective
  histories vs panel observation, registered vs reported, intentions vs behavior — and address recall,
  under-registration, return-migration undercount, and household-definition changes.
- **Attrition and selective panel exit.** Household panels lose movers, migrants, and the recently
  separated — exactly the demographic events studied. Document attrition by event status; bound (Lee)
  where differential; use register linkage when available.
- **Inference matched to the policy level.** Cluster where policy varies (region, cohort × region);
  with few clusters use wild-cluster bootstrap or randomization inference.
- **Heterogeneity, disciplined.** JOPE audiences care about parity, gender, education, migrant
  generation, and institutional context; present pre-specified or theory-motivated splits as
  confirmatory, the rest as exploratory with multiple-testing adjustment.
- **Magnitudes in demographic units.** Percentage points of a hazard, births per woman, years of life,
  relative to the control mean — see jope-contribution-framing.

Springer Nature's research-data policy asks authors to ensure that data and code support the published
claims and to include a data-availability statement; build the analysis so every number is reproducible
from a script the day you submit (see jope-replication-and-data-policy).

## Robustness expected

- Alternative cohort windows, age ranges, and horizon lengths (short vs completed fertility)
- Weighted vs unweighted; alternative household or union definitions
- Hazard vs linear probability; competing risks where relevant (birth vs separation; emigration vs death)
- Placebo outcomes that should not move (e.g., births conceived before a reform's announcement)
- Spillovers across regions or across siblings and partners where treatment leaks

## Worked analysis (illustrative)

Hypothetical: a childcare-subsidy reform in one country, household-panel data, outcome = second birth
within four years, 12 regions.

- **Inference:** cluster at the region level; with 12 clusters report wild-cluster-bootstrap p-values
  (*illustrative* effect = +2.4 pp on a base of 38 percent, bootstrap p = 0.04).
- **Censoring:** women under 40 at the last wave are right-censored; estimate a discrete-time hazard and
  show the linear-probability version for the completed-cohort subsample.
- **Attrition:** 14 percent of mothers with a birth leave the panel vs 9 percent without — differential;
  add Lee bounds and a register-linked check where available.
- **Measurement:** births taken from the panel's birth biography cross-checked against the household
  roster; discrepancies reported.
- **Heterogeneity:** the education split was theory-motivated and pre-specified; report it with
  Romano–Wolf adjustment and demote the rest.

## Empirical-credibility pushback and the fix

| Referee objection                                        | The JOPE-norm response                                             |
|----------------------------------------------------------|--------------------------------------------------------------------|
| "Your fertility outcome is right-censored"               | Hazard model; completed-cohort subsample; state the horizon         |
| "Weights ignored; the sample over-represents X"          | Weighted and unweighted; population definition stated               |
| "Movers and migrants leave your panel"                   | Attrition by event status; Lee bounds; register cross-check         |
| "12 regions is too few for clustered SEs"                | Wild-cluster bootstrap / randomization inference                    |
| "Subgroup result looks mined"                            | Pre-specified vs exploratory; Romano–Wolf                           |

## Execution bridge (StatsPAI / Stata MCP)

Run the battery, don't just enumerate it. Full map:
[`execution-with-mcp`](../../_linked/shared-resources/empirical-methods/execution-with-mcp.md).
Population economics leans on panel and register data with few policy clusters and many related
outcomes (timing, parity, labor supply); the few-cluster bootstrap and the family-wise correction are
the checks to run.

- **Many outcomes / specifications:** `romano_wolf` (step-down FWER) or `benjamini_hochberg` — report
  the adjusted threshold.
- **OVB sensitivity:** `oster_delta` / `sensemakr` — the confounder strength that would overturn the headline.
- **Inference:** `wild_cluster_bootstrap` (few regions), `twoway_cluster` / `conley`.
- **Re-fit off one handle:** `audit_result(result_id)` lists the missing checks and the exact
  `suggest_function` for each.
- **Exhibits:** `etable` / `did_summary_to_latex` from the handle — no retyped numbers.

Keep the decisive checks in the body and the exhaustive (now actually-run) battery in the appendix. See
the executed chain in the
[JF execution walkthrough](../../_linked/Journal-of-Finance-Skills/resources/worked-examples/02-execution-walkthrough.md).
Duration and competing-risks models are not in the StatsPAI chain; use Stata `stcox` / `stcrreg` /
`logit` discrete-time hazards or R `survival` / `cmprsk` via the vendored `../../resources/code` layout.

## Anti-patterns

- Completed-fertility claims from women still in their twenties
- Survey weights silently dropped; no population definition
- Attrition of movers and the separated ignored in a paper about moving and separating
- Standard errors clustered below the policy level; few-cluster bias ignored
- A wall of unadjusted subgroup interactions presented as confirmatory
- Tables that cannot be regenerated from the submitted code


## Evidence pass for Journal of Population Economics

Treat this skill as an executable review pass, not a prose hint. First lock the demographic margin (fertility, partnership, household formation, migration, mortality or ageing), the economic mechanism, the identification against demographic selection, and the population or policy implication; then judge whether the manuscript answers the venue's real reader: population economists who expect an explicit economics-demography link, a design that handles selection into demographic events, and population-level or policy relevance.

- **Do the pass:** Audit the research design before polishing prose: unit of analysis, cohort window, censoring, weights, comparison set, uncertainty, sensitivity, missingness, and reproducibility must be visible.
- **Return a ledger:** give `claim / evidence / risk / manuscript location` rows, so the next agent can edit rather than rediscover the issue.
- **Sibling guard:** compare against Demography or Population and Development Review for a demographer audience, Journal of Human Resources or Labour Economics for labor mechanisms without a demographic margin, Journal of Health Economics for health mechanisms, Review of Economics of the Household for household economics, and JDE for low-income development mechanisms; if a sibling owns the contribution, recommend re-routing before polishing format.
- **Stop condition:** do not give submission-ready advice until the pack's `../../resources/official-source-map.md` has been checked for volatile rules and the manuscript has one concrete fix for the largest venue-specific risk.

## Output format

```
【Estimator】+ why it fits the design (hazard / LPM / event study / ...)
【Cohorts and censoring】window, horizon, completed vs period measure
【Weights】weighted / unweighted / register population definition
【Inference】clustering level / few-cluster method / MHT
【Attrition】rate by event status, differential? bounds?
【Measurement】how the demographic outcome is observed + error handling
【Heterogeneity】pre-specified vs exploratory
【Robustness done / missing】[...]
【Reproducible from code today?】[Y/N]
【Next step】jope-tables-figures
```

---
name: jope-contribution-framing
description: Use when sharpening the economics-demography takeaway of a Journal of Population Economics (JOPE) manuscript — the explicit "what this teaches about how economic forces and population outcomes interact" claim an editor can restate in one sentence. Frames the contribution; it is not a writing-polish pass.
---

# Contribution Framing (jope-contribution-framing)

## When to trigger

- You can describe the coefficient but not what it teaches about fertility, family, migration, or ageing
- The introduction states estimates but never the population-level or policy implication
- An editor skimming the 150-word abstract could not restate the contribution
- The paper risks reading as "a labor or health result on a demographic sample" rather than population economics

## The JOPE framing bar

JOPE publishes research on the **relationships between economic and demographic problems**, and its
abstract rule is explicit: **at most 150 words, non-technical, stating the innovation and contribution**.
Framing turns a result into a contribution by answering, early:

- **What economic force moved which demographic margin** (or the reverse) — fertility quantum or tempo,
  partnership formation or dissolution, household formation, migration flows or selection, mortality,
  ageing, population composition?
- **For whom it binds** — which cohorts, parities, genders, education groups, migrant generations, or
  institutional settings?
- **What follows** — for population policy (family benefits, leave, childcare, pensions, immigration
  rules, abortion access), for welfare across groups, or for theory (quantity-quality, bargaining,
  overlapping-generations models)?

Magnitudes belong in **demographic units**: births per woman, percentage points of a birth hazard or of
the share with a second child, percentage points of a migration rate, years of life expectancy, change in
a dependency ratio — each relative to the control-group mean. Two percentage points off a base of 60
percent reads differently from two off a base of 10.

## Framing tactics

- Lead with the population-economics question and answer; the design is a tool.
- Say which of **tempo vs quantum**, **flow vs stock**, **cohort vs period** the estimate speaks to.
- Convert individual-level effects to a population quantity where the design allows (completed
  fertility, net migration, old-age dependency) and say what is extrapolated.
- Name the policy lever and, where possible, its cost per outcome (per additional birth, per retained
  worker, per year of healthy life).
- State external validity across institutional settings — welfare-state generosity, labor-market
  rigidity, gender norms, immigration regime — because JOPE's readership is international.

## From result to contribution (worked, illustrative)

Hypothetical: a four-month extension of paid parental leave, identified off a child-birth-date cutoff.

- **Weak framing:** "We find a 3 percentage-point increase in the probability of a second birth within
  five years." A coefficient, no lesson.
- **JOPE framing:** "Extending paid leave by four months raised second births within five years by 3
  percentage points (≈ 5 percent of the control mean, *illustrative*) with no offsetting decline at
  longer horizons — a quantum effect, not a timing shift — so leave generosity moves completed fertility
  among employed mothers." Names margin, population, mechanism, and policy implication.
- **Scope hedge:** compliers are employed mothers near the cutoff in a high-coverage welfare state; say
  what it teaches about leave policy elsewhere without claiming a universal elasticity.

## Contribution-strength screen

| Symptom in the draft                                        | The reframe a JOPE referee wants                                    |
|-------------------------------------------------------------|---------------------------------------------------------------------|
| "We estimate the effect of X on Y among women aged 20–45"   | Which demographic margin moved and which population quantity changes |
| Effect only as a hazard ratio or log-odds                   | Percentage points of the hazard, births per woman, vs control mean   |
| Timing effect sold as a fertility-level effect              | Tempo vs quantum stated; long-horizon outcome shown                  |
| One-country result with no institutional context            | Which institutional feature the mechanism depends on                 |

## Referee pushback on contribution

- *"This is a timing shift, not more children."* → report a long-horizon or completed-fertility outcome
  and say tempo vs quantum explicitly.
- *"Why JOPE rather than a labor journal?"* → make the demographic margin the spine of the framing.
- *"Is 0.02 children per woman meaningful?"* → benchmark against cross-country TFR gaps, other
  policies' effects, and cost per additional birth.

## Anti-patterns

- An abstract of coefficients with no stated economics-demography lesson
- Burying the contribution in the conclusion where a desk-screening editor never reaches it
- Hazard ratios and odds ratios with no translation to population units
- Overclaiming a single-country local effect as a universal demographic law


## Contribution pass for Journal of Population Economics

Treat this skill as an executable review pass, not a prose hint. First lock the demographic margin (fertility, partnership, household formation, migration, mortality or ageing), the economic mechanism, the identification against demographic selection, and the population or policy implication; then judge whether the manuscript answers the venue's real reader: population economists who expect an explicit economics-demography link, a design that handles selection into demographic events, and population-level or policy relevance.

- **Do the pass:** Translate the result into who learns what, which demographic margin and economic mechanism changes, and which alternative explanation (timing, selection, composition) is ruled out; keep the contribution narrower than the evidence.
- **Return a ledger:** give `claim / evidence / risk / manuscript location` rows, so the next agent can edit rather than rediscover the issue.
- **Sibling guard:** compare against Demography or Population and Development Review for a demographer audience, Journal of Human Resources or Labour Economics for labor mechanisms without a demographic margin, Journal of Health Economics for health mechanisms, Review of Economics of the Household for household economics, and JDE for low-income development mechanisms; if a sibling owns the contribution, recommend re-routing before polishing format.
- **Stop condition:** do not give submission-ready advice until the pack's `../../resources/official-source-map.md` has been checked for volatile rules and the manuscript has one concrete fix for the largest venue-specific risk.

## Output format

```
【One-sentence contribution】"We show that ... moved ... for ... which implies ..."
【Demographic units】births per woman / pp of hazard / pp of migration rate / years, vs control mean
【Tempo vs quantum, flow vs stock, cohort vs period】stated? [Y/N]
【Scope / external validity】institutional setting where it binds, where it may not
【Policy or theory implication】...
【Next step】jope-identification-strategy
```

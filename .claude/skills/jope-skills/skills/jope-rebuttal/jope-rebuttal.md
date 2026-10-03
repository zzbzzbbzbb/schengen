---
name: jope-rebuttal
description: Use when responding to a Journal of Population Economics (JOPE) decision — drafting the response letter and revision plan for a major or minor revision. Strategy for the response; it does not rewrite the manuscript.
---

# Rebuttal & R&R Strategy (jope-rebuttal)

## When to trigger

- A JOPE revise-and-resubmit arrived and you need a response-letter strategy
- Referee reports conflict and you must triage which changes to make
- A referee asks for a demographic analysis (completed fertility, competing risks, cohort view) you have not run
- You need to decide what to concede, what to defend, and what to add

## Read the decision first

Map the **editor's letter** against the referee reports: the editor's priorities are binding even when
a referee raised a point in passing. JOPE editors handle papers by field and decide quickly; a revision
that resolves the editor's two or three gating concerns — typically **selection into the demographic
event, the tempo/quantum or cohort/period interpretation, and the economics-demography contribution** —
is what moves the paper. Respect the revision deadline in the Editorial Manager letter; ask the
editorial office (JOPE-Office@glabor.org) for an extension before it lapses, not after.

## Response-letter structure

- **Cover summary:** thank the editor and referees; state the two or three substantive changes that most
  improve the paper; flag where you respectfully disagree and why.
- **Point-by-point:** quote each comment, then respond. For each: what changed, where (section, table,
  figure), and the new result — or a reasoned, evidence-backed defense if you did not change it.
- **New analyses:** add the cohort, horizon, weighting, attrition, or identification checks requested;
  if a check is infeasible (restricted data, censored cohorts, power), say so transparently and offer
  the closest alternative.
- **Abstract and declarations:** re-count the abstract (≤ 150 words, non-technical) after revision —
  abstracts grow during R&R — and update the data-availability statement and replication package so
  they reflect every new result.

## Tactics

- Concede cheap, defensible points quickly to build credibility for the points you defend.
- For selection objections, add a design-based check (density test, pseudo-event, placebo cohort),
  not rhetoric.
- When a referee reads the result as a timing effect, show the long horizon rather than arguing.
- Keep claims calibrated across institutional settings; JOPE's international readership punishes
  overreach about "fertility" or "migration" in general when the evidence is one country.
- If a referee cites a demography-journal literature you ignored, engage with it; the editors expect
  population economists to know both literatures.

## Common JOPE referee objections and the venue-specific fix

| Referee objection                                            | The fix that lands at JOPE                                               |
|--------------------------------------------------------------|--------------------------------------------------------------------------|
| "Births (or moves, or marriages) are selected"               | Design-based selection check; bounds; complier description               |
| "This is tempo, not quantum"                                 | Long-horizon or completed-cohort outcome; state which the design identifies |
| "Cohort and period effects are conflated"                    | Cohort-based re-estimation; APC constraint stated                        |
| "Weights ignored / sample not representative"                | Weighted and unweighted; population definition                           |
| "Movers and the separated leave your panel"                  | Attrition by event status; Lee bounds; register cross-check              |
| "Too few policy clusters"                                    | Wild-cluster bootstrap / randomization inference                         |
| "Birth timing manipulated at the cutoff"                     | Density test; donut RD; placebo-year cutoff                              |
| "What is the policy lesson?"                                 | Effect in demographic units; cost per outcome; institutional scope       |
| "The abstract is technical / too long"                       | Rewrite to ≤ 150 non-technical words                                     |

## Worked micro-example (illustrative)

Hypothetical: a major revision on a parental-leave extension and second births. The editor flags three
gates — selection at the birth-date cutoff, tempo vs quantum, and a heterogeneity claim by education.

- **Concede + fix (cheap):** add `rddensity` and a donut RD; the estimate moves from +3.1 to +2.8 pp
  and the CI stays positive (*illustrative*) — concede the original omission, show the result survives.
- **Defend with evidence:** for tempo vs quantum, add the eight-year outcome showing no offsetting
  decline; state that completed fertility is right-censored for the youngest cohorts and report the
  completed-cohort subsample.
- **Demote:** move the education interaction to "exploratory, multiple-testing adjusted."
- **Letter line:** "Comment 2 (manipulation): density test p = 0.41 and donut RD (± 2 weeks) in Table
  A3; estimate 2.8 pp, 95% CI 0.9–4.7; the replication package reflects this change." Numbers *illustrative*.

## Anti-patterns

- Defending everything and conceding nothing
- Answering a "timing vs level" objection with prose instead of a longer horizon
- Adding a robustness table the code does not reproduce
- Letting the abstract drift over 150 words during revision
- A response letter that does not point to the exact revised location of each change

## Output format

```
【Decision type】major revision / minor revision / reject-with-encouragement
【Editor's gating concerns】[top 2-3]
【Concede】[points + fix]
【Defend (with evidence)】[points + argument]
【New analyses】[cohort / horizon / selection / weighting checks added]
【Abstract re-counted ≤150 words?】[Y/N]
【Replication package and data statement in sync?】[Y/N]
【Deadline】date from the decision letter; extension requested? [Y/N/NA]
```

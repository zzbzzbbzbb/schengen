---
name: jope-literature-positioning
description: Use when staking a manuscript's contribution against the population-economics literature for the Journal of Population Economics (JOPE). Positions the paper at the frontier; it does not write a standalone survey.
---

# Literature Positioning (jope-literature-positioning)

## When to trigger

- A reviewer would ask "what is new here relative to the population-economics literature?"
- The introduction reads like a survey instead of staking a claim
- You cannot name the two or three papers you build on or overturn
- The paper sits between labor, health, and demography and you have not chosen which conversation it joins

## The JOPE positioning bar

JOPE referees are population economists, often with demography or labor training. They judge the
**economics-demography contribution first**. Three moves:

1. **Locate the conversation.** Name the specific literature — e.g., the quantity-quality trade-off,
   fertility responses to family policy or income shocks, the child penalty, marriage markets and sex
   ratios, household bargaining and intra-household allocation, immigration and native outcomes, selection
   of migrants, remittances, pensions and retirement under population ageing, health and mortality over the
   life course, unified growth and the demographic transition, or the economics of abortion and contraception.
2. **Stake the gap precisely.** Say what is known, what is open, and why prior work could not answer it —
   usually **selection into the demographic event**, missing cohort or register data, or a policy that had
   not yet happened.
3. **Claim the increment.** A new causal estimate on a demographic margin, a mechanism linking the economic
   cause to the population outcome, new data (registers, linked censuses, historical records), or a model
   that delivers a testable demographic implication.

Cite canonical anchors and the recent frontier (working papers and the last few years). JOPE publishes many
papers on adjacent questions; referees will know the closest JOPE articles. Search the journal's own back
issues before claiming novelty.

## Positioning tactics

- Tie the increment to a **population-level quantity** — completed fertility, migration flows, sex ratios,
  dependency ratios, life expectancy — not only to an individual-level coefficient.
- If the method is familiar (event study around births, shift-share for immigration, twins IV), the novelty
  must be in the **question, the population, or the mechanism**.
- Distinguish **tempo from quantum** (fertility), **flows from stocks** (migration), and **cohort from period**
  effects; positioning often hinges on which one prior work estimated.
- Name the closest JOPE paper explicitly. A paper that ignores the journal's own recent work reads as off-venue.

## Worked positioning (illustrative)

Hypothetical: an RDD on a pension-eligibility age and grandmothers' childcare provision.

- **Conversation joined:** intergenerational time transfers and the labor supply of older women under
  pension reform.
- **Binding gap:** prior work estimates the effect of grandparental childcare on *mothers'* employment; the
  effect of pension rules on the *supply* of that care is less studied.
- **Our increment:** the eligibility cutoff shifts grandmothers' time, raising daughters' employment by
  (*illustrative*) 3 pp — a pension-policy channel to the child penalty.
- **Honest competition:** cite the closest recent JOPE and JHR papers and state the delta (supply margin vs
  demand margin; RDD vs panel FE).

## Positioning failure modes and fixes

| Failure                                                     | JOPE-specific fix                                              |
|-------------------------------------------------------------|----------------------------------------------------------------|
| Survey-style intro that never stakes a claim                | One paragraph: known / binding gap / our increment             |
| Positioned only against labor economics                     | Name the demographic literature the result changes             |
| Ignores the closest recent JOPE article                     | Search JOPE back issues; cite it and state the delta           |
| Fertility timing result sold as a fertility-level result    | Say whether prior work and yours estimate tempo or quantum     |

## Anti-patterns

- A literature section that surveys three fields and stakes no claim
- "First to study X in country Y" as if a new setting were a contribution
- Missing the closest JOPE paper on the same reform or population
- Positioning a migration paper only within the wage literature, ignoring selection and composition


## Positioning pass for Journal of Population Economics

Treat this skill as an executable review pass, not a prose hint. First lock the demographic margin (fertility, partnership, household formation, migration, mortality or ageing), the economic mechanism, the identification against demographic selection, and the population or policy implication; then judge whether the manuscript answers the venue's real reader: population economists who expect an explicit economics-demography link, a design that handles selection into demographic events, and population-level or policy relevance.

- **Do the pass:** Build a three-column map: incumbent conversation, unresolved tension, and this manuscript's delta; include one sibling-venue omission that would make a referee doubt the fit.
- **Return a ledger:** give `claim / evidence / risk / manuscript location` rows, so the next agent can edit rather than rediscover the issue.
- **Sibling guard:** compare against Demography or Population and Development Review for a demographer audience, Journal of Human Resources or Labour Economics for labor mechanisms without a demographic margin, Journal of Health Economics for health mechanisms, Review of Economics of the Household for household economics, and JDE for low-income development mechanisms; if a sibling owns the contribution, recommend re-routing before polishing format.
- **Stop condition:** do not give submission-ready advice until the pack's `../../resources/official-source-map.md` has been checked for volatile rules and the manuscript has one concrete fix for the largest venue-specific risk.

## Output format

```
【Conversation joined】population-economics subliterature
【Frontier papers】[2-4 anchors, incl. recent and the closest JOPE article]
【Binding gap】one sentence
【Our increment】what we add the frontier lacks
【Tempo/quantum, flow/stock, cohort/period clarified?】[Y/N]
【Next step】jope-contribution-framing
```

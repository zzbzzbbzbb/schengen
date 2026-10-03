---
name: jope-topic-selection
description: Use when judging whether a research question fits the Journal of Population Economics (JOPE) — a first-order question about the relationship between economic and demographic problems. Tests topic fit before identification or drafting begins.
---

# Topic Selection (jope-topic-selection)

## When to trigger

- You have data or a policy setting but are unsure it is a *population-economics* question
- The question is interesting but the demographic margin is incidental
- You are weighing JOPE against a labor, health, development, or demography outlet
- You want to know whether the work fits an open JOPE special collection

## The JOPE fit bar

JOPE is the **leading field journal in population economics** (Springer; founded 1987). Its scope is
**theoretical and applied research and surveys on the broadly defined relationships between economic and
demographic problems**:

- **Micro:** household behavior — household formation, marriage and divorce, **fertility choices**,
  education, labor supply, and **migration**.
- **Macro:** economic growth with exogenous or endogenous population evolution, population policy, savings
  and pensions, social security, housing, and health care.
- **Also:** economic approaches to human biology, population dynamics and public choice, and the effect of
  population on the distribution of income and wealth.
- **Societal challenges the journal names:** gender, wellbeing and happiness, sexuality, abortion,
  religion, poverty, inequality, war, peace, and refugees.

A question fits when:

- A **demographic margin is the point** — births, marriage, household formation, migration, survival,
  ageing, or population composition is the outcome, the cause, or the transmission channel.
- An **economic mechanism** drives or responds to it — prices, incomes, policies, institutions, markets.
- It is **first-order**: the answer matters for population outcomes, public budgets, or welfare across
  groups, not a marginal refinement inside one subfield.

Acceptance rates reported by the Editor-in-Chief run around **5-7%**, and the journal desk-rejects to give
early signals. The economics-demography link has to be visible in the first paragraph.

## Decision shortcuts

- "It's a labor-supply paper on a sample of mothers" → fits only if the demographic event (birth, partnership,
  childcare by grandparents) is the mechanism. Otherwise a labor outlet owns it.
- "It's a migration paper about natives' wages" → fits; migration is core JOPE scope. Make the population
  composition channel explicit.
- "It's an abortion, contraception, or family-policy reform" → strong fit; check the open collections.
- "It's an OLG or unified-growth model with endogenous fertility" → fits; JOPE publishes theory.
- "It's a health paper with age as a control" → weak fit unless mortality, ageing, or the life course is the question.

## Fit-screen table (illustrative verdicts)

| Candidate question                                                         | JOPE fit | Why                                                         |
|----------------------------------------------------------------------------|----------|-------------------------------------------------------------|
| Effect of a sex-selective-abortion ban on women's later schooling           | Strong   | Demographic policy → cohort sex ratios → human capital       |
| Female breadwinning and domestic abuse within couples                       | Strong   | Household bargaining, gender, partnership outcomes            |
| Pension-age reform and grandparental childcare supply                       | Strong   | Ageing, pensions, intergenerational time transfers           |
| Minimum-wage effects on teen employment                                     | Weak     | Age-defined sample, no demographic mechanism                 |
| Stock-market returns and aggregate birth rates, cross-country correlation   | Weak     | Demographic outcome, but no credible design or mechanism      |

## Worked fit call (illustrative)

A team has register data on a housing-subsidy reform and wonders if it is a JOPE paper.

- **Off-fit version:** "Did the subsidy raise homeownership among young adults?" — a housing-finance question.
- **On-fit version:** "Did cheaper family housing raise completed fertility, or only shift the timing of
  first births?" — a population-economics question (tempo vs quantum) with a policy lever. Route to
  `jope-identification-strategy` to separate timing from completed fertility.

## Referee fit pushback

- *"This is a labor paper that happens to condition on parenthood."* → move the demographic event into the
  mechanism, or retarget honestly.
- *"Where is the population-level implication?"* → say what the effect implies for fertility rates,
  migration flows, age structure, or the old-age dependency burden.

## Anti-patterns

- An age- or sex-defined sample presented as population economics with no demographic mechanism
- Pure demography (descriptive rates, decompositions) with no economic behavior or policy
- Ignoring the tempo/quantum distinction when the outcome is fertility
- Treating JOPE as a fallback for a rejected general-interest paper without rebuilding the demographic stake


## Fit pass for Journal of Population Economics

Treat this skill as an executable review pass, not a prose hint. First lock the demographic margin (fertility, partnership, household formation, migration, mortality or ageing), the economic mechanism, the identification against demographic selection, and the population or policy implication; then judge whether the manuscript answers the venue's real reader: population economists who expect an explicit economics-demography link, a design that handles selection into demographic events, and population-level or policy relevance.

- **Do the pass:** Score the manuscript on venue fit, novelty, evidence readiness, and audience ownership; reject a prestige-only target when a sibling venue owns the contribution more directly.
- **Return a ledger:** give `claim / evidence / risk / manuscript location` rows, so the next agent can edit rather than rediscover the issue.
- **Sibling guard:** compare against Demography or Population and Development Review for a demographer audience, Journal of Human Resources or Labour Economics for labor mechanisms without a demographic margin, Journal of Health Economics for health mechanisms, Review of Economics of the Household for household economics, and JDE for low-income development mechanisms; if a sibling owns the contribution, recommend re-routing before polishing format.
- **Stop condition:** do not give submission-ready advice until the pack's `../../resources/official-source-map.md` has been checked for volatile rules and the manuscript has one concrete fix for the largest venue-specific risk.

## Output format

```
【Population-economics question】one sentence
【Demographic margin】fertility / partnership / household / migration / mortality-ageing / composition
【Economic mechanism】...
【Travels beyond the subfield?】[Y/N + why]
【Open special collection that fits】[name / none]
【Next step】jope-literature-positioning
```

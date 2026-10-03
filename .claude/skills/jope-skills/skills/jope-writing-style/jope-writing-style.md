---
name: jope-writing-style
description: Use when polishing prose for a Journal of Population Economics (JOPE) manuscript so the economics-demography question, answer, and policy stakes land for a broad population-economics audience, under a 150-word non-technical abstract cap. A late-stage polish; do not rewrite the intro before identification and framing are settled.
---

# Writing Style (jope-writing-style)

## When to trigger

- The abstract exceeds 150 words, names estimators, or states a topic but no finding
- The introduction buries the population-economics question under data description
- Demographic terms (TFR, tempo, parity progression, hazard) appear undefined for an economist reader
- Identification and contribution are settled and the paper needs its final polish

## The JOPE prose bar

JOPE readers are population economists, demographers, and policy-oriented economists across many
countries; the writing has to make a **first-order economics-demography question and its answer** land
quickly, with policy stakes explicit. Principles:

- **Abstract: 150 words, non-technical, innovation and contribution stated.** This is the journal's own
  rule and a desk-screen item. Lead with the question, the setting and design in a phrase, the headline
  effect in demographic units, and the contribution. No estimator names, no p-values.
- **Introduction as an argument.** Question → why it matters for population outcomes or policy →
  setting and design in a few sentences → headline result with magnitude → contribution relative to the
  frontier → honest scope → brief roadmap. Avoid a literature-survey opening.
- **Define demographic measures in words** before the reader meets them in a table: total fertility
  rate vs completed cohort fertility, tempo vs quantum, parity progression, hazard, net migration,
  dependency ratio.
- **Institutional detail is part of the argument.** Say how the leave, benefit, pension, or
  immigration rule works, because the mechanism depends on it and the readership is international.
- **Honest scope.** State external-validity limits across institutional settings plainly.
- **Language and references.** Use American or British English consistently. Springer's author-year
  reference style for this journal (in-text "Author (year)" / "(Author and Author year)" / "(Author et al.
  year)"; reference list with initials and no quotation marks) — confirm the exact style and the
  BibTeX file on the live submission guidelines before formatting.
- **Keywords and JEL codes** on the title page; a short, informative title.

## Tactics

- Cut throat-clearing; paragraph one poses the population-economics question.
- Put the policy lever in the reader's hands early: what would a government change, and what would happen?
- Keep the conclusion to what the design supports plus open questions; no new results there.
- Count the abstract. Then count it again after revision — abstracts grow during R&R.

## Abstract rewrite (worked, illustrative)

Hypothetical: a pension-age reform and grandparental childcare.

- **Weak (over the limit, technical; excerpt):** "This paper uses a regression discontinuity design with bias-corrected
  confidence intervals and a density test to study the effect of the 2014 increase in the statutory
  retirement age on grandparental childcare provision using survey data linked to registers..." Names
  methods, states no finding, over the limit.
- **JOPE-shaped (≈ 70 words):** "Raising the pension age keeps older women in work longer. Does it also
  cut the childcare they provide to their adult children? Using a reform that raised the eligibility age
  from 63 to 65 and comparing women just above and below the new threshold, we find that childcare hours
  fall by about a quarter and daughters' employment declines (*illustrative*). Pension reforms shift
  care within families and shape the next generation's labor supply."

## Prose pushback and the fix

| Referee/editor reaction                              | The JOPE-prose fix                                              |
|------------------------------------------------------|-----------------------------------------------------------------|
| "The abstract states a topic, not a finding"         | Lead with the headline effect in demographic units              |
| "The abstract is over the limit and technical"       | 150 words; cut estimator names; keep question, answer, lesson   |
| "A survey delayed the question"                      | Open paragraph one with the population-economics question       |
| "I don't know what tempo means"                      | Define demographic terms in words at first use                  |
| "Does this apply outside your country?"              | Name the institutional feature the mechanism depends on         |

## Calibration anchors (hedged)

- Abstract ≤ 150 words, non-technical, stating innovation and contribution (official guideline).
- Third-party template sites show other abstract limits; the official Springer guideline is the rule.
- No manuscript length cap was located in the latest refresh; keep the main text focused and move
  overflow to the ESM.

## Anti-patterns

- An abstract that names a topic but states no effect size, or runs past 150 words
- Estimator names and p-values in the abstract
- A survey-style introduction that delays the question and result
- Undefined demographic jargon for an economist reader, or undefined econometric jargon for a demographer reader
- Inflated external-validity language unsupported by the design


## Style execution pass for Journal of Population Economics

Treat this skill as an executable review pass, not a prose hint. First lock the demographic margin (fertility, partnership, household formation, migration, mortality or ageing), the economic mechanism, the identification against demographic selection, and the population or policy implication; then judge whether the manuscript answers the venue's real reader: population economists who expect an explicit economics-demography link, a design that handles selection into demographic events, and population-level or policy relevance.

- **Do the pass:** Rewrite the abstract to ≤ 150 non-technical words and the first two pages so each paragraph starts from the venue-level claim, not from chronology or method inventory; preserve exact source-map limits and move technical overflow to the ESM.
- **Return a ledger:** give `claim / evidence / risk / manuscript location` rows, so the next agent can edit rather than rediscover the issue.
- **Sibling guard:** compare against Demography or Population and Development Review for a demographer audience, Journal of Human Resources or Labour Economics for labor mechanisms without a demographic margin, Journal of Health Economics for health mechanisms, Review of Economics of the Household for household economics, and JDE for low-income development mechanisms; if a sibling owns the contribution, recommend re-routing before polishing format.
- **Stop condition:** do not give submission-ready advice until the pack's `../../resources/official-source-map.md` has been checked for volatile rules and the manuscript has one concrete fix for the largest venue-specific risk.

## Output format

```
【Abstract】≤150 words, non-technical, finding + magnitude + contribution? [Y/N + word count]
【Intro arc】question → stakes → design → result → contribution → scope? [Y/N]
【Demographic terms defined】[Y/N]
【Institutional setting explained】[Y/N]
【Language】consistent US or UK English? [Y/N]
【References】Springer author-year style, consistent? [Y/N]
【Next step】jope-replication-and-data-policy
```

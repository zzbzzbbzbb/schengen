> **Illustrative teaching example.** The paper, country, reform, and every number below are
> **fictional** and exist only to demonstrate JOPE house style. No real-paper facts and no real policy
> are stated. Corresponding skills:
> [`jope-writing-style`](../../skills/jope-writing-style/jope-writing-style.md),
> [`jope-contribution-framing`](../../skills/jope-contribution-framing/jope-contribution-framing.md),
> [`jope-identification-strategy`](../../skills/jope-identification-strategy/jope-identification-strategy.md), and
> [`jope-topic-selection`](../../skills/jope-topic-selection/jope-topic-selection.md).

# Worked Example: A JOPE-Style Introduction (before → after)

This demonstrates the **JOPE introduction arc** from `jope-writing-style`:
**population-economics question → why it matters for population outcomes or policy → setting and
design in a few sentences → headline result with a magnitude in demographic units → tempo vs quantum
stated → contribution relative to the frontier → honest institutional scope → brief roadmap** — with
the JOPE rules that the **abstract is at most 150 non-technical words stating the innovation and
contribution**, that **effects are reported in demographic units against the control mean**, and that
**external validity across institutional settings is stated honestly** (`jope-contribution-framing`,
`jope-writing-style`).

**Illustrative paper (fictional):** *"Leave to Stay: Paid Parental Leave and Second Births."*
Fictional setting: a high-income country that extended paid parental leave from 10 to 14 months for
children born on or after 1 July of a reform year. The reform is **invented for teaching** and is not a
real program. Real birth-date-cutoff leave reforms exist and have been studied (for example Lalive &
Zweimüller, QJE 2009, and Raute, JPubE 2019 — neither in JOPE); every number below is invented and
describes none of them.

---

## Before (buries the population-economics question — typical first-draft intro)

> The relationship between family policy and fertility has been studied extensively. Many papers
> examine parental leave, child benefits, and childcare. In this paper, we use a regression
> discontinuity design on the child's birth date, with bias-corrected confidence intervals, a density
> test, and a donut specification, to study the effects of a parental-leave extension. We assemble
> register data on all births and link them to employment histories. Fertility is an important topic
> for policymakers in ageing societies. Section 2 reviews the literature, Section 3 describes the data,
> Section 4 presents the empirical strategy, Section 5 reports results, and Section 6 concludes.

**What's wrong (against `jope-writing-style` / `jope-contribution-framing` / `jope-topic-selection`):**

- **Leads with method and inference machinery** ("regression discontinuity … bias-corrected … density
  test … donut") instead of the population-economics question — the named anti-pattern in
  `jope-identification-strategy` and `jope-writing-style`, and fatal in a 150-word abstract.
- **No finding and no magnitude.** The intro "names a topic but states no effect size"; no demographic
  unit appears.
- **Tempo vs quantum never addressed.** A reader cannot tell whether the paper is about timing or about
  completed fertility — the first question a JOPE referee asks.
- **No institutional detail.** How the leave works (duration, replacement rate, who is eligible) is the
  mechanism; it is missing.
- **Throat-clearing** ("has been studied extensively," "is an important topic") with vague stakes.
- **No stated contribution** relative to the frontier; an editor skimming for two minutes could not
  restate it.

---

## After (JOPE arc — question + demographic magnitude + tempo/quantum + institutional scope)

> **Does more generous paid parental leave raise the number of children families have, or only change
> when they have them?** Using a reform that extended paid leave from 10 to 14 months for children born
> on or after 1 July, and comparing mothers whose child was born just before and just after the cutoff,
> we find that the probability of a second birth within five years rises by 3.2 percentage points — about
> 6 percent of the control mean of 52 percent — and that the gap does not close over ten years.
> *(population-economics question + headline answer + demographic-unit magnitude against the control
> mean, in the first breath.)*
>
> The distinction matters for population policy. If leave only moves births earlier, cohort fertility is
> unchanged and the policy's demographic case rests on timing alone; if it raises completed fertility,
> leave generosity is a lever on the age structure that ageing societies are trying to shift. Which of
> the two holds depends on how leave interacts with the employment protection that makes a second
> birth affordable for working mothers. *(why it matters; tempo vs quantum posed as the stake; the
> mechanism stated before the design.)*
>
> The reform we study replaced 10 months of earnings-related leave with 14, at the same replacement
> rate, for employed mothers; eligibility depended only on the child's birth date. We use complete birth
> registers linked to employment records, test for birth-timing manipulation around the cutoff, exclude
> births within two weeks of it, and follow mothers for ten years. *(setting and design in a few
> sentences — institutional detail as mechanism; diagnostics named, not foregrounded.)*
>
> Four extra months of leave raised second births within five years by **3.2 percentage points** and
> within ten years by **2.9 points**, so the effect is a change in the number of children, not a shift
> in timing. Effects are concentrated among mothers in the lower half of the pre-birth earnings
> distribution, consistent with leave relaxing a budget constraint rather than a preference. At the
> reform's cost, this is roughly **X thousand euros per additional birth** (fictional), comparable to
> the cost per birth of child-benefit increases estimated elsewhere. *(headline result restated with
> the horizon that settles tempo vs quantum, the population for whom it binds, and a
> policy-comparable unit, per `jope-contribution-framing`.)*
>
> Our contribution is to show that **leave duration, holding the replacement rate fixed, moves
> completed fertility among employed mothers** — a quantum effect the timing-focused literature could
> not separate because it observed short horizons. *(contribution stated early, as one restatable
> sentence, relative to a specific prior view.)* The result is local to mothers in paid employment in a
> country with high leave coverage and strong job protection; where leave is unpaid or employment
> protection is weak, the budget-constraint channel may not operate. *(honest institutional scope —
> calibrated for an international readership, per `jope-writing-style` and `jope-topic-selection`.)*
>
> The paper proceeds as follows. Section 2 describes the reform and data; Section 3 presents the design,
> manipulation tests, and compliers; Section 4 reports effects on second births at five and ten years
> and the heterogeneity by earnings; Section 5 discusses cost per birth and scope. *(brief roadmap.)*

---

## Why the "after" meets the JOPE bar

Mapped to the skill checklists:

- **Finding with a number in demographic units** — 3.2 pp against a 52 percent control mean, and the
  ten-year horizon — appears immediately (`jope-writing-style`; `jope-contribution-framing`: effect in
  demographic units vs control mean).
- **Tempo vs quantum stated and settled** — the ten-year outcome is the evidence, not an assertion
  (`jope-contribution-framing`, `jope-identification-strategy`).
- **Question first, method demoted to a tool** — the RDD, density test, and donut are named only where
  the design is described, never as the lead, which also makes the 150-word abstract writable.
- **Institutional detail as mechanism** — leave duration, replacement rate, eligibility, job protection
  are part of the argument, as JOPE's international readership requires.
- **Contribution stated early and restatable** ("leave duration moves completed fertility among
  employed mothers"), not "we contribute to the literature."
- **Honest external validity** — local to employed mothers in a high-coverage, high-protection setting;
  explicitly not a universal elasticity.
- **Identification diagnostics signposted but not foregrounded** — manipulation test, donut, compliers,
  matching the `jope-identification-strategy` birth-date-RDD branch.

> Next: see [`../exemplars/library.md`](../exemplars/library.md) for verified **real** JOPE papers whose
> introductions execute this arc, and [`../code/`](../code/) for the runnable estimator chain — e.g. the
> RDD skeleton with the density test in [`../code/stata/05_rdd.do`](../code/stata/05_rdd.do) and the
> publication-grade plot in [`../code/python/event_study_plot.py`](../code/python/event_study_plot.py).

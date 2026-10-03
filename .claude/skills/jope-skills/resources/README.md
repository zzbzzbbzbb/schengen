# Journal of Population Economics — Resources

Capability layer for the **Journal of Population Economics** skill pack. The runnable code is vendored for
self-containment; the cross-cutting method guidance lives once in the shared
empirical-methods hub and is linked below.

## Contents

| Resource | What it gives an agent |
|---|---|
| [`code/`](code/) | Reproducible Stata + Python causal-inference skeleton (clean → descriptive → DiD/IV/RDD/DML → mechanism → robustness → tables). Adapted from the verified Economic-Research-Journal-Skills library (Stata 18 MP, 2026-06); copy-and-adapt, change no command blindly. Duration and competing-risks models are not in the skeleton; see `external_tools.md`. |
| [reviewer-objection-checklist](../_linked/shared-resources/empirical-methods/reviewer-objection-checklist.md) | The objections referees actually raise, by identification strategy (DiD / IV / RDD / DML / matching / mechanism), each with its preemption. Stress-test the design before drafting. |
| [reporting-standards](../_linked/shared-resources/empirical-methods/reporting-standards.md) | Modern inference + reporting table stakes: SE clustering, weak-IV diagnostics, multiple-testing, DiD/RDD reporting, reproducibility. |
| [execution-with-mcp](../_linked/shared-resources/empirical-methods/execution-with-mcp.md) | **Guidance → a fitted, audited result.** Maps each design family / reviewer objection to the concrete StatsPAI / Stata MCP tools in this environment, so this pack's identification / analysis skills *run* the modern DiD / weak-IV-robust CI / density test / multiple-testing correction and report the number. |
| [`official-source-map.md`](official-source-map.md) | Venue-specific facts (abstract cap, editors, desk-screen statistics, data policy, submission system) with sourcing discipline and a verification status for each fact. |
| [`external_tools.md`](external_tools.md) | Population-economics data sources (registers, household panels, HFD/HMD, IPUMS, DHS) and Stata/R/Python packages, including duration and APC tools. |
| [`worked-examples/01-introduction.md`](worked-examples/01-introduction.md) | See a before→after rewrite of a population-economics paper introduction in JOPE house style (economics-demography question → demographic-unit magnitude → tempo/quantum → contribution → honest scope). Illustrative fictional paper. |
| [`exemplars/library.md`](exemplars/library.md) | Benchmark against **real, web-verified JOPE papers** (including recent Kuznets Prize winners) organized by method × topic, with a sibling-confusion guardrail. Design positioning only — no fabricated numbers. |

## How to use

1. **Before drafting tables** — run the design against the reviewer-objection checklist; every objection you cannot answer in one paragraph + one exhibit is a hole. For population economics add the selection-into-the-event, birth-timing-manipulation, and tempo/quantum questions from the pack's identification skill.
2. **When building results** — adapt `code/` to your data; keep the modern-estimator chain (heterogeneity-robust DiD, weak-IV-robust IV, bias-corrected RDD with a density test).
3. **Before submission** — walk the reporting-standards inference audit and this pack's `official-source-map.md` for venue limits, above all the 150-word non-technical abstract.

> Method guidance here is venue-neutral; always defer to this pack's skills and
> `official-source-map.md` for what *this* journal specifically requires.

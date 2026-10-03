---
name: jope-replication-and-data-policy
description: Use when assembling the data-availability statement and the data/code package for a Journal of Population Economics (JOPE) submission or accepted paper — Springer Nature research-data policy, restricted register and survey data, repository choice. Builds the package; it does not run the analysis.
---

# Replication & Data Policy (jope-replication-and-data-policy)

## When to trigger

- A paper is heading toward submission and the replication package or data-availability statement is not written
- The data are restricted (Nordic registers, SOEP, NLSY geocodes, census research-data-center files) and you need a compliant path
- You are unsure what JOPE and Springer require and when
- You want to pre-empt a referee or editor asking for code

## JOPE's policy (what was verifiable)

JOPE is a Springer journal and follows **Springer Nature's research-data policy**: authors are asked to
ensure that **all data and materials, software applications, and custom code support their published
claims** and comply with field standards; authors are **strongly encouraged to deposit supporting data
in a publicly available repository** under a licence permitting reuse; and the **Declarations** block of
the manuscript carries a **data-availability statement** alongside funding and competing-interest
statements. The statement should name a real repository, not a placeholder, or explain why data cannot
be shared.

Not located in the latest refresh (verify on the live submission guidelines before relying on it):
whether JOPE requires a code deposit at acceptance, whether it runs a replication check, and whether a
journal-managed archive exists. Treat the package as a referee-facing deliverable regardless — a
reviewer can ask for it, and a reproducible package is the cheapest credibility you can buy.

## Build the package as you go

- **One master script** (`run_all` / `00_master`) that regenerates every table and figure, in order,
  from raw or constructed data.
- **A README** documenting data provenance and access path, every construction and sample-selection
  step with counts, software and package versions, run time, seeds, and which script produces which exhibit.
- **Pinned environment:** Stata `ssc` versions, `renv.lock`, or `requirements.txt`; all random seeds
  (bootstrap, randomization inference, simulation) set and reported.
- **Self-contained:** relative paths, no machine-specific dependencies, no hand edits to outputs.

## Restricted data (the normal case in population economics)

Most JOPE empirical work uses data that cannot be redistributed: register data accessed remotely
through national statistical offices, household panels under contract (SOEP, HILDA, Understanding
Society), restricted geocoded surveys, census research-data-center extracts, DHS or IPUMS data under
terms of use. In that case:

- Provide **all programs** and a precise, documented **access path** (which office, which application,
  which dataset version) so another researcher can obtain the data and rerun the code.
- Disclose the restriction in the data-availability statement and the README rather than omitting data silently.
- Deposit a **synthetic or de-identified test extract** that exercises the code end to end where the
  data provider allows.
- Cite the dataset itself (DOI or version) in the reference list where the provider requires it.

## Data-status routing table

| Data in the paper                                   | What the JOPE package must contain                                   |
|-----------------------------------------------------|----------------------------------------------------------------------|
| Author-collected survey or experiment                | De-identified microdata + master script + instruments                |
| Register data via remote access (Nordic, Dutch, Austrian) | All programs + access path + synthetic test extract              |
| Contracted household panel (SOEP, HILDA, PSID restricted) | Programs + dataset version/DOI + access instructions; data withheld |
| Public microdata (IPUMS, DHS, EU-SILC, CPS/ACS)      | Download script or pinned extract definition + every cleaning step   |
| Aggregate data (HFD, HMD, WPP, Eurostat, OECD)       | Snapshot with access date + construction code                        |

## Worked micro-example (illustrative)

Hypothetical: a parental-leave RDD on register-linked birth records accessed through a national
statistics office's remote server.

- **Deposit shape:** `run_all.do` regenerates all 5 tables and 4 figures; `/code` holds every script;
  `/synthetic` holds a simulated birth-record extract with the same variable names so the pipeline runs
  end to end; `README.md` names the register tables, the data-access application route, and the
  software versions; seeds for the bootstrap p-values are set and printed.
- **Data-availability statement:** "The register data are held by [office] and accessed under
  agreement [ref]; they cannot be redistributed. All code and a synthetic extract are deposited at
  [repository DOI]; the README documents the access route." File counts are *illustrative*.

## Referee / editor pushback

- *"Please share the code so I can check the density test."* → the package is staged at submission, not
  promised for acceptance.
- *"Your Table 3 will not reproduce — which script makes it?"* → the README maps each exhibit to its script.
- *"You cite restricted data and share nothing."* → withholding restricted data is fine; withholding the
  programs and access path is not.

## Anti-patterns

- A data-availability statement that says "available on request" with no repository and no access path
- A code dump with no README and no master script
- Hand-edited tables the code does not reproduce
- Unset seeds, so bootstrap or randomization-inference results shift on rerun
- Dataset versions unrecorded (panel releases change; register extracts are refreshed)

## Output format

```
【Master script regenerates all exhibits?】[Y/N]
【README】provenance + access path + steps + versions + seeds? [Y/N]
【Environment pinned】[Stata/R/Python versions]
【Data status】public / contracted / register (+ access path + dataset version)
【Data-availability statement】names repository or explains restriction? [Y/N]
【Synthetic extract deposited?】[Y/N/NA]
【Next step】jope-review-process
```

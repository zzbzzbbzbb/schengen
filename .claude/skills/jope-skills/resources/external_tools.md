# External Tools & Resources for JOPE-Style Population Economics

Data sources, software, and packages useful when preparing a *Journal of Population Economics*
(JOPE) submission — theoretical and applied work on the relationships between economic and demographic
problems, with credible identification against selection into demographic events (policy reforms,
birth-date and age cutoffs, natural experiments, shift-share migration designs), demographic
measurement done properly (cohorts, censoring, weights), a 150-word non-technical abstract, and a
reproducible package with a data-availability statement. Check licenses and current access terms.

## 1. Data sources (population-economics emphasis)

### Household panels and longitudinal surveys
| Source | Provider | Typical use |
|--------|----------|-------------|
| SOEP (German Socio-Economic Panel) | DIW Berlin | Fertility, partnership, migration, wellbeing; contracted access |
| HILDA | Melbourne Institute | Australian household dynamics, gender, bargaining |
| PSID / NLSY79 / NLSY97 / NLSY-CYA | Michigan / BLS | US family formation, intergenerational outcomes |
| Understanding Society / BHPS | ISER Essex | UK household and family dynamics |
| SHARE / HRS / ELSA / CHARLS | Various | Ageing, retirement, intergenerational transfers, health |
| Generations and Gender Programme (GGP) | GGP consortium | Fertility intentions, partnership histories, cross-national |
| Add Health; NSFG | UNC / CDC | Youth transitions; US fertility and family |

### Registers and census microdata
| Source | Provider | Typical use |
|--------|----------|-------------|
| Nordic population registers (Denmark, Sweden, Norway, Finland) | National statistical offices (remote access) | Birth-date RDDs, full-population event studies, intergenerational links |
| Dutch CBS microdata; Austrian ASSD | CBS / ASSD | Register-based family and labor outcomes |
| IPUMS International / IPUMS USA / IPUMS CPS | U. Minnesota | Harmonized census and survey microdata; historical linkage (MLP) |
| EU-SILC / EU-LFS; ACS / CPS | Eurostat / Census Bureau | Household structure, migration status, labor supply |
| Census research data centers (US FSRDC, UK SRS, German FDZ) | National agencies | Restricted linked data |

### Demographic aggregates
| Source | Provider | Typical use |
|--------|----------|-------------|
| Human Fertility Database (HFD); Human Mortality Database (HMD) | MPIDR / VID / Berkeley | Cohort and period fertility, life tables, tempo adjustment |
| UN World Population Prospects | UN DESA | Cross-country population structure, projections |
| Eurostat population and migration statistics; OECD Family Database; OECD DIOC | Eurostat / OECD | Family policy indicators, migrant stocks by education |
| DHS; MICS; NFHS | USAID / UNICEF / India | Fertility, child mortality, sex ratios in low- and middle-income countries |
| Guttmacher Institute; CDC abortion surveillance | Guttmacher / CDC | Abortion access and incidence |
| Mexican Migration Project; UN DESA migrant stocks | Princeton–Guadalajara / UN | Migration flows and selection |

### Preprint series tied to the JOPE community
| Series | Note |
|--------|------|
| GLO Discussion Papers | Global Labor Organization's series; GLO co-publishes JOPE |
| IZA Discussion Papers | Institute of Labor Economics; population and labor economics |

## 2. Statistical software

### Stata
- DID / event study: `csdid` (Callaway–Sant'Anna), `eventstudyinteract` (Sun–Abraham), `did_multiplegt_dyn` (de Chaisemartin–D'Haultfœuille), `did_imputation` (Borusyak–Jaravel–Spiess), `bacondecomp`
- IV: `ivreg2`, `ivreghdfe`, `weakivtest`, `weakiv`
- RDD at birth-date / age cutoffs: `rdrobust`, `rddensity`, `rdbwselect`
- Duration / hazard: `stcox`, `streg`, `stcrreg` (competing risks), discrete-time hazards via `logit` / `cloglog` on person-periods; frailty options
- Survey design: `svyset`, `svy:` prefix; weights for panels
- Inference: `boottest` (wild-cluster bootstrap), `ritest`, `rwolf` / `wyoung` (multiple testing)
- Fixed effects at scale: `reghdfe`
- Age-period-cohort: `apc_ie`, `apcd` (community-contributed; state the constraint)

### R
- DID / event study: `did`, `fixest` (`sunab`), `didimputation`, `bacondecomp`, `HonestDiD`
- RDD: `rdrobust`, `rddensity`, `rdlocrand`
- Duration: `survival`, `cmprsk`, `flexsurv`, `coxme`; `Epi` (Lexis diagrams)
- Demography: `HMDHFDplus` (HMD/HFD access), `demography`, `popReconstruct`
- Survey weights: `survey`, `srvyr`
- Inference: `fwildclusterboot`, `sandwich` / `clubSandwich`, `multcomp`
- Reproducibility: `renv`, `targets`

### Python
- `pandas`, `numpy` — data wrangling
- `statsmodels`, `linearmodels` — estimation; `lifelines` — survival analysis
- `rdrobust` (Python port), `doubleml`, `econml`
- `matplotlib` / `seaborn` — figures; `binsreg` for binscatter
- `pip freeze` / `requirements.txt` — pin the environment

## 3. Identification toolkit by design

| Design | Core checks | Packages |
|--------|-------------|----------|
| Policy-reform DID / event study | Goodman-Bacon decomposition, modern estimator, leads, conception-lag timing, few-cluster inference | `csdid`, `did`, `did_multiplegt_dyn`, `fixest`, `boottest` |
| Birth-date / age RDD | Density test at the cutoff (birth-timing manipulation), donut, placebo-year cutoff, bandwidth sweep | `rdrobust`, `rddensity` |
| Twins / sex-composition IV | First-stage F, weak-IV-robust CI, exclusion in three registers, complier description | `ivreg2`, `weakiv`, `linearmodels` |
| Shift-share / enclave (migration) | Shares vs shocks statement, Rotemberg weights, pre-period balance | `bartik_weight` (Stata), `ShiftShareSE` (R) |
| Event study around births / unions | Pseudo-event controls, age-cohort controls, long horizon, reform cross-check | `fixest`, `reghdfe` |
| Fertility / mortality duration | Censoring rule, competing risks, frailty, cohort window | `stcox`, `stcrreg`, `survival`, `cmprsk` |
| Age-period-cohort | Identification constraint stated; robustness to alternatives | `apc_ie`, `Epi` |

## 4. Figures (JOPE rewards demographic pictures)
- Event-time plots around births or moves; RD plots with density panels; survival and cumulative-hazard
  curves; age and cohort profiles with eligibility ages marked; Lexis-style cohort diagrams; maps for
  migration exposure
- Confidence bands shown; control mean printed; grayscale-legible; vector output (EPS/PDF)
- Figures as separate files, tables editable, captions in the text (Springer delivery)

## 5. Reproducibility & data policy
- Pin software and package versions; one master script regenerating every exhibit; seeds set and reported
- README mapping each exhibit to its script, with data provenance, dataset version, and access route
- **Data-availability statement** in the Declarations naming a repository (Zenodo, OSF, Harvard
  Dataverse, openICPSR, GESIS) or explaining the restriction and access path
- For register and contracted panel data, deposit all programs and a synthetic extract; cite the dataset

## 6. Writing & references
- **Abstract ≤ 150 words, non-technical, stating innovation and contribution** — the venue's hard rule
- Reference managers: Zotero, BibTeX/BibLaTeX, EndNote — Springer author-year style for this journal
  (confirm the style file on the live submission guidelines)
- American or British English, used consistently
- Typesetting: LaTeX (Springer's class files are optional) or Word; editable source required

## 7. Process & portal
| Item | Note |
|------|------|
| Submission portal | Editorial Manager — editorialmanager.com/jope |
| Editorial office | POP at UNU-MERIT, Maastricht — JOPE-Office@glabor.org |
| Submission fee | None located (verify) |
| Open access | Hybrid (Open Choice); APC only if chosen after acceptance; transformative agreements may cover it |
| Review model | Not verified in this refresh — read the live "Peer review" section |
| Desk screen | Desk-rejection policy since 2013; first decisions within weeks |
| Special collections | Continuously open; named collections get "particular interest and speedy handling" |
| Prize | Kuznets Prize for the best article in the journal, awarded at the GLO-JOPE Global Conference |
| Publisher | Springer, in cooperation with POP at UNU-MERIT and GLO |

## 8. Cautions
1. **Verify volatile specifics** (review model, fee, APC, editors, collections, reference style) on the official pages — they change, and several were not directly readable in the latest refresh.
2. **Respect data contracts**; register and panel microdata require formal access, but the programs must still be shared.
3. **Match estimator to design** — plain TWFE on staggered reforms and RDDs without density tests at birth-date cutoffs are known pitfalls here.
4. **Say which demographic quantity you estimate** — tempo vs quantum, period vs cohort, flow vs stock.
5. **Count the abstract** — 150 words, non-technical, every time.

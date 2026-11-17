# Sources Map — Paper 5: The Testability Atlas

Author: Atharva Chourey
Affiliation: Atharva Chourey Lab (independent research lab)

*Manuscript in preparation — not yet peer-reviewed.*

This file maps every key number, verdict and reference in `paper.md` to the source file it was taken from. Nothing in the paper was taken from a source outside this list. Where a source gives a verdict without a number, the paper reports the verdict without a number.

## Primary sources

- `~/workspace/india-gov-data-patterns/ATLAS.md` — build report, dated 2026-11-17. Headline counts (§1), verdict grid (§2), surprising cells (§3), per-series audit summaries (§4), honest gaps and deviations (§5), file list (§6).
- `~/workspace/india-gov-data-patterns/ATLAS_PREREGISTRATION.md` — pre-registration, registered 2026-11-17. Language rule (§0), grid and applicability (§1), ruler rules R1–R6 (§2), MDES machinery (§3), cell designs, inputs and anchors (§4), audit schema and metadata (§5), sources verified for the registration (§7).
- `~/workspace/india-gov-data-patterns/data/atlas_summary.json` — computed summary. Verdict counts, graded/NA counts, all spectral and regression MDES values at full precision.
- `~/workspace/india-gov-data-patterns/data/atlas_grid.csv` — 82-row machine-readable grid. Per-row verdict, MDES, anchor, clean n/span, reason and MDES detail for every graded and NA row.
- `~/workspace/india-gov-data-patterns/scripts/atlas.py` — re-runnable computation. Spectral injection implementation, regression formulas, audit table contents, grid construction, figure generation.
- `~/workspace/india-gov-data-patterns/figures/fig_atlas_heatmap.png`, `figures/fig_atlas_spans.png` — the two Atlas figures described (not reproduced) in §3.1 of the paper.
- `~/workspace/papers/precedent-sweep/SWEEP.md` — precedent sweep, run 2026-11-17, §P5 and Manager Summary item 7. Binding rescope for the novelty claim; precedents Ioannidis et al. (2017) and Tomlinson (1993/2013).

## Context-only sources (skimmed; no results imported)

- `~/workspace/famine-1900-patterns/REPORT.md` — skimmed for context only, per brief. No number or result from this file is used in the paper.
- `~/workspace/india-historical-stats/REPORT.md` — skimmed for context only, per brief. No number or result from this file is used in the paper. The paper cites the relationship between the Atlas and other builds only as `ATLAS.md` / `ATLAS_PREREGISTRATION.md` themselves state it (pilot reuse; CGWB row existing because the series powers the future Shah build, ASSESSMENT §B).

## Key numbers and their sources

| Claim in paper | Value | Source file |
|---|---|---|
| Questions graded | 23 | ATLAS.md §1; atlas_summary.json (`graded_cells: 23`); atlas_grid.csv (23 rows with applicable = yes) |
| Verdict split | 4 testable / 11 underpowered / 8 untestable | ATLAS.md §1 table; atlas_summary.json (`verdict_counts`) |
| Shares of graded | 17% / 48% / 35% | ATLAS.md §1 table |
| Questions not answerable at literature-sized effects | 19 of 23 | ATLAS.md §1 |
| Grid size | 10 series × 8 tests = 80 pairs; 21 graded pairs → 23 graded rows; 82 grid rows; 59 NA | ATLAS.md §1, §5.1; ATLAS_PREREGISTRATION.md §1; atlas_summary.json (`na_cells: 59`); atlas_grid.csv (82 rows) |
| Registration NA-count erratum | Registration said 57 NA; correct count 59 | ATLAS.md §5.1 |
| Common settings | α = 0.05, power 0.80, multiplier 2.802 = 1.960 + 0.842 | ATLAS_PREREGISTRATION.md §3 |
| Monsoon anchor | 0.47 sd (10% variance share) | ATLAS_PREREGISTRATION.md §3a; ATLAS.md §2 |
| Business-cycle anchor | 0.59 sd (15% variance share) | ATLAS_PREREGISTRATION.md §3a; ATLAS.md §2 |
| Monsoon ENSO MDES / verdict | IMD 0.69 / IITM 0.68 sd; joint Underpowered | ATLAS.md §2 (full precision 0.685 / 0.684 in atlas_grid.csv and atlas_summary.json) |
| Monsoon solar MDES / verdict | IMD 0.56 / IITM 0.46 sd; joint Underpowered; IITM alone Testable | ATLAS.md §§2–3; atlas_summary.json |
| Monsoon long MDES / verdict | IMD 0.55 / IITM 0.43 sd; joint Underpowered; IITM alone Testable | ATLAS.md §§2–3; atlas_summary.json |
| Monsoon clean spans | IMD 125 yrs (1901–2025); IITM 146 yrs (1871–2016) | ATLAS.md §§2, 4 |
| IMD–IITM gap (identical years 1901–2016) | 887.3 mm vs 843.6 mm (+5.2%); r = 0.947 | ATLAS.md §4 (pilot values) |
| Monsoon persistence | IMD ρ +0.03; IITM ρ −0.10 (sign depends on ruler) | ATLAS.md §4; atlas.py (`run_spec` inputs 0.031 / −0.100) |
| ENSO detectable floor | ~19% of variance | ATLAS.md §3.6; atlas_summary.json (varshare 0.19) |
| GDP Kitchin | MDES 1.04 sd (35% var); Underpowered; 58 qtrs | ATLAS.md §2; atlas_summary.json (1.042, varshare 0.352) |
| GDP Juglar | Untestable, span rule; 58 qtrs = 14.5 yr < 22 yr | ATLAS.md §2; atlas_grid.csv |
| GDP two-ruler growth gap | FY2023-24: 9.2% (2011-12 base) vs 7.2% (2022-23 base); FY2024-25: 6.5% vs 7.1% | ATLAS.md §4; ATLAS_PREREGISTRATION.md §7 |
| GDP audit facts | Clean span 58 qtrs on 2011-12 base; three bases spliced; new base covers 2022-23–2025-26, back series pending (expected Dec 2026); IMF Article IV grade "C" (2024/2025) | ATLAS.md §4; ATLAS_PREREGISTRATION.md §§5, 7 |
| Beta convergence | Testable; MDES 1.21 %/yr vs anchor 1.5 %/yr (Cashin & Sahay); 28 states, 13-yr difference | ATLAS.md §2; atlas_summary.json (`mdes_lambda_pct` 1.2106) |
| Sigma sub-grade (not counted in the 23) | Underpowered; MDES 0.0030 log-pts/yr vs drift 0.001–0.003/yr; 13 annual points | ATLAS.md §2 (listed as sub-grade row); atlas_grid.csv T7 reason; atlas_summary.json |
| IIP Kitchin / Juglar | 0.43 sd Underpowered (span-capped) / Juglar Untestable, 0.36 sd for the record; 167 months growth; 13.9 yr | ATLAS.md §2; atlas_grid.csv; atlas_summary.json. Audit clean index span n = 168 (ATLAS.md §4; atlas.py) vs graded growth n = 167 — both reported as their sources state them |
| CPI Kitchin / Juglar | 0.75 sd Underpowered / Untestable (span rule); 180 months, base 2012; 15.0 yr | ATLAS.md §2 |
| CPI Phillips | MDES 0.29 pp/pp vs anchor 0.25; Underpowered; 58 joint quarters | ATLAS.md §2; atlas_summary.json (0.289) |
| Taylor / r* | Untestable; 58 clean qtrs vs ≥100-qtr structural floor (≥160 for Testable); RBI published r* 1.4–1.9% | ATLAS.md §§2–3; ATLAS_PREREGISTRATION.md §3c |
| WPI Kitchin / Juglar / Phillips | 0.70 sd Underpowered / Untestable (span rule) / Phillips 0.39 vs 0.25 Underpowered; 169 months; 14.1 yr; 58 joint quarters | ATLAS.md §2; atlas_summary.json (WPI Phillips 0.394) |
| Bank credit Kitchin / Juglar | Testable 0.50 sd / Underpowered 0.47 sd (span-capped); 272 months, Mar 2003–Oct 2025; 22.7 yr | ATLAS.md §2 |
| Bank credit stability | Definition stable since Nov 1960 (RBI Handbook notes); breaks are coverage events | ATLAS.md §4; atlas.py audit row S6 |
| Trade Kitchin / Juglar | Testable 0.42 sd / Underpowered 0.37 sd (span-capped); 312 months, Apr 2000–Mar 2026; 26.0 yr | ATLAS.md §2 |
| Political budget cycle | Testable; MDES 0.20 pp of GSDP vs anchor 0.25 pp; 952 state-yrs, n_eff 359; deficit MDES 0.29 pp vs anchor 0.50 pp | ATLAS.md §§2–3; atlas_summary.json (primary 0.1998, deficit 0.2906, n_eff 359.25) |
| PLFS Kitchin / Juglar | Both Untestable, span rule; longest span 6.0 yr | ATLAS.md §2; atlas_grid.csv |
| PLFS Okun | Untestable by minimum-n rule; formula MDES 0.16 for the record vs anchor 0.30; n = 7 annual | ATLAS.md §§2–3; atlas_summary.json (0.1589) |
| PLFS audit facts | Launched Apr 2017; EUS officially "not comparable"; annual clean span 2017-18–2023-24 (7 points); redesigned Jan 2025; monthly CWS from Apr 2025 | ATLAS.md §4; ATLAS_PREREGISTRATION.md §§4–5 |
| CPI audit facts | Exists from Jan 2011; clean Jan 2011–Dec 2025, base 2012; Jan 2026 revision 2.75% → 2.74%; linking factor 0.5267; food weight 45.86% → 36.75% on base 2024; YoY comparable only from Jan 2026 | ATLAS.md §4; ATLAS_PREREGISTRATION.md §§5, 7 |
| Assumed ρ inputs | GDP 0.35, CPI 0.50, WPI 0.45, credit 0.30, trade 0.15 | ATLAS.md §5.2; ATLAS_PREREGISTRATION.md §4 |
| Boundary-adjacent verdicts | Phillips–CPI (0.29 vs 0.25), beta convergence (1.21 vs 1.5), PBC capital outlay (0.20 vs 0.25); within ~25% of a boundary | ATLAS.md §5.2 |
| Spectral implementation | 2,000 AR(1) surrogates, seed 42; injection 200 trials/amplitude, seed 43, random phase; amplitudes 0.10–1.20 sd; periodogram checked vs scipy (<1% band-max agreement) | ATLAS_PREREGISTRATION.md §3a; ATLAS.md §5.5–5.6; atlas.py |
| CGWB groundwater | NA on all 8 tests; waves 2009, 2013, 2017, 2020, 2022–2025; GEC-97 → GEC-2015 break at 2017; 6 like-for-like waves | ATLAS.md §§2, 4; ATLAS_PREREGISTRATION.md §1 |
| Pre-registration | Registered 2026-11-17; git commit `4167fc2` as recorded in ATLAS.md; pilot git `171929d` as recorded in ATLAS_PREREGISTRATION.md | ATLAS.md header; ATLAS_PREREGISTRATION.md header |
| Ioannidis et al. precedent scale | 159 empirical economics literatures surveyed (paper text); sweep also records 64,076 estimates, over 6,700 studies, median power 18% or less (not all used in paper text) | SWEEP.md §P5a |
| Tomlinson precedent wording | Colonial data "misleading, deceptive or partial"; quantitative attempts at definitive answers "have convinced few sceptics" (questions listed in sweep) | SWEEP.md §P5a |

## References in the paper — provenance

- Cashin & Sahay (1996), Khemani (2004, *Journal of Development Economics* 73:125–154 — pages as given in ATLAS_PREREGISTRATION.md §7), Kane (1990), Kapur & Patra (2003), Patra et al. (2015-16): all as cited in ATLAS_PREREGISTRATION.md §§3–4, 7. No DOI, page range or publisher has been added where the source materials do not give one; Kane (1990) is flagged in the paper's reference list as incompletely specified in the sources.
- Ioannidis, Stanley & Doucouliagos (2017), *The Economic Journal* 127(605): F236–F265, DOI 10.1111/ecoj.12461: as given in SWEEP.md §P5a. (DOI recorded here from the sweep; the paper's reference list does not print a DOI.)
- Tomlinson, *The Economy of Modern India* (1st ed. 1993; 2nd ed. Cambridge, 2013): as given in SWEEP.md §P5a.
- Maddison / Maddison Project Database: mentioned in SWEEP.md §P5a only as validation data. The Atlas files themselves do not cite Maddison, so Maddison is **not** cited as a source for any number in the paper.
- Broadberry & Gupta: checked in SWEEP.md §P5a and found not to be a prior for the grading; not cited in the paper.
- Official sources (MoSPI/NSO, RBI, OEA/DPIIT, DGCIS, IMD, IITM, CGWB, IMF Article IV): as named in ATLAS_PREREGISTRATION.md §7 and the atlas.py audit rows. No specific release numbers, DOIs or page numbers beyond those in the sources have been added.

## NOVELTY CLAIMS — SWEEP-ADOPTED

Precedent sweep verdict for this paper (P5a): **NARROWED**. Sweep detail: `~/workspace/papers/precedent-sweep/SWEEP.md` §P5.

Surviving claim, in the exact rescoped wording adopted in the paper (§1):

> "the first question-level testability/power grading scoped specifically to Indian historical statistics, applying an established method to 23 standard questions"

Marked: **SWEEP-ADOPTED**.

Claims explicitly **not** made, following the sweep:

- No claim to the testability/power-grading method itself. Precedent: Ioannidis, Stanley & Doucouliagos (2017) established field-scale power grading in economics (159 literatures; grades published estimates/literatures, not questions; not scoped to India or historical statistics).
- No claim to India-undecidability arguments in general. Precedent: Tomlinson (1993; 2nd ed. 2013) already argued qualitatively that colonial Indian data are misleading, deceptive or partial and that quantitative attempts at definitive answers to old questions have convinced few sceptics.
- No claim of "first power audit in economics" and no claim of "first claim that Indian historical data cannot decide old questions" — both formulations are expressly disavowed in the paper's §1.
- No other "first", "novel" or priority claim appears in the paper. The words "first" in the paper occur only in (a) the rescoped claim above, (b) its disavowals, and (c) non-novelty uses (e.g. "first pattern", "first, Okun's law…") that assert no priority.

## Numbers the brief asked about that were checked

- 23 graded, 4 / 11 / 8 split: **found and verified** in ATLAS.md §1 and atlas_summary.json.
- Full 23-question table with MDES, anchors and clean spans: **found** in ATLAS.md §2 and atlas_grid.csv; reproduced in the paper's Table 1.
- Flagship examples named by the Atlas itself (groundwater / Shah build; political budget cycle design inversion; Okun minimum-n trap; r*): **found** in ATLAS.md §§3–4 and used only as presented there.
- No brief number was missing. One counting subtlety was found and flagged in the paper (§§2.1, 3.1): the sigma-convergence sub-grade is listed as a row in ATLAS.md §2 but is a sub-grade inside the T7 cell in atlas_grid.csv and is **not** counted in the 23; counting it would give a spurious 24 rows and a 12th underpowered verdict.

## Gaps flagged in the paper

These are stated in the paper itself (§§4.2–4.3, Data & Code Availability) and are reproduced here for the parent agent:

1. Assumed (not measured) ρ/σ inputs for GDP, CPI, WPI, credit, trade and all regression cells; three verdicts within ~25% of a boundary could move under measured inputs (ATLAS.md §5.2).
2. Cross-ruler gaps measured for one pair only (monsoon), documented for one more (GDP); IIP and CPI overlap gaps not extracted — pending D-grade work (ATLAS.md §5.3).
3. Revision behaviour documented-only throughout; every systematic revision magnitude is pending D (ATLAS.md §5.4).
4. Spectral MDES grades the registered periodogram test, not sharper methods such as Kane's MESA (ATLAS.md §5.5).
5. Grid scope is a registered choice: questions outside the 10 × 8 grid are ungraded, not untestable.
6. Rubric thresholds are pre-registered conventions; a different registered threshold set would give a different split.
7. COVID observations retained by rule R6; the convergence long difference contains COVID and the Okun formula value is a COVID leverage artefact.
8. Kane (1990) reference is incompletely specified in the source materials; the paper flags this rather than inventing bibliographic details.
9. Source build is local and unpublished at the time of writing; the Data & Code Availability statement describes the files and their reproducibility, and makes no repository claim.

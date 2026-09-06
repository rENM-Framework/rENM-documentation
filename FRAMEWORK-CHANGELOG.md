# rENM Framework Changelog

This file tracks **Framework-level** versions. Each rENM package (`rENM`, `rENM.core`, `rENM.data`, `rENM.model`, `rENM.analysis`, `rENM.ai`, `rENM.reports`) is versioned and released independently, with its own `NEWS.md` and its own Zenodo DOI. A "Framework version" here is a specific, tested combination of those package versions — the combination that a paper, a report, or a user cites as "rENM Framework vX.Y.Z."

For package-level detail (what changed inside a single package and why), see that package's `NEWS.md`. This file only records which combination shipped together, and what that combination means for reproducibility.

---

## v0.1.0 — 2026 (bioRxiv preprint; submitted to PLOS One, review in progress)

Initial public release. Described in:

- Schnase, John L., Mark L. Carroll, Paul M. Montesano, and Virginia A. Seamster. "The rENM Framework: A Modular System for Reconstructing and Analyzing Long-Term Ecological Niche Dynamics." Preprint, bioRxiv, August 7, 2026. <https://doi.org/10.64898/2026.08.06.741224>. Submitted to PLOS One; review in progress.

Archived and citable as a set through the [rENM Framework Zenodo Community](https://zenodo.org/communities/renm-framework/records).

| Package          | Version | Git tag  | DOI                                                                  | Released     |
| ---------------- | ------- | -------- | --------------------------------------------------------------------- | ------------ |
| `rENM`           | 0.1.0   | `v0.1.0` | [10.5281/zenodo.20785160](https://doi.org/10.5281/zenodo.20785160)    | Jun 21, 2026 |
| `rENM.core`      | 0.1.0   | `v0.1.0` | [10.5281/zenodo.20787447](https://doi.org/10.5281/zenodo.20787447)    | Jun 21, 2026 |
| `rENM.data`      | 0.1.0   | `v0.1.0` | [10.5281/zenodo.20789477](https://doi.org/10.5281/zenodo.20789477)    | Jun 21, 2026 |
| `rENM.model`     | 0.1.0   | `v0.1.0` | [10.5281/zenodo.20797840](https://doi.org/10.5281/zenodo.20797840)    | Jun 22, 2026 |
| `rENM.analysis`  | 0.1.0   | `v0.1.0` | [10.5281/zenodo.20798280](https://doi.org/10.5281/zenodo.20798280)    | Jun 22, 2026 |
| `rENM.ai`        | 0.1.0   | `v0.1.0` | [10.5281/zenodo.20798613](https://doi.org/10.5281/zenodo.20798613)    | Jun 22, 2026 |
| `rENM.reports`   | 0.1.0   | `v0.1.0` | [10.5281/zenodo.20798788](https://doi.org/10.5281/zenodo.20798788)    | Jun 22, 2026 |

Example reports and example runs (CASP, GRRO, BCRF) distributed with this release are archived at:

- Reports: [zenodo.org/records/20750861](https://zenodo.org/records/20750861)
- Runs: [zenodo.org/records/20762105](https://zenodo.org/records/20762105)

**Reproducibility note:** results in the bioRxiv preprint and the PLOS One submission were generated with this exact combination. To reproduce them, install these tagged versions, not `main`. See the pinned installation instructions in the [org README](https://github.com/rENM-Framework).

---

## v0.2.0 — in progress, unreleased

Work has begun on corrections and improvements to the v0.1.0 codebase, tracked collectively as v0.2.0. This section is a placeholder until a coherent, tagged set of package versions is ready to be released together. Fill in below as each package is tagged.

| Package          | Version | Git tag  | DOI              |
| ---------------- | ------- | -------- | ---------------- |
| `rENM`           | TBD     | TBD      | TBD              |
| `rENM.core`      | TBD     | TBD      | TBD              |
| `rENM.data`      | TBD     | TBD      | TBD              |
| `rENM.model`     | TBD     | TBD      | TBD              |
| `rENM.analysis`  | TBD     | TBD      | TBD              |
| `rENM.ai`        | TBD     | TBD      | TBD              |
| `rENM.reports`   | TBD     | TBD      | TBD              |

Summary of changes since v0.1.0 (from each package's `NEWS.md`; not yet tagged as a Framework release):

- **`rENM.core`** — added `check_species()`, an audit function for the species metadata table. `get_species_info()` no longer requires or returns an `EBD.RANGE` column and its console output is now left-justified; the returned object is still a plain data frame.
- **`rENM.data`** — `find_occurrence_extent()`'s default `bbox_pct` changed from 99 to 90, and occurrence records are now restricted to a continental-US bounding box before that percentile extent is computed. This changes the spatial extent used to crop predictors for any run using the default settings.
- **`rENM.model`** — one compatibility patch (fixes an R 4.6.0 `"invalid 'scipen'"` crash in `create_ensemble_model()`), currently recorded under the `0.1.0` heading in `NEWS.md` rather than a new version section.
- **`rENM.analysis`** — fixed `create_state_trend_analysis()` and `create_hot_spot_map()`, which could error or silently include states with no real raster coverage when a species' modeled extent is smaller than its GAP range polygon. State-level statistics for affected species may change.
- **`rENM.ai`** — no changes.
- **`rENM.reports`** — added a `top_states` filter to the state summary table (default preserves prior behavior). `assemble_final_report()` was substantially rewritten: page numbering now uses `cpdf` instead of a raster overlay, pages are normalized to letter size, an optional `.docx` output was added, and the function's return value changed from a single path to a vector of paths.
- **`rENM`** — default extent determination now calls `find_occurrence_extent()` (matching the `rENM.data` change above).

<!--
When filling in this section: pull the high-level points from each package's
NEWS.md rather than duplicating detail here; keep the summary to a few
sentences and link out to the relevant NEWS.md entries.
-->

Affects a result, figure, or number reported in the v0.1.0 / bioRxiv paper: **Possibly — needs confirmation.** The `rENM.data` extent default change and the `rENM.analysis` state-statistics fix both touch computations that feed published numbers; the rest are non-computational (docs, output format, a crash fix). Confirm before tagging v0.2.0.

<!--
Answer this explicitly once v0.2.0 is tagged. If yes, that's a signal to loop
in PLOS about the submitted manuscript, not just update this file.
-->

---

## How to add a new Framework version

1. Decide the current state of `main` across the affected packages is coherent and ready to ship together.
2. Tag each changed package (`git tag vX.Y.Z`) and let the Zenodo–GitHub integration mint a DOI for the tag. Packages that didn't change keep their previous tag and DOI in the new row.
3. Tag the top-level `rENM` orchestration repo with the Framework version.
4. Add a new section to this file with the table above, filled in, plus a plain-language summary of what changed and why.
5. Update the banner and installation instructions in the [org README](https://github.com/rENM-Framework) to reference the new version.
6. If the change would alter any published or submitted result, note that explicitly and handle it through the relevant journal, not just through this file.

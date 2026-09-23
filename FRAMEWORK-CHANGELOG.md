# rENM Framework Changelog

This file tracks **Framework-level** versions. Each rENM package (`rENM`, `rENM.core`, `rENM.data`, `rENM.model`, `rENM.analysis`, `rENM.ai`, `rENM.reports`) is versioned and released independently, with its own `NEWS.md` and its own Zenodo DOI. A "Framework version" here is a specific, tested combination of those package versions — the combination that a paper, a report, or a user cites as "rENM Framework vX.Y.Z."

For package-level detail (what changed inside a single package and why), see that package's `NEWS.md`. This file only records which combination shipped together, and what that combination means for reproducibility.

---

## v0.1.0 — 2026 (bioRxiv preprint; submitted to PLOS One, review in progress)

Initial public release. Described in:

- Schnase, John L., Mark L. Carroll, Paul M. Montesano, and Virginia A. Seamster. "The rENM Framework: A Modular System for Reconstructing and Analyzing Long-Term Ecological Niche Dynamics." Preprint, bioRxiv, August 7, 2026. <https://doi.org/10.64898/2026.08.06.741224>. Submitted to PLOS One; review in progress.

Archived and citable as a set through the [rENM Framework Zenodo Community](https://zenodo.org/communities/renm-framework/records). The complete v0.1.0 software bundle carries its own DOI: [10.5281/zenodo.20799598](https://doi.org/10.5281/zenodo.20799598).

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

Datasets used by this release are archived separately:

| Dataset | Archive | Zenodo |
| ------- | ------- | ------ |
| Example (~725 MB) | `rENM-Framework-v0.1.0-example-data` | [zenodo.org/records/20750253](https://zenodo.org/records/20750253) |
| Extended (~30 GB) | `rENM-Framework-v0.1.0-extended-data` | [zenodo.org/records/20765324](https://zenodo.org/records/20765324) |

Datasets are versioned on their own line. The `v0.1.0` in a dataset name refers to that line, not to a Framework software version. The two coincide here because both were first published together.

Documentation for this release:

| Artifact | Source | Zenodo |
| -------- | ------ | ------ |
| User Manual | `rENM-documentation` tag `v0.1.0` | [10.5281/zenodo.20799331](https://doi.org/10.5281/zenodo.20799331) |

The `v0.1.0` tag of `rENM-documentation` carries the rendered manual in PDF, DOCX, HTML, and IPYNB, together with per-package reference manuals. Use the manual matching the Framework version you are running: each edition describes the pipeline as it behaved at that release, and the v0.1.0 manual does not describe the buffered extent default, the `seed` and `ai` arguments, or boundary statistics.

**Reproducibility note:** the figures in the bioRxiv preprint and the PLOS One submission were generated with this exact combination. To work from the same code, install these tagged versions, not `main`. See the pinned installation instructions in the [org README](https://github.com/rENM-Framework).

This reproduces the method rather than every number. v0.1.0 seeds no stage of the pipeline, so `limit_record_count()`, `screen_by_convergence2()`, and `create_ensemble_model()` draw fresh on each run. Quantities derived from vector geometry, including Range Area, Extent Area, and Range %, involve no model and are exact on any run. Model-derived statistics vary. In the one case measured, two runs of the same species, range-wide aggregates moved by one to three percentage points while a small state's positive-trend fraction moved from 98.4 to 11.3. Run-to-run determinism was added in v0.2.0 through the `seed` argument to `rENM()`.

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

**Datasets:** unchanged. Framework v0.2.0 runs against the v0.1.0 example and extended datasets listed above, and the User Manual's download instructions are unchanged. A dataset version is not expected to track the software version.

**Documentation:** the User Manual is being revised for v0.2.0 and will be tagged in `rENM-documentation` and deposited to Zenodo alongside the release. Until then the v0.1.0 manual remains the published reference and describes v0.1.0 behavior.

Summary of changes since v0.1.0 (from each package's `NEWS.md`; not yet tagged as a Framework release):

- **`rENM.core`** — added `check_species()`, an audit of the species metadata table. `get_species_info()` no longer requires or returns an `EBD.RANGE` column and now prints left-justified.
- **`rENM.data`** — `find_range_extent()` now derives the modeled extent from a true 250 km buffer around the GAP range polygon, applied in EPSG:5070, replacing a percentage pad of the bounding box that varied with latitude and corresponded to no fixed ground distance. `pad_pct` is replaced by `buffer_km` (default 250), and the buffered polygon is saved so boundary statistics can use it. `find_occurrence_extent()` changed its default `bbox_pct` from 99 to 90 and now restricts records to a CONUS bounding box first, though it is no longer the pipeline default.
- **`rENM.model`** — run-to-run determinism. `create_timeseries()` had been seeding its worker streams from the wall clock, which defeated any seed set upstream; it and `create_ensemble_model()` gain a `seed` argument with per-year seeding, which is what makes a result independent of which worker picks up which year. `screen_by_convergence2()` now registers `doRNG`, tying the RNG stream to the iteration rather than the worker, so variable selection no longer varies between seeded runs. Adds `doRNG` to Imports.
- **`rENM.analysis`** — added `find_boundary_trend_statistics()`, comparing trend behavior inside the GAP range against the surrounding buffer ring. `find_trend_percentages()` gained a `layer` argument and per-class area columns, and its percentages moved from a cell-count basis to an area basis, matching every other percentage the framework reports. Several hot-spot corrections: area is clipped to the GAP range portion within each state and weighted by the fraction of each cell inside it, and Hot Spot % is taken against a grid-measured range area, so it can no longer exceed 100. Also fixed `create_hot_spot_map()` aborting where a range edge coincides with a state line, and both state functions including states with no raster coverage.
- **`rENM.ai`** — added `assemble_coversheet()`, which builds the narrative page locally with no language model, used when `ai = NULL` and as the fallback when a provider call fails. Adds `officer` to Imports. `submit_to_chatgpt()`'s container listing is now paginated, which was the actual cause of document retrieval failing at random. `render_ai_docx()` runs three checks on the returned document: unsubstituted placeholders stop the run, truncation and known prose faults warn. Extensive prompt corrections, including removing fabricated references.
- **`rENM.reports`** — `assemble_final_report()` substantially rewritten: `cpdf` page numbering in place of a raster overlay, letter-size normalization, optional `.docx` output, an `optional_pages` argument that lets a missing narrative page be skipped rather than aborting assembly, and a vector return value. Adds `SystemRequirements: cpdf`. The state summary table gained a boundary block and a `top_states` filter, Hot Spot % now uses a grid-measured range area as its denominator, and the mislabeled "State Area" column was renamed. Added a methods note to the report appendix.
- **`rENM`** — added `seed` (default 42) and `ai` (`"chatgpt"`, `"claude"`, or `NULL`) arguments. Default extent determination is now `find_range_extent()`, superseding a `find_occurrence_extent()` default that never shipped in a release. The pipeline now calls `find_boundary_trend_statistics()` and runs `find_trend_percentages()` a second time on the change trend. A GenAI failure no longer aborts the run; the coversheet substitutes.

<!--
When filling in this section: pull the high-level points from each package's
NEWS.md rather than duplicating detail here; keep the summary to a few
sentences and link out to the relevant NEWS.md entries.
-->

**Affects a result, figure, or number reported in the v0.1.0 / bioRxiv paper:** Numbers change, but no published claim depends on them. The manuscript's figures illustrate the kinds of data product the framework produces rather than supporting scientific conclusions, so no result rests on a specific value, and the v0.1.0 tag remains the anchor for the figures as published. Note that several v0.2.0 changes are corrections rather than refinements: hot-spot percentages could exceed 100, percentages and the areas printed beside them were computed on different bases, and state statistics could include states with no raster coverage. Figures regenerated under v0.2.0 will therefore differ visibly from their v0.1.0 counterparts. The preprint can be updated; anything arising in PLOS One review will be handled there.

---

## How to add a new Framework version

1. Decide the current state of `main` across the affected packages is coherent and ready to ship together.
2. Tag each changed package (`git tag vX.Y.Z`) and let the Zenodo–GitHub integration mint a DOI for the tag. Packages that didn't change keep their previous tag and DOI in the new row.
3. Tag the top-level `rENM` orchestration repo with the Framework version.
4. Add a new section to this file with the table above, filled in, plus a plain-language summary of what changed and why.
5. Update the banner and installation instructions in the [org README](https://github.com/rENM-Framework) to reference the new version.
6. If the change would alter any published or submitted result, note that explicitly and handle it through the relevant journal, not just through this file.

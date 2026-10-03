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

**Known defect:** in this release `find_hot_spots()` selects declining cells where the decline is easing, not accelerating as documented. Hot-spot maps, areas and percentages produced by v0.1.0, including those in the example reports and the preprint, are affected. Corrected in v0.2.0.

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

v0.2.0 makes runs reproducible under a fixed seed, standardizes the modeled extent, adds boundary statistics and a report option with no generated prose, and corrects several defects in v0.1.0. Each package's `NEWS.md` gives the detail and the reasoning.

**Added**

- Run-to-run determinism: a `seed` argument to `rENM()` (default 42), applied to occurrence subsampling, variable screening and model fitting.
- A buffered extent: the GAP range polygon buffered 250 km, now the default (`find_range_extent()`).
- Boundary statistics comparing the GAP range interior with the surrounding 250 km ring, with median slopes (`find_boundary_trend_statistics()`).
- An `ai` argument to `rENM()`: `"claude"` (the default, on `claude-opus-5-5`), `"chatgpt"`, or `NULL` for a report with no generated prose (`assemble_coversheet()`).
- A REPRODUCIBILITY section on every report, saying which figures vary between seeds, and a methods note in the report appendix.
- Automated checks on AI narratives, convergence diagnostics for the variable-contribution fits, and a summary of warnings in each run log.
- `check_species()`, an audit of the species metadata table.

**Changed**

- Models are fitted and predicted on land only, so the modeled domain no longer depends on which variables are selected.
- Percentages are area-based throughout, and every area and percentage in a narrative is computed in R rather than by the language model.
- The change trend is described by its sign rather than as acceleration or deceleration.
- Top variables are ranked by their average contribution over all intervals; the variable table notes the importance it leaves out; single-run contribution trends are no longer marked as strong.
- Report assembly numbers pages with `cpdf` and continues when the narrative page is missing.

**Fixed**

- The hot-spot mask selected easing declines rather than steepening ones (see below).
- Hot Spot % could exceed 100, state trend shares could fall short of 100 where a range reaches water, and states with no raster coverage could appear in state tables.
- `create_hot_spot_map()` failed where a range edge follows a state line.
- ChatGPT narratives were intermittently not retrieved, and a provider failure stopped the whole run.
- Temporary occurrence files were occasionally left behind.

<!--
When filling in this section: pull the high-level points from each package's
NEWS.md rather than duplicating detail here; keep the summary to a few
sentences and link out to the relevant NEWS.md entries.
-->

**Corrections affecting v0.1.0 results and the published paper.** Two. The paper describes the hotspot analysis as identifying areas of accelerating suitability decline; in v0.1.0 the code identified declines that were easing, so the Cassin's Sparrow hotspot figures in the paper and its S2 Appendix are affected. The method as described stands. The paper also describes runs as fully reproducible; v0.1.0 did not fix its random seeds, so a repeated run does not reproduce its figures exactly. Other changes alter numbers but no published claim, and figures regenerated under v0.2.0 will differ from their v0.1.0 counterparts.

---

## How to add a new Framework version

1. Decide the current state of `main` across the affected packages is coherent and ready to ship together.
2. Tag each changed package (`git tag vX.Y.Z`) and let the Zenodo–GitHub integration mint a DOI for the tag. Packages that didn't change keep their previous tag and DOI in the new row.
3. Tag the top-level `rENM` orchestration repo with the Framework version.
4. Add a new section to this file with the table above, filled in, plus a plain-language summary of what changed and why.
5. Update the banner and installation instructions in the [org README](https://github.com/rENM-Framework) to reference the new version.
6. If the change would alter any published or submitted result, note that explicitly and handle it through the relevant journal, not just through this file.

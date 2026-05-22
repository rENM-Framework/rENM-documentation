# rENM Framework

[![Lifecycle: experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://lifecycle.r-lib.org/articles/stages.html#experimental)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**A modular R framework for reconstructing and analyzing long-term ecological niche dynamics in North American birds**

---

The rENM framework integrates 45 years (1980–2020) of eBird citizen science occurrence records with NASA MERRA-2 Earth system model data to reconstruct the spatio-temporal dynamics of climate-driven niche change in North American bird species. Rather than treating ecological niche models as static snapshots, rENM uses time-structured modeling to reveal how — and how fast — species' climatic environments have shifted across decades.

The complete pipeline runs from a single function call:

```r
library(rENM)
rENM("CASP")   # California Scrub-Jay, Cassin's Sparrow, or any four-letter banding code
```

---

## What the framework reveals

- **Long-term trends** in climatic suitability across the 45-year study period
- **Acceleration and deceleration** in those suitability trends over time
- **Bioclimatic velocity** and the direction of habitat-climate change
- **Hotspots** of potential climate change vulnerability
- **Changes in environmental structure** across decades

---

## Pipeline

The `rENM()` function executes twelve stages in sequence:

| Stage | What happens |
|---|---|
| 1 | eBird occurrence extraction and preparation |
| 2 | Spatial thinning and record limiting |
| 3 | Range-based extent determination |
| 4 | MERRA-2 environmental variable extraction |
| 5 | Stochastic variable screening |
| 6 | Five-year-binned time-series construction |
| 7 | Climatic suitability trend analysis |
| 8 | Centroid, velocity, and hotspot analysis |
| 9 | Report table and summary page compilation |
| 10 | AI-ready package assembly and submission |
| 11 | AI document rendering |
| 12 | Final report assembly |

---

## Packages

| Package | Role |
|---|---|
| [`rENM`](https://github.com/rENM-Framework/rENM) | Top-level orchestration; the single entry point for running the complete pipeline |
| [`rENM.core`](https://github.com/rENM-Framework/rENM.core) | Shared infrastructure: project directory resolution, species and variable metadata, logging |
| [`rENM.data`](https://github.com/rENM-Framework/rENM.data) | eBird occurrence extraction and MERRA-2 variable assembly, thinning, and temporal binning |
| [`rENM.model`](https://github.com/rENM-Framework/rENM.model) | Ensemble ENM construction and five-year time-series assembly using the sdm framework |
| [`rENM.analysis`](https://github.com/rENM-Framework/rENM.analysis) | Suitability trends, centroid tracking, bioclimatic velocity, hotspot detection, range change |
| [`rENM.ai`](https://github.com/rENM-Framework/rENM.ai) | AI-ready package assembly and submission to Claude and ChatGPT for interpretive analysis |
| [`rENM.reports`](https://github.com/rENM-Framework/rENM.reports) | Summary tables, per-topic report pages, and final species PDF report assembly |

---

## Installation

Install all framework packages from GitHub in dependency order:

```r
# install.packages("remotes")
remotes::install_github("rENM-Framework/rENM.core")
remotes::install_github("rENM-Framework/rENM.data")
remotes::install_github("rENM-Framework/rENM.model")
remotes::install_github("rENM-Framework/rENM.analysis")
remotes::install_github("rENM-Framework/rENM.ai")
remotes::install_github("rENM-Framework/rENM.reports")
remotes::install_github("rENM-Framework/rENM")
```

---

## Documentation

A full User Manual is available in the
[rENM-documentation](https://github.com/rENM-Framework/rENM-documentation)
repository (PDF, HTML, and Word formats).

---

## Selected Publications

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. (in preparation). The rENM Framework: Toward a modular system for reconstructing and analyzing long-term ecological niche dynamics.

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. 2026. Shifts in seasonal climatic suitability for Cassin's Sparrow (*Peucaea cassinii*) over four decades. *The Southwestern Naturalist*, 70(1):1–17. https://doi.org/10.1894/0038-4909-70.1.7

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. 2025. Shifts in breeding phenology for Cassin's Sparrow (*Peucaea cassinii*) over four decades. *Journal of Field Ornithology* 96(3):3. https://doi.org/10.5751/JFO-00691-960303

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. 2024. Complex changes in climatic suitability for Cassin's Sparrow (*Peucaea cassinii*) revealed by retrospective ecological niche modeling. *Journal of Field Ornithology* 95(1):9. https://doi.org/10.5751/JFO-00432-950109

Schnase, J. L., and M. L. Carroll. 2023. The MMX Toolkit: High-performance, reanalysis-based climatic suitability modeling to advance avian conservation. In *Proceedings of the 2023 Conference on Big Data from Space (BiDS'23)*, 299–303. https://doi.org/10.2760/46796

Schnase, J. L., and M. L. Carroll. 2022. Automatic variable selection in ecological niche modeling: a case study using Cassin's Sparrow (*Peucaea cassinii*). *PLoS One* 17(1):e0257502. https://doi.org/10.1371/journal.pone.0257502

Schnase, J. L., M. L. Carroll, R. L. Gill, G. S. Tamkin, J. Li, S. L. Strong, T. P. Maxwell, M. E. Aronne, and C. S. Spradlin. 2021. Toward a Monte Carlo approach to selecting climate variables in MaxEnt. *PLoS One* 16(3):e0237208. https://doi.org/10.1371/journal.pone.0237208

---

## Status and support

The rENM framework is an active research platform under ongoing development, provided for educational and research purposes. It is distributed without formal technical support. Feedback and contributions are welcome at rENM.Framework@gmail.com.

&copy; 2021–2026 John L. Schnase &nbsp;|&nbsp; MIT License

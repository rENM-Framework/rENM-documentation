# rENM Framework Documentation

![rENM](https://img.shields.io/badge/rENM-framework-blue)
![module](https://img.shields.io/badge/module-documentation-informational)
![status](https://img.shields.io/badge/status-pre--release-orange)

**User manual and reference documentation for the rENM Framework**

## Overview

This repository contains the primary documentation for the rENM Framework —
a modular suite of R packages for reconstructing and analyzing long-term
ecological niche dynamics using historical species occurrence records and
environmental data.

## Contents

| File | Description |
|---|---|
| `rENM-Framework-User-Manual.qmd` | Quarto source for the user manual |
| `rENM-Framework-User-Manual.pdf` | User manual (PDF) |
| `rENM-Framework-User-Manual.docx` | User manual (Word) |
| `rENM-Framework-User-Manual.html` | User manual (HTML, self-contained) |
| `rENM-Framework-User-Manual.ipynb` | User manual (Jupyter notebook) |

Per-package reference manuals (PDF) are generated from the installed packages
via `R CMD Rd2pdf` and are not tracked in this repository. Install the
packages and run `?<function>` in R for function-level reference.

## The rENM Framework

The rENM Framework spans six modular R packages organized as a linear
analytical pipeline:

```
rENM.core → rENM.data → rENM.model → rENM.analysis → rENM.ai → rENM.reports
```

Each package has its own GitHub repository and README under the
[rENM-Framework](https://github.com/rENM-Framework) organization.

## Selected Publications

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. (in
preparation). The rENM Framework: Toward a modular system for reconstructing
and analyzing long-term ecological niche dynamics.

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. 2026.
Shifts in seasonal climatic suitability for Cassin's Sparrow (*Peucaea
cassinii*) over four decades. *The Southwestern Naturalist*, 70(1):1--17.
<https://doi.org/10.1894/0038-4909-70.1.7>

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. 2025.
Shifts in breeding phenology for Cassin's Sparrow (*Peucaea cassinii*) over
four decades. *Journal of Field Ornithology* 96(3):3.
<https://doi.org/10.5751/JFO-00691-960303>

Schnase, J. L., M. L. Carroll, P. M. Montesano, and V. A. Seamster. 2024.
Complex changes in climatic suitability for Cassin's Sparrow (*Peucaea
cassinii*) revealed by retrospective ecological niche modeling. *Journal of
Field Ornithology* 95(1):9. <https://doi.org/10.5751/JFO-00432-950109>

Schnase, J. L., and M. L. Carroll. 2023. The MMX Toolkit: High-Performance,
Reanalysis-Based Climatic Suitability Modeling to Advance Avian Conservation.
In *Proceedings of the 2023 Conference on Big Data from Space (BiDS'23)*,
299--303. <https://doi.org/10.2760/46796>

Schnase, J. L., and M. L. Carroll. 2022. Automatic variable selection in
ecological niche modeling: a case study using Cassin's Sparrow (*Peucaea
cassinii*). *PLoS ONE* 17(1):e0257502.
<https://doi.org/10.1371/journal.pone.0257502>

Schnase, J. L., M. L. Carroll, R. L. Gill, G. S. Tamkin, J. Li, S. L.
Strong, T. P. Maxwell, M. E. Aronne, and C. S. Spradlin. 2021. Toward a
Monte Carlo approach to selecting climate variables in MaxEnt. *PLoS ONE*
16(3):e0237208. <https://doi.org/10.1371/journal.pone.0237208>

## Status

> **Pre-release.** Content is subject to ongoing revision and periodic
> updates.

## Contact

John Schnase — rENM.Framework@gmail.com

## License

See `LICENSE` for details.

---

**rENM Framework** — A modular system for reconstructing and analyzing
long-term ecological niche dynamics.

# Data Links & Sources

This file lists the primary **public data sources** used in the paper and the accompanying notebook. The analysis is based on homogeneously reduced catalogs from JWST, HST, and Gaia.

**Data Policy:** Due to the large size of raw catalogs and the terms of the source archives, the full multi-gigabyte datasets are not redistributed here. Instead, processed Cartesian point clouds (optimized filtered subsets) are provided in [`data/processed/`](./data/processed/) for immediate, one-click reproducibility.

---

### JWST & High-Redshift Surveys

#### 1. UNCOVER Survey (Abell 2744 Lensed Field)
The primary source for the early cosmic web analysis (z = 5–16).
- **Project Page:** [jwst-uncover.github.io](https://jwst-uncover.github.io/)
- **Core Catalog:** Weaver et al. (2024), *ApJS*, 270, 7 ([DOI: 10.3847/1538-4365/ad07e0](https://iopscience.iop.org/article/10.3847/1538-4365/ad07e0)).
- **SPS & Photo-z:** Wang et al. (2024), *ApJS*, 270, 12. Full catalog available via [Zenodo (doi:10.5281/zenodo.8401181)](https://zenodo.org).
- **Spectroscopic Redshifts:** DR4.1 update (Dec 2024) via [UNCOVER Project Page]([https://jwst-uncover.github.io](https://jwst-uncover.github.io/DR4.html).
- **Processed Subsets in this Repo:** 
  - `UNCOVER_z5_z10.csv`: 5,217 galaxies (5 ≤ z ≤ 10). 
  - `UNCOVER_z10_z16.csv`: 953 galaxies (z ≥ 10), including the record-breaking $z=13.16$ source (ID 13077).
- **Relevance:** Used to measure $D_{3D} \approx 1.23$ (global) and $1.60$ (small-scale), validating hierarchical clustering at Cosmic Dawn.

#### 2. CEERS (Cosmic Evolution Early Release Science)
Source for the **Cosmic Vine** filamentary structure.
- **Project Page:** [ceers.github.io](https://ceers.github.io)
- **Primary Source:** Goulding et al. (2023), *Nature Astronomy* ([arXiv:2303.10174](https://arxiv.org)).
- **Processed File:** `cosmic_vine_members.csv`.
- **Relevance:** A 13-million-light-year long filament at $z \approx 3.44$ used as a benchmark for $D_{3D} \approx 1.63 \pm 0.03$.

#### 3. DAWN JWST Archive (DJA)
Used for cross-checks and high-z candidate verification.
- **Archive:** [dawn-cph.github.io/dja/](https://dawn-cph.github.io/dja/)
- **NIRSpec Merged Table (v4.4, 2025):** [Direct link](https://dawn-cph.github.io/dja/blog/2025/05/01/nirspec-merged-table-v4/).

---

### Local Group & Nearby Systems

#### 1. Gaia DR3 & Savino et al. (2025)
- **Source:** [Gaia Archive](https://gea.esac.esa.int/archive/).
- **Paper:** Savino et al. (2025), *High-resolution satellites of M31* ([arXiv:2412.01234](https://arxiv.org)).
- **Processed File:** `m31_mw_facing_sector.csv` (30 objects).
- **Relevance:** Baseline for local fractal dimension ($D_{3D} \approx 1.25$).

---

### Cosmology & Computation Parameters

All comoving coordinates ($x, y, z$) in the processed files were calculated using the **Planck 2018** cosmology via `astropy.cosmology`:
- **$H_0$:** $67.66$ km/s/Mpc
- **$\Omega_m$:** $0.3111$
- **$\Omega_b$:** $0.049$

**Contact:** [janoscsabakeves@gmail.com](mailto:janoscsabakeves@gmail.com) | GitHub: [@JanosKeves68](https://github.com)

# Emergent Fractal Spacetime Analysis Pipeline

**Reproducible 3D Fractal Dimension Measurements**  
János Csaba Kevés – Independent Researcher  
Budapest, Hungary  
janoscsabakeves@gmail.com  
January–April 2026

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
<!-- [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXXX) -->

[📄 Full Paper (PDF)](./emergent-fractal-spacetime.pdf)

### Overview

This repository provides the code and processed data needed to reproduce the core empirical results of the preprint:

**"Emergent Fractal Geometry of Spacetime from Interstellar Clouds to the Cosmic Web:  
A Dark-Component-Free Cosmological Model"** (Kevés, 2026)

The analysis applies uniform 3D box-counting and correlation dimension methods to publicly available datasets (JWST PHANGS, JADES, CEERS, UNCOVER, GLASS, PRIMER, HST, Gaia DR3, DESI Year-1).  
It measures fractal dimensions in the range **1.25 ≤ D₃D ≤ 2.25** in strongly perturbed baryonic structures across ~16 orders of magnitude in physical scale.

The results are compared to ΛCDM hydrodynamical simulations (IllustrisTNG, MillenniumTNG, Thesan, FLARES etc.).  
The repository aims for **maximum practical reproducibility** while respecting data size and licensing constraints.

### Repository Contents

- **`supplementary_calculations.ipynb`** – Main Jupyter notebook containing all analysis steps.
- **`data/processed/`** – Representative Cartesian point clouds (small CSV files for fast execution):
  - `m31_mw_facing_sector.csv`
  - `cosmic_vine_members.csv`
  - `UNCOVER_z5_z10.csv` (subsample)
  - `UNCOVER_z10_z16.csv` (subsample)
  - Additional local/DESI subsets
- **`data_links.md`** – Detailed instructions and direct links to download full public catalogs + quality cuts applied.
- **`requirements.txt`** – Exact Python dependencies.

### Data Availability and Reproducibility

All measurements are based on **publicly available** astronomical catalogs. The repository contains only small representative subsamples for immediate execution. Full catalogs can be obtained via the links and instructions in [`data_links.md`](data_links.md).

#### Primary Public Datasets

**DESI Year-1 Early Data Release**
- `BGS_ANY_NGC_clustering.dat.fits` / `BGS_ANY_SGC_clustering.dat.fits`
- `LRG_NGC_clustering.dat.fits` / `LRG_SGC_clustering.dat.fits`
- `ELG_LOPnotqso_NGC_clustering.dat.fits`

**JWST UNCOVER (Abell 2744)**
- `UNCOVER_DR3_SPS_redshift_catalog.fits`
- `uncover-msa-default_drz-DR4.1-zspec.fits`

**JWST JADES**
- `jades_dr3_prism_public_gs_v1.1.fits`
- `Combined_DR4_external_v1.2.1.fits`

**Local Universe**
- `6dFGSzDR3.txt`
- Gaia DR3 (extragalactic extension)

#### Data Processing Pipeline

1. **Redshift fusion** – Spectroscopic redshifts take priority.
2. **Comoving distance conversion** – Using Astropy + Planck 2018 cosmology (`H₀ = 67.74 km s⁻¹ Mpc⁻¹`, `Ωₘ = 0.3153`).
3. **3D Cartesian transformation** – Equatorial coordinates (RA, Dec) + comoving distance → (X, Y, Z) in Mpc.
4. **Fractal analysis** – 3D box-counting + KDTree-based correlation dimension.

#### Reproducibility Benchmarks (validation targets)

| Dataset                    | Objects (filtered) | Measured D₃D | Interpretation                  |
|----------------------------|--------------------|--------------|---------------------------------|
| DESI BGS NGC               | ~4 081 033         | 2.2503       | Local web (filamentary)         |
| DESI LRG NGC               | ~1 116             | 1.8848       | Hierarchical scaffold           |
| DESI ELG NGC               | ~2 740             | 1.4551       | Pure filamentary (1D-like)      |
| UNCOVER (z > 5)            | 73 998             | 1.7490       | Primordial fractal web          |
| JADES Prism (spectroscopic)| 279                | 1.6379       | Spaghetti-limit filament index  |

**North–South anisotropy** (noted for further investigation):  
- LRG layer: NGC = 1.885 vs. SGC = 1.774  
- BGS layer: NGC = 2.250 vs. SGC = 2.180

**Important note**: Full filtered catalogs are **not redistributed** due to size. The notebook uses representative subsamples (N ≈ 20–50 for high-z systems) that preserve the main trends. For full statistical power, download the complete datasets using `data_links.md`.

### Quick Start

```bash
git clone https://github.com/janoscsabakeves-afk/emergent-fractal-spacetime.git
cd emergent-fractal-spacetime

# Recommended: virtual environment
python -m venv venv
source venv/bin/activate          # Linux / macOS
# venv\Scripts\activate           # Windows

pip install -r requirements.txt

jupyter notebook supplementary_calculations.ipynb
````

**The notebook is also Colab-friendly** (fallback hardcoded data works offline).

### Reproducibility Status

Core algorithms and benchmark values can be reproduced in 1–5 minutes with the included subsamples.  
Full reproduction of all figures and tables requires the complete catalogs (see above).  
Validation on synthetic fractal sets and comparison with ΛCDM mocks is planned for a future update.

We welcome contributions, bug reports, and independent verifications.

### Citation

```bibtex
@misc{keves2026emergent,
  author       = {Kevés, János Csaba},
  title        = {Emergent Fractal Geometry of Spacetime from Interstellar Clouds to the Cosmic Web: A Dark-Component-Free Cosmological Model},
  year         = {2026},
  howpublished = {arXiv / Zenodo (pending)},
  url          = {https://github.com/janoscsabakeves-afk/emergent-fractal-spacetime}
}
````
Zenodo DOI will be added upon archival.ContactEmail: janoscsabakeves@gmail.com  
GitHub Issues: Feel free to open an issue.

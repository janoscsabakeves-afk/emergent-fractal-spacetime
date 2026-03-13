# Emergent Fractal Spacetime  
**A Dark-Component-Free Cosmological Model Based on Emergent Fractal Geometry**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
<!--Zenodo: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXXX)-->

János Csaba Kevés  
Independent Researcher  
Budapest, Hungary  
janoscsabakeves@gmail.com  
January 2026

[📄 Full paper (PDF)](./emergent-fractal-spacetime.pdf)

### Overview

This repository contains the supplementary code and processed datasets to reproduce the key results of the paper:

**Emergent Fractal Geometry of Spacetime from Interstellar Clouds to the Cosmic Web: A Dark-Component-Free Cosmological Model**

Persistently low 3D fractal dimensions (1.25 ≤ D₃D ≤ 1.82) are measured across 16 orders of magnitude in scale using uniform box-counting on public JWST/HST/Gaia/DESI-derived point clouds — in strong tension with ΛCDM predictions for virialized structures.

The results motivate an alternative where spacetime curvature emerges solely from baryonic matter perturbations, rendering dark matter and dark energy unnecessary.

### Key Scientific Breakthroughs (Validated in this Repo)
- **Large-Scale Anisotropy Detected:** Measurement of North-South fractal asymmetry ($D_{NGC} \approx 1.88$ vs. $D_{SGC} \approx 1.77$) using **DESI Year-1** LRG samples.
- **Hubble Tension Resolution:** Geometric derivation showing $H_0 \approx 73$ km/s/Mpc is a scaling artifact of $D \approx 2.25$ fractal geometry, resolving the conflict with the global $67.4$ value.
- **16 Orders of Magnitude:** Persistent fractal dimensions ($1.25 \le D \le 1.82$) from **PHANGS** clouds ($10^{-6}$ pc) to **JWST JADES/UNCOVER** filaments ($10^4$ Mpc).

### What's Included

- Main Jupyter notebook: [`supplementary_calculations.ipynb`](supplementary_calculations.ipynb)  
  → box-counting, deprojection correction, bootstrap errors, scaling regime detection, plots
- Processed point clouds (Cartesian subsamples): [`data/processed/`](data/processed/)  
  → small CSV files for fast reproduction  
  → fallback to hardcoded representative arrays if files missing (Colab/offline friendly)
- Catalog links & filtering notes: [`data_links.md`](data_links.md)
- Dependencies: [`requirements.txt`](requirements.txt)

**Representative subsamples** (due to non-public filtered full lists):
- m31_mw_facing_sector.csv
- cosmic_vine_members.csv
- UNCOVER_z10_z16.csv
- UNCOVER_z5_z10.csv
- LOCAL_LARGE_SCALE_SUBSET.csv
- local_anisotropy_summary.csv

Full filtered catalogs not redistributed (size, privacy, and source archive limitations) — see `data_links.md` for sources and query instructions.

### Quick Start

```bash
# Clone
git clone https://github.com/janoscsabakeves-afk/emergent-fractal-spacetime.git
cd emergent-fractal-spacetime

# Virtual environment (recommended)
python -m venv venv
source venv/bin/activate          # Linux/macOS
# venv\Scripts\activate           # Windows

# Install
pip install -r requirements.txt

# Run
jupyter notebook supplementary_calculations.ipynb
# or upload to Google Colab

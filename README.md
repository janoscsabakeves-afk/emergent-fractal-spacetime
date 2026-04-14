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
It measures fractal dimensions in the range **1.25 ≤ D₃D ≤ 2.25** in strongly perturbed baryonic structures across \~16 orders of magnitude in physical scale.

The results are compared to ΛCDM hydrodynamical simulations (IllustrisTNG, MillenniumTNG, Thesan, FLARES etc.).  
The repository aims for **maximum practical reproducibility** while respecting data size and licensing constraints.

### Repository Contents

- **`supplementary_calculations.ipynb`** – Main Jupyter notebook containing:
  - Data loading (with fallback to hardcoded representative samples)
  - 3D box-counting implementation
  - Automatic scaling regime selection (R² ≥ 0.95, ≥ 1 decade)
  - Bootstrap confidence intervals
  - Deprojection correction for photometric/high-z data
  - PCA-based filament analysis
  - Exploratory Hubble scaling toy model
  - Summary tables and plots

- **`data/processed/`** – Representative Cartesian point clouds (small CSV files for fast execution):
  - `m31_mw_facing_sector.csv`
  - `cosmic_vine_members.csv`
  - `UNCOVER_z5_z10.csv` (subsample)
  - `UNCOVER_z10_z16.csv` (subsample)
  - Additional local/DESI subsets

- **`data_links.md`** – Detailed instructions and links to download full public catalogs + quality cuts applied.

- **`requirements.txt`** – Exact Python dependencies.

**Important note on data**:  
Full filtered catalogs are **not redistributed** in this repository due to size and origin from public archives (MAST, DESI, etc.). The notebook uses **representative subsamples** (typically N ≈ 20–50 for high-z systems) that preserve the main observed trends. For full statistical power, users are encouraged to download the complete datasets using the instructions in `data_links.md`.

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

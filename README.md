# Emergent Fractal Spacetime  
**A Dark-Component-Free Cosmological Model Based on Emergent Fractal Geometry**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
<!-- Zenodo DOI (activate upon publication): [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXXX) -->

János Csaba Kevés  
Independent Researcher  
Budapest, Hungary  
janoscsabakeves@gmail.com  

**February 2026**

[📄 Full paper (PDF)](./emergent-fractal-spacetime.pdf)

### Overview

This repository provides supplementary code and processed datasets to reproduce the key results from the paper:

**Emergent Fractal Geometry of Spacetime from Interstellar Clouds to the Cosmic Web: A Dark-Component-Free Cosmological Model**

We measure persistently low 3D fractal dimensions (1.25 ≤ D₃D ≤ 1.82) across 16 orders of magnitude in scale (10⁻⁶ pc to 10⁴ Mpc) using uniform 3D box-counting on public JWST, HST, Gaia, unWISE, and DESI datasets. These values show strong tension (up to 3–6σ in extreme high-z cases) with ΛCDM predictions for virialized dark-matter halos (D₃D ≈ 2.4–3.0).

The findings support an alternative framework where spacetime curvature emerges solely from baryonic matter perturbations and self-gravitating structures — making dark matter and dark energy unnecessary mathematical artifacts.

### What's Included

- **Main analysis notebook**: [`supplementary_calculations.ipynb`](supplementary_calculations.ipynb)  
  → Uniform box-counting, deprojection correction, bootstrap uncertainties, automatic scaling regime selection, diagnostic plots

- **Processed point clouds** (Cartesian comoving coordinates in Mpc): [`data/processed/`](data/processed/)  
  → Ready-to-use CSV files for offline reproduction  
  → Fast demo mode with subsampling (e.g., 100 points) + full dataset support  
  → Fallback to hardcoded representative arrays if files are missing (Colab/offline friendly)

- **Data source & filtering notes**: [`data_links.md`](data_links.md)  
  → Links to original public catalogs + quality cut / coordinate conversion recipes

- **Dependencies**: [`requirements.txt`](requirements.txt)

Key high-redshift datasets now use comprehensive filtered subsets from the UNCOVER JWST survey (Abell 2744 lensed field), replacing smaller aggregated subsamples for better statistics and reproducibility.

### File Descriptions in data/processed/

- **m31_mw_facing_sector.csv** — 30 M31 satellites (MW-facing sector); lowest D₃D = 1.25 ± 0.04  
- **cosmic_vine_members.csv** — 20 core members of Cosmic Vine (z ≈ 3.44 filament); D₃D = 1.63 ± 0.03  
- **UNCOVER_z5_z10.csv** — ~5167 galaxies (5 ≤ z ≤ 10); probes mid-to-high redshift filaments  
- **UNCOVER_z10_z16.csv** — ~826 galaxies (z ≥ 10, candidates + confirmed); probes early cosmic web (z ≳ 10–16)

All coordinates are comoving (Planck 2018 cosmology via Astropy), centered on field/structure barycenter. Columns include: name, id, ra, dec, z_spec_or_phot, x_Mpc, y_Mpc, z_Mpc, note, survey.

### Quick Start

```bash
# Clone the repository
git clone https://github.com/janoscsabakeves-afk/emergent-fractal-spacetime.git
cd emergent-fractal-spacetime

# Create and activate virtual environment (recommended)
python -m venv venv
source venv/bin/activate          # Linux/macOS
# venv\Scripts\activate           # Windows

# Install dependencies
pip install -r requirements.txt

# Launch the notebook
jupyter notebook supplementary_calculations.ipynb
# or upload to Google Colab for quick testing

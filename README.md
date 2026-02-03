# Emergent Fractal Spacetime  
**A Dark-Component-Free Cosmological Model Based on Emergent Fractal Geometry**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io)](https://www.python.org)

**János Csaba Kevés**  
Independent Researcher  
Budapest, Hungary  
[janoscsabakeves@gmail.com](mailto:janoscsabakeves@gmail.com)

**February 2026**

[📄 Full paper (PDF)](./emergent-fractal-spacetime.pdf)

### Overview

This repository provides supplementary code and high-resolution processed datasets to reproduce the key results from the paper:

> **Emergent Fractal Geometry of Spacetime from Interstellar Clouds to the Cosmic Web: A Dark-Component-Free Cosmological Model**

We report persistently low 3D fractal dimensions ($1.23 \leq D_{3D} \leq 1.82$) across 16 orders of magnitude in scale using uniform 3D box-counting and correlation integral methods on public **JWST (UNCOVER, CEERS, JADES)**, HST, and Gaia datasets. 

The high-redshift results ($z > 10$) show a significant tension ($3–6\sigma$) with $\Lambda$CDM predictions, supporting an alternative framework where spacetime curvature emerges from baryonic matter perturbations, potentially rendering dark matter and dark energy as mathematical artifacts of an assumed homogeneous metric.

### What's Included

- **Main Analysis Notebook**: [`supplementary_calculations.ipynb`](supplementary_calculations.ipynb)  
  → Implementation of KDTree-based correlation integrals, deprojection corrections, and bootstrap uncertainty estimation.
  
- **Processed Point Clouds**: [`data/processed/`](data/processed/)  
  → High-fidelity CSV files containing Cartesian comoving coordinates (Mpc).
  → Optimized "slim" versions for GitHub searchability and fast offline reproducibility.

- **Data Source & Methodology**: [`data_links.md`](data_links.md)  
  → Comprehensive links to original JWST/HST master catalogs and coordinate conversion recipes.

### Key Datasets in `data/processed/`

- **`m31_mw_facing_sector.csv`**: 30 M31 satellites (Local Group); $D_{3D} = 1.25 \pm 0.04$.
- **`cosmic_vine_members.csv`**: Confirmed members of the $z \approx 3.44$ filament; $D_{3D} = 1.63 \pm 0.03$.
- **`UNCOVER_z5_z10.csv`**: **5,217 galaxies** ($5 \leq z \leq 10$); robust probe of the Reionization era cosmic web.
- **`UNCOVER_z10_z16.csv`**: **953 galaxies** ($z \geq 10$); deep-field extension probing the Cosmic Dawn, including record-breaking candidates at $z \approx 13.2$.

*All coordinates are comoving (Planck 2018 cosmology: $H_0=67.66$, $\Omega_m=0.3111$).*

### Quick Start

1. **Clone the repository:**
   ```bash
   git clone https://github.com/janoscsabakeves-afk/emergent-fractal-spacetime.git
   cd emergent-fractal-spacetime

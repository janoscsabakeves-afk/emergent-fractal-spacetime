# Emergent Fractal Geometry of Spacetime  
A Dark-Component-Free Cosmological Model

**Author**: János Csaba Kevés  

The work demonstrates low fractal dimensions (1.25 ≤ D₃D ≤ 1.82) in biased, perturbed baryonic structures across 19 orders of magnitude in scale — from ISM clouds to z ≳ 10 cosmic filaments — using uniform 3D box-counting on public JWST/HST/Gaia/DESI datasets. These findings challenge ΛCDM expectations in extreme environments and propose an emergent, matter-dependent spacetime geometry as an alternative to dark components.

### Key Features
- Jupyter notebook reproducing main D₃D measurements (box-counting + bootstrap)
- Processed point clouds (small CSV files) for offline reproducibility
- Fallback hardcoded representative subsamples when full data not public
- Dependencies: NumPy, SciPy, Pandas, Astropy, Matplotlib

### Repository Structure
- `supplementary_calculations.ipynb` — Main analysis notebook (box-counting, deprojection, bootstrap)
- `data/processed/` — Processed Cartesian point clouds (M31, Cosmic Vine subsample, z>10 subsample, z>5 subsample)
- `emergent-fractal-spacetime.pdf` — Full paper
- `data_links.md` — External catalog links (JWST archives, arXiv, etc.)
- `requirements.txt` — Python dependencies
- `README_processed.md` (in data/processed/) — Detailed data file descriptions

### Installation & Quick Start
1. Clone the repo:
   ```bash
   git clone https://github.com/janoscsabakeves-afk/emergent-fractal-spacetime.git
   cd emergent-fractal-spacetime
Clone the repository: https://github.com/janoscsabakeves-afk/emergent-fractal-spacetime.git

Install dependencies: pip install -r requirements.txt (if added; otherwise manual).

Run the notebook:
Open and run the cells sequentially in Jupyter. For maximum accuracy, ensure n_boot=5000 is set and use the complete datasets.

## Quick Start
- Install deps: `pip install -r requirements.txt`
- Run notebook: Open in Jupyter or Colab.
- Demo runtime: ~5 min (n_boot=2000); for faster, set n_boot=100 in code.

Contact: janoscsabakeves@gmail.com or @JanosKeves68 on X.

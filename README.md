# Emergent-Fractal-Geometri

This repository contains a reproducible Jupyter notebook for calculating 3D fractal dimensions in cosmic structures, as described in the paper:"Emergent Fractal Geometry of Spacetime from
Interstellar Clouds to the Cosmic Web: A Dark-Component-Free Cosmological Model"
by János Kevés – January 17, 2026

Key Features

Notebook: supplementary_calculations.ipynb – Fully reproduces key calculations using real public data (M31 satellites, Cosmic Vine, z>10 galaxies).

Methods: 3D box-counting with bootstrap resampling, deprojection correction.

Requirements: Python 3.x with NumPy, SciPy, Pandas, Astropy, Matplotlib.

Data: Hardcoded samples; full catalogs via links in notebook.

Runtime: Bootstrap may take 5-60 minutes depending on hardware.

Usage

Clone the repository: https://github.com/janoscsabakeves-afk/emergent-fractal-spacetime.git

Install dependencies: pip install -r requirements.txt (if added; otherwise manual).

Run the notebook:
Open and run the cells sequentially in Jupyter. For maximum accuracy, ensure n_boot=5000 is set and use the complete datasets.

## Quick Start
- Install deps: `pip install -r requirements.txt`
- Run notebook: Open in Jupyter or Colab.
- Demo runtime: ~5 min (n_boot=2000); for faster, set n_boot=100 in code.

Contact: janoscsabakeves@gmail.com or @JanosKeves68 on X.

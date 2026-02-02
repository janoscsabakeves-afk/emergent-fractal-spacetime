# Processed Data Files for Reproducibility

This folder contains processed point clouds (Cartesian comoving coordinates in Mpc) used for the main 3D fractal dimension (D₃D) measurements reported in Table 2 of the paper:

> Emergent Fractal Geometry of Spacetime from Interstellar Clouds to the Cosmic Web:  
> A Dark-Component-Free Cosmological Model  
> János Csaba Kevés (February 1, 2026)

All files are in CSV format with minimal columns for direct use in the `supplementary_calculations.ipynb` notebook (e.g., `ra`, `dec`, `z_spec_or_phot`, `x_Mpc`, `y_Mpc`, `z_Mpc`, and optional metadata like `name`, `id`, `note`, `survey`).

These files enable fast, offline, one-click reproducibility of key results without downloading full external JWST catalogs. Coordinates are in comoving frame (Planck 2018 cosmology via Astropy.cosmology) and approximately centered on the field center (A2744 for UNCOVER). For full catalogs and raw data sources, see `data_links.md`.

### File Descriptions

- **m31_mw_facing_sector.csv**  
  **Description**: 30 satellites from the MW-facing sector (θ ≤ 90° from M31–MW line-of-sight) of the M31 system.  
  **Source**: Savino et al. (2025) updated Table 1 (full sample 41 objects; filtered to 30 in sector).  
  **Columns**: name, ra (deg), dec (deg), dist_kpc, theta_deg, x_kpc, y_kpc, z_kpc (Cartesian relative to M31 center).  
  **Relevance**: Key system with lowest D₃D = 1.25 ± 0.04 (3–4σ tension vs ΛCDM).  
  **Size**: ~30 rows.

- **cosmic_vine_members.csv**  
  **Description**: Representative subsample of 20 spectroscopically confirmed members (core/most massive objects).  
  **Source**: Jin et al. (2024, A&A 683, L12 / Table 1); full 136 members from Sillassen et al. (2025, arXiv:2510.23549) not fully public.  
  **Columns**: id, name, ra (deg), dec (deg), z_spec, logMstar, SFR, x_Mpc, y_Mpc, z_Mpc (comoving, relative to vine barycenter), note.  
  **Relevance**: z ≈ 3.44 filament; D₃D = 1.63 ± 0.03 (3σ tension).  
  **Note**: Use as representative subsample; full list not open access.

- **UNCOVER_z5_z10.csv**  
  **Description**: Filtered subset of ~5167 galaxies with photometric/spectroscopic redshifts in 5 ≤ z ≤ 10 from the UNCOVER survey (Abell 2744 lensed field).  
  **Source**: Own filtering of the public UNCOVER master catalog (Weaver et al. 2024; latest DR3/DR4 versions via https://jwst-uncover.github.io/). Quality cuts applied (S/N > 5, photo-z flags, etc.).  
  **Columns**: name, id, ra (deg), dec (deg), z_spec_or_phot, x_Mpc, y_Mpc, z_Mpc (comoving), note, survey.  
  **Relevance**: Probes filamentary structures in lensed field at cosmic noon to early universe transition. Can be used to test D₃D evolution in biased environments (expected ~1.5–1.6 range based on similar z>5 samples).  
  **Size**: ~772 kB (~5167 rows).  
  **Note**: Lensed field → magnification effects possible; consider weighting by mu if available in raw catalog.

- **UNCOVER_z10_z16.csv**  
  **Description**: Filtered subset of ~826 galaxies with photometric/spectroscopic redshifts z ≥ 10 (mostly candidates + confirmed) from the UNCOVER survey.  
  **Source**: Own filtering of public UNCOVER master catalog (latest DR versions). Quality cuts applied.  
  **Columns**: name, id, ra (deg), dec (deg), z_spec_or_phot, x_Mpc, y_Mpc, z_Mpc (comoving), note, survey.  
  **Relevance**: High-redshift extension (z ≳ 10–16); directly relevant for probing early cosmic web filaments and D₃D ≈ 1.47–1.59 trend toward cosmic dawn.  
  **Size**: ~122 kB (~826 rows).  
  **Note**: High photo-z uncertainty at z>12; deprojection correction recommended for box-counting.

### Usage in Notebook

In `supplementary_calculations.ipynb`, files are loaded with fallback to hardcoded representative data if missing (for Colab/offline compatibility). Example for UNCOVER files (adapt existing loading pattern):

```python
import pandas as pd
from pathlib import Path

DATA_DIR = Path('../data/processed')

try:
    df_uncov_high = pd.read_csv(DATA_DIR / 'UNCOVER_z10_z16.csv')
    # Optional: quick subsample for demo / low-RAM runs
    # df_uncov_high = df_uncov_high.sample(n=100, random_state=42)
except FileNotFoundError:
    print("UNCOVER file not found — using fallback hardcoded high-z sample")
    # hardcoded representative array here (as in existing code)

coords = df_uncov_high[['x_Mpc', 'y_Mpc', 'z_Mpc']].to_numpy()
# Proceed with box-counting, deprojection, bootstrap, etc.

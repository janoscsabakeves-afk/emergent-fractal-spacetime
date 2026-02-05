# Processed Data Files for Reproducibility

This folder contains the processed point clouds (Cartesian coordinates) used for the main 3D fractal dimension (D₃D) measurements reported in Table 2 of the paper:

> Emergent Fractal Geometry of Spacetime from Interstellar Clouds to the Cosmic Web:  
> A Dark-Component-Free Cosmological Model  
> János Csaba Kevés (January 27, 2026)

All files are in CSV format with minimal columns for direct use in the `supplementary_calculations.ipynb` notebook (e.g., `ra`, `dec`, `dist_kpc` or `z`, `x_kpc`/`x_Mpc`, `y_kpc`/`y_Mpc`, `z_kpc`/`z_Mpc`).

These files enable offline, one-click reproducibility of the key results without needing to download full external catalogs. Coordinates are in comoving frame (Planck 2018 cosmology via Astropy) and centered on the structure barycenter (or approximate field center).

### File Descriptions

- **m31_mw_facing_sector.csv**  
  **Description**: 30 satellites from the MW-facing sector (θ ≤ 90° from M31–MW line-of-sight) of the M31 system.  
  **Source**: Savino et al. (2025) updated Table 1 (full sample 41 objects; filtered to 30 in sector).  
  **Columns**: name, ra (deg), dec (deg), dist_kpc, theta_deg, x_kpc, y_kpc, z_kpc (Cartesian relative to M31 center).  
  **Relevance**: Key system with lowest D₃D = 1.25 ± 0.04 (3–4σ tension vs ΛCDM).  
  **Size**: ~30 rows.

- **cosmic_vine_members.csv**  
  **Description**: Subsample of 20 spectroscopically confirmed members (the core/most massive objects).  
  **Source**: Jin et al. (2024, A&A 683, L4 / Table 1); full 136 members from Sillassen et al. (2025, arXiv:2510.23549) not publicly available (DAWN JWST Archive internal).  
  **Columns**: id, name, ra (deg), dec (deg), z_spec, logMstar, SFR, x_Mpc, y_Mpc, z_Mpc (comoving, relative to approximate vine barycenter ~RA 214.9°, Dec 52.87°), note.  
  **Relevance**: z ≈ 3.44 filament; D₃D = 1.63 ± 0.03 (3σ tension).  
  **Note**: Use as representative subsample; full list not open access.

- **z10_confirmed.csv**  
  **Description**: Representative subsample of ~12 spectroscopically/photometrically confirmed z > 10 galaxies (from public JWST papers).  
  **Source**: Aggregated from JADES (e.g., JADES-GS-z14-0), GLASS (GHZ1/z10), CEERS, UNCOVER, etc. (2024–2025 publications); full 28 confirmed objects from Pérez-González et al. (2025) not publicly listed.  
  **Columns**: name, id, ra (deg), dec (deg), z_spec_or_phot, x_Mpc, y_Mpc, z_Mpc (comoving, relative to GOODS-S center), note, survey.  
  **Relevance**: z > 10 confirmed; D₃D = 1.47 ± 0.06 (4–5σ tension). Photometric uncertainties addressed via deprojection.  
  **Note**: Exploratory subsample; full list pending publication.

- **z5_filaments_sample.csv**  
  **Description**: Representative subsample of ~25 z > 5 galaxies from filament/protocluster environments.  
  **Source**: Aggregated from JADES, CEERS, GLASS, UNCOVER, NGDEEP, PRIMER public high-z catalogs (Harikane et al. 2024 and related works); full ~427 galaxies not publicly available as a filtered filament list.  
  **Columns**: name, id, ra (deg), dec (deg), z_spec_or_phot, x_Mpc, y_Mpc, z_Mpc (comoving, relative to approximate GOODS-S/EGS center), note, survey.  
  **Relevance**: z > 5 filaments; D₃D = 1.59 ± 0.04 (3–4σ tension).  
  **Note**: Representative for method demonstration; full merged dataset from JWST DRs.

### Usage in Notebook
In `supplementary_calculations.ipynb`, files are loaded with fallback to hardcoded representative data:

```python
import pandas as pd
from pathlib import Path

DATA_DIR = Path('data/processed')

try:
    df = pd.read_csv(DATA_DIR / 'm31_mw_facing_sector.csv')  # example
except FileNotFoundError:
    print("CSV not found — using fallback hardcoded subsample")
    # hardcoded data here

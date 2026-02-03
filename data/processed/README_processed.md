# Processed Data Files for Reproducibility

This folder contains processed point clouds (Cartesian comoving coordinates in Mpc) used for the main 3D fractal dimension ($D_{3D}$) measurements reported in Table 2 of the paper:

> **Emergent Fractal Geometry of Spacetime from Interstellar Clouds to the Cosmic Web:**  
> **A Dark-Component-Free Cosmological Model**  
> *János Csaba Kevés (February 1, 2026)*

All files are in CSV format, optimized for the `supplementary_calculations.ipynb` notebook. Coordinates are calculated in the comoving frame using **Planck 2018 cosmology** (via `astropy.cosmology`).

### Key Statistical Updates (as of Feb 3, 2026)
Following the integration of the full **JWST UNCOVER DR3/DR4** spectroscopic and photometric catalogs, the samples have been expanded to provide higher statistical significance for fractal analysis.

---

### File Descriptions

#### 1. `m31_mw_facing_sector.csv`
- **Description**: 30 satellite galaxies from the M31 system, filtered to the Milky Way-facing sector ($\theta \leq 90^\circ$).
- **Source**: Updated from [Savino et al. (2025)](https://arxiv.org).
- **Relevance**: Represents a local system with a measured $D_{3D} = 1.25 \pm 0.04$, showing significant tension ($3–4\sigma$) against $\Lambda$CDM predictions.

#### 2. `cosmic_vine_members.csv`
- **Description**: Confirmed members of the **Cosmic Vine** filament in the CEERS field ($z \approx 3.44$).
- **Source**: [Goulding et al. (2023)](https://www.nature.com).
- **Relevance**: A prime example of a $z \approx 3.4$ filamentary structure; contributes to the observed $D_{3D} = 1.63$ trend.

#### 3. `UNCOVER_z5_z10.csv` (Slim version)
- **Description**: Expanded subset of **5,217 galaxies** ($5 \leq z \leq 10$) from the UNCOVER survey (Abell 2744 field).
- **Source**: Integrated master catalog (SUPER cat + SPS DR4). Processed to resolve the "pencil-beam" geometry bias.
- **Relevance**: High-resolution probe of the early cosmic web. Measured small-scale $D_{3D} \approx 1.60$, confirming the hierarchical clustering model during the Reionization era.
- **Note**: "Slim" version used for GitHub compatibility (rounded to 4 decimal places).

#### 4. `UNCOVER_z10_z16.csv`
- **Description**: Extreme high-redshift sample containing **953 galaxies** ($z \geq 10$) from the UNCOVER survey.
- **Source**: Combined UNCOVER DR4 spectroscopic and photometric (SPS) catalogs.
- **Relevance**: One of the largest available samples of Cosmic Dawn candidates. Essential for testing $D_{3D}$ evolution toward the theoretical $1.47–1.59$ limit at high redshift.
- **Note**: Includes the record-breaking $z = 13.16$ (ID: 13077) and $z = 12.19$ (ID: 38766) objects.

---

### Usage in Notebook

Files are loaded via `pandas`. The `slim` versions are recommended for web-based environments (like GitHub/Colab) to ensure fast loading and searchability.

```python
import pandas as pd
from pathlib import Path

# Load the high-redshift sample (N=953)
df_high_z = pd.read_csv('UNCOVER_z10_z16.csv')

# Accessing Cartesian coordinates for fractal dimension calculation
coords = df_high_z[['x_Mpc', 'y_Mpc', 'z_Mpc']].to_numpy()

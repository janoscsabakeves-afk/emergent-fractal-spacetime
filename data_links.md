# Data Links & Sources

This file provides direct links and instructions to all **publicly available** datasets used in the paper and in `supplementary_calculations.ipynb`.  
Full raw/filtered catalogs are **not redistributed** in this repository (size, licensing, and archive policies). Representative subsamples are provided in [`data/processed/`](./data/processed/) for immediate reproduction.

---

### 1. Primary Public Datasets

**DESI Year-1 Early Data Release (EDR)**
- Bright Galaxy Sample (BGS): `BGS_ANY_NGC_clustering.dat.fits`, `BGS_ANY_SGC_clustering.dat.fits`
- Luminous Red Galaxies (LRG): `LRG_NGC_clustering.dat.fits`, `LRG_SGC_clustering.dat.fits`
- Emission Line Galaxies (ELG): `ELG_LOPnotqso_NGC_clustering.dat.fits`
- Official release: https://data.desi.lbl.gov/public/edr/

**JWST UNCOVER Program (Abell 2744)**
- `UNCOVER_DR3_SPS_redshift_catalog.fits`
- `uncover-msa-default_drz-DR4.1-zspec.fits`
- Official site: https://jwst-uncover.github.io/

**JWST JADES (Deep & Medium surveys)**
- `jades_dr3_prism_public_gs_v1.1.fits`
- `Combined_DR4_external_v1.2.1.fits`
- MAST Portal: https://mast.stsci.edu/portal/Mashup/Clients/Mast/Portal.html (search “JADES”)
- High-Level Science Products: https://archive.stsci.edu/hlsp/jades

**Additional JWST Programs**
- CEERS (Cosmic Vine): https://mast.stsci.edu/portal/Mashup/Clients/Mast/Portal.html (search “CEERS”)
- GLASS, NGDEEP, PRIMER: Official project pages via MAST

**Merged JWST Catalogs (DAWN Archive)**
- DAWN JWST Archive: https://dawn-cph.github.io/dja/
- Merged NIRSpec + photometric table (v4): https://zenodo.org/records/15472354

**Local & Nearby Catalogs**
- Gaia DR3 (Local Group satellites + extragalactic extension): https://gea.esac.esa.int/archive/
- 6dFGS DR3: `6dFGSzDR3.txt` – https://www.6dfgs.net/
- HST archival data (M31, interacting pairs): https://mast.stsci.edu/

**Voids & Quiescent Regions**
- Boötes Void (SDSS DR7 + DESI update): Sutter et al. (2012), arXiv:1203.6377 + DESI EDR

---

### 2. Generated Intermediate Files

These files are created by the notebook when full catalogs are available:

- `UNCOVER_TOTAL_MASTER.csv` – 73 998 galaxies (JWST DR3 + DR4 merged)
- `LOCAL_LARGE_SCALE.csv` – 4 081 033 galaxies (6dFGS + DESI BGS)
- `UNCOVER_ULTRA_3D.csv` – 3D Cartesian coordinates (comoving Mpc)

---

### 3. Reproducibility Notes

- The notebook `supplementary_calculations.ipynb` automatically uses the full files if they are present in the working directory; otherwise it falls back to the small representative subsamples in `data/processed/`.
- All coordinate transformations use Astropy + Planck 2018 cosmology.
- Redshift priority: spectroscopic > photometric.
- Fractal metrics: 3D box-counting + KDTree-based correlation dimension.
- Benchmark values for verification are listed in the [README](README.md#reproducibility-benchmarks).

For full reproduction:
1. Download the catalogs listed above.
2. Place them in a `data/raw/` folder (or adjust paths in the notebook).
3. Run the notebook.

Questions or issues? Open an issue or contact:  
janoscsabakeves@gmail.com | [@JanosKeves68](https://x.com/JanosKeves68)

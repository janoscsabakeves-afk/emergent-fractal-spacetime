# Data Links & Sources

This file lists the primary **public data sources** used in the paper and notebook. All analyses rely on publicly available, homogeneously reduced JWST, HST, Gaia, unWISE, and DESI catalogs. 

**Full raw/filtered datasets are not redistributed** here due to size and source archive policies — instead, processed Cartesian point clouds (subsamples or filtered subsets) are in [`data/processed/`](./data/processed/) for fast, offline reproducibility. Coordinates are comoving (Planck 2018 cosmology via Astropy), centered on field/structure barycenter.

For high-z samples (e.g., z>5 filaments, z>10 structures), the notebook uses representative subsamples or filtered subsets from public catalogs. Full reproduction: download originals from links below, apply similar quality/overdensity filters (S/N >5, photo-z flags, δ>5, filamentarity F>0.7), then run box-counting.

### JWST & High-Redshift Catalogs

- **UNCOVER Survey (Abell 2744 lensed field, primary source for z~5–16 subsets)**  
  Weaver et al. (2024), ApJS, 270, 7 ("First-look HST+JWST Catalog of 60,000 Galaxies")  
  → https://iopscience.iop.org/article/10.3847/1538-4365/ad07e0  
  → Project page: https://jwst-uncover.github.io/ (Data Releases: DR4 August 2024 / DR4.1 December 2024)  
  → Photometric catalogs (PSF-matched, aperture-optimized): MAST HLSP search "UNCOVER" or direct via https://archive.stsci.edu/hlsp/uncover  
  → Stellar population + photo-z catalogs (Wang et al. 2024, ApJS 270, 12): Zenodo doi:10.5281/zenodo.8401181 (posteriors, SFHs, etc.)  
  → Redshift catalog (NIRSpec/PRISM, Price et al. 2025): DR4 release on project page  
  → Lens models & magnifications: Furtak et al. (2023), Price et al. (2025) updates  
  **Relevance**: Basis for `UNCOVER_z5_z10.csv` (~5167 galaxies, 5≤z≤10) and `UNCOVER_z10_z16.csv` (~826 galaxies, z≥10). Quality cuts applied (S/N>5, flags). Lensed → consider mu weighting if using raw.

- **PHANGS–JWST Treasury (ISM molecular clouds, 108k objects)**  
  Bazzi et al. (2025), ApJ, 972, 150 (arXiv:2511.06596)  
  Data: https://phangs-jwst.github.io/ (mosaics, catalogs) or MAST search "PHANGS-JWST"

- **JADES DR3/DR4 (high-z galaxies, filaments, protoclusters)**  
  JADES Collaboration releases (2024–2025)  
  MAST Portal: https://mast.stsci.edu/portal/Mashup/Clients/Mast/Portal.html (search "JADES DR4")  
  HLSP: https://archive.stsci.edu/hlsp/jades

- **CEERS (Cosmic Vine z≈3.44, high-z structures)**  
  CEERS Collaboration (2023–2025)  
  MAST: search "CEERS"  
  Jin et al. (2024): https://arxiv.org/abs/2311.04867 (Table 1 subsample used for `cosmic_vine_members.csv`)

- **GLASS, NGDEEP, PRIMER**  
  GLASS: https://glass-jwst.github.io/  
  NGDEEP: https://ngdeep.github.io/  
  PRIMER: https://primer-jwst.github.io/  
  All via MAST Portal (program IDs or HLSPs)

- **DAWN JWST Archive (merged NIRSpec/photometric catalogs across fields)**  
  https://dawn-cph.github.io/dja/  
  NIRSpec merged table v4.4 (2025): https://dawn-cph.github.io/dja/blog/2025/05/01/nirspec-merged-table-v4/ (summary tables, searchable extractions)  
  Zenodo snapshot: https://zenodo.org/records/15472354 (80k+ public NIRSpec spectra)  
  **Relevance**: Useful for cross-checks / full high-z merging (e.g., JADES+UNCOVER+CEERS)

### Local & Nearby Catalogs

- **Gaia DR3 (Local Group satellites, extragalactic extension)**  
  https://gea.esac.esa.int/archive/  
  Savino et al. (2025): M31 satellites Table 1 (basis for `m31_mw_facing_sector.csv`)

- **HST (M31 satellites, interacting pairs like M51, Antennae)**  
  MAST: https://mast.stsci.edu/ (search HST programs for M31, M51, etc.)

- **DESI Year-1 + Euclid Q1 Early Release (local biased filaments)**  
  DESI: https://data.desi.lbl.gov/public/edr/ (Year-1 catalogs)  
  Euclid Q1: https://euclid.calet.org/early-release (data products)

- **unWISE (local extragalactic extension)**  
  https://unwise.me/ (catalog downloads)

### Voids & Quiescent Counterexamples

- **Boötes Void (SDSS DR7 + DESI update)**  
  Sutter et al. (2012): https://arxiv.org/abs/1203.6377  
  DESI Year-1 updates: https://data.desi.lbl.gov/public/edr/

### General Tools & Cosmology

- **Astropy** (coordinates, comoving distances, Planck 2018: H₀=67.74 km/s/Mpc, Ωₘ=0.3153)  
  https://docs.astropy.org/en/stable/

### Notes on Reproduction & Filtering

- High-z filament/protocluster samples (z>5: ~427, z>10 confirmed: 28 in paper) derived from merged JWST catalogs (UNCOVER, JADES DR, DAWN) via quality + overdensity selection.  
- `data/processed/` contains filtered Cartesian subsets (e.g., UNCOVER z-bins) — subsample in notebook for quick runs (e.g., 100 points).  
- For exact paper replication: download from MAST/DAWN/Zenodo → apply filters (spectro-z priority, photo-z σ/(1+z)<0.05, filament criteria) → generate point clouds → run `supplementary_calculations.ipynb`.

Questions or updates? Contact: janoscsabakeves@gmail.com or @JanosKeves68 on X.

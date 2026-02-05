# Data Links & Sources

This file lists the primary public data sources used in the paper and notebook. All analyses rely on publicly available, homogeneously reduced JWST, HST, Gaia, unWISE, and DESI catalogs. Full raw/filtered datasets are **not redistributed** here due to size, licensing, and privacy reasons — instead, representative subsamples are in [`data/processed/`](./data/processed/) for reproducibility.

Full filtered lists (e.g., exact 427 z>5 filament galaxies, 136 Cosmic Vine members, 28 z>10 confirmed) are not publicly released as separate subsets in the source archives; they require internal merging/filtering (e.g., via DAWN JWST Archive or JADES DR queries). The notebook demonstrates the pipeline on subsamples consistent with the reported trends.

### JWST & High-Redshift Catalogs

- **PHANGS–JWST Treasury (ISM clouds, 108k objects)**  
  Bazzi et al. (2025), ApJ, 972, 150  
  arXiv: 2511.06596  
  Data: https://phangs-jwst.github.io/ (public mosaics, catalogs) or MAST archive search "PHANGS-JWST"

- **JADES DR3/DR4 (high-z galaxies, filaments)**  
  JADES Collaboration (2024–2025 releases)  
  MAST Portal: https://mast.stsci.edu/portal/Mashup/Clients/Mast/Portal.html (search "JADES DR4")  
  Catalogs: https://archive.stsci.edu/hlsp/jades (High-Level Science Products)

- **CEERS (Cosmic Vine, high-z structures)**  
  CEERS Collaboration (2023–2025)  
  MAST: https://mast.stsci.edu/portal/Mashup/Clients/Mast/Portal.html (search "CEERS")  
  Jin et al. (2024): https://arxiv.org/abs/2311.04867 (Table 1 subsample used)

- **GLASS, UNCOVER, NGDEEP, PRIMER**  
  GLASS: https://glass-jwst.github.io/  
  UNCOVER: https://jwst-uncover.github.io/  
  NGDEEP: https://ngdeep.github.io/  
  PRIMER: https://primer-jwst.github.io/  
  All accessible via MAST Portal (search program IDs or HLSPs)

- **DAWN JWST Archive (merged NIRSpec/photometric catalogs)**  
  https://dawn-cph.github.io/dja/  
  Merged table v4: https://dawn-cph.github.io/dja/blog/2025/05/01/nirspec-merged-table-v4/  
  Zenodo: https://zenodo.org/records/15472354 (large FITS/CSV downloads)

### Local & Nearby Catalogs

- **Gaia DR3 (Local Group satellites, extragalactic extension)**  
  https://gea.esac.esa.int/archive/  
  Savino et al. (2025): M31 satellites Table 1 (used for MW-facing sector)

- **HST (M31 satellites, interacting pairs)**  
  MAST: https://mast.stsci.edu/ (search HST programs for M31, M51, Antennae)

- **DESI Year-1 + Euclid Q1 Early Release (local biased filaments)**  
  DESI: https://data.desi.lbl.gov/public/edr/ (Year-1 catalogs)  
  Euclid Q1: https://euclid.calet.org/early-release (Q1 data products)

- **unWISE (local extragalactic)**  
  https://unwise.me/ (catalog downloads)

### Voids & Quiescent Counterexamples

- **Boötes Void (SDSS DR7 + DESI update)**  
  Sutter et al. (2012): https://arxiv.org/abs/1203.6377  
  DESI Year-1: https://data.desi.lbl.gov/public/edr/

### General Tools & Cosmology

- Astropy (used for coordinates, comoving distances, Planck 2018 cosmology)  
  https://docs.astropy.org/en/stable/

### Notes on Non-Public / Filtered Data

- Full lists for large high-z samples (427 z>5, 136 Cosmic Vine, 28 z>10 confirmed) are derived from merged JWST catalogs (DAWN, JADES DR, etc.) via internal filtering/overdensity selection — not available as single public tables.  
- Notebook uses representative subsamples from public tables (Jin+2024 Table 1, JADES/GLASS papers) to demonstrate the method.  
- For full reproduction: download merged catalogs from DAWN/MAST, apply similar filters (spectroscopic confirmation, overdensity δ>5, filamentarity F>0.7), then run the notebook on your point cloud.

Questions? Contact: janoscabakeves@gmail.com or @JanosKeves68 on X.

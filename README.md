Applying Contrastive Learning to Stellar Spectra
=======

This repository contains the code for `StarCLIP`, a contrastive self-supervised learning framework that embeds observed APOGEE and _ab initio_ JWST/NIRSpec spectra into a unified, physically meaningful latent space. StarCLIP leverages pre-trained convolutional neural networks (CNNs) as spectral encoders, aligned under a contrastive objective to learn representations that are robust and transferrable across modalities. The repository also includes `MockStarCLIP', a variant trained on semi-empirical, stochastically transformed JWST/NIRSpec spectra to simulate realistic observational effects. Together, these models enable downstream tasks such as cosine similarity search and stellar property recovery directly from spectral embeddings.

<img width="694" alt="Screenshot 2025-04-08 at 11 57 41 AM" src="https://github.com/user-attachments/assets/ba0d867e-eb4d-4f27-95ed-507f7a5d9706" />
The folder contains two Jupyter notebooks `StarNet.ipynb` and `AstroCLIP.ipynb`, the paper in progress, and supporting sub-folders: 
- `DATA`: contains cleaned spectral data. 
- `FIGURES`: contains .png figures of all plots.
- `lightning_logs`, `logs`: contains logs of ML models. 
- `MODELS`: contains working, saved ML models. 
    - `OLD_MODELS`: contains old models. 
- `OLD NOTEBOOKS`: contains an archive of old Jupyter notebooks. 

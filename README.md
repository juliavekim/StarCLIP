# 🌌 Applying Contrastive Learning to Stellar Spectra

This repository contains the code for **StarCLIP**, a contrastive self-supervised learning framework that embeds observed APOGEE and *ab initio* JWST/NIRSpec spectra into a unified, physically meaningful latent space.

Our approach consists of training convolutional neural networks (CNNs) to recover twenty fundamental stellar properties from single-modal spectroscopic data. These pre-trained CNNs are then used as encoders and aligned via contrastive loss. To simulate realistic NIRSpec observations, we construct semi-empirical, stochastic NIRSpec catalogs and embed them into the shared latent space using **MockStarCLIP**, a modified CLIP-based framework.

Both models enable seamless transfer to downstream tasks, including cosine similarity search and stellar property recovery.

<p align="center">
  <img width="694" alt="StarCLIP Overview" src="https://github.com/user-attachments/assets/ba0d867e-eb4d-4f27-95ed-507f7a5d9706" />
</p>

## Results
- To the best of our knowledge, we develop one of the first self-supervised foundation models for analysing NIRSpec data, along with a pipeline for seamless integration with observed data.
- We train robust CNNs in a supervised setting to predict stellar parameters with high precision and accuracy.
- We apply cross-modal contrastive training to align pre-trained encoders around shared physical properties, creating a discriminative latent space.
-  We apply dimension-reduction to the latent space, visualising its intrinsic local geometry in a lower- dimensional setting.
-  With minimal processing, our models enable accurate transfer to downstream tasks, including (i) in-modal and cross-modal cosine similarity searches and (ii) stellar property estimation from spectra. These tasks empirically show that latent embeddings capture key physical properties of underlying stars.

## File Structure

This repository is structured as follows:

- `Paper/`  
  Contains the PDF and zipped LaTeX source files of the paper.

- `Scripts/`  
  Contains the Python notebooks used to train CNNs (`StarNet.ipynb`) and implement the contrastive framework (`StarCLIP.ipynb`).

- `DATA/`
  Contains the following input data files:
  
  - `apogee_dr17.h5`: A summary HDF5 file from SDSS DR17 containing stellar labels, including effective temperature, surface gravity, metallicity, and elemental abundances.
  - `apogee_spectra.pkl.gz`: A compressed pickled dataset containing APOGEE spectra. 
  -  `JWST_APOGEE.h5` *(external)*: A semi-synthetic catalog of JWST/NIRSpec + APOGEE spectra, with accompayning stellar parameters.  
  ⚠️ Due to GitHub LFS limitations, this file is hosted externally and must be downloaded from the following link: [Download via Dropbox](https://www.dropbox.com/s/your-shared-link-here).
  After downloading, place it in the `DATA/` folder to run `StarCLIP.ipynb`.

> **Note:** These are the only required source files.  
> All additional datasets are automatically generated when running `StarCLIP.ipynb`.

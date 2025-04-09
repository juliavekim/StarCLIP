# Applying Contrastive Learning to Stellar Spectra

This repository contains the code for `StarCLIP`, a contrastive self-supervised learning framework that embeds observed APOGEE and _ab initio_ JWST/NIRSpec spectra into a unified, physically meaningful latent space. Our approach consists of training convolutional neural networks (CNNs) to recover twenty fundamental stellar properties from single-modal spectroscopic data. We then adopt these pre-trained CNNs as encoders, aligning them via contrastive loss. To simulate realistic NIRSpec observations, we construct semi-empirical, stochastic NIRSpec catalogs and embed them into the shared latent space using `MockStarCLIP`, a modified CLIP-based framework. Both models enable seamless transfer to downstream tasks, including cosine similarity search and stellar property recovery.

<img width="694" alt="Screenshot 2025-04-08 at 11 57 41 AM" src="https://github.com/user-attachments/assets/ba0d867e-eb4d-4f27-95ed-507f7a5d9706" />

## File Structure

This repository is structured, as follows:

-   `Paper` contains the PDF and LaTeX source files of the paper.
-   `Scripts` contains the Python scripts used to train CNNs (`StarNet.ipynb`) and implement the contrastive frameworks (`StarCLIP.ipynb`).

## Results
- To the best of our knowledge, we develop one of the first self-supervised foundation models for analysing NIRSpec data, along with a pipeline for seamless integration with observed data.
- We train robust CNNs in a supervised setting to predict stellar parameters with high precision and accuracy.
- We apply cross-modal contrastive training to align pre-trained encoders around shared physical properties, creating a discriminative latent space.
-  We apply dimension-reduction to the latent space, visualising its intrinsic local geometry in a lower- dimensional setting.
-  With minimal processing, our models enable accurate transfer to downstream tasks, including (i) in-modal and cross-modal cosine similarity searches and (ii) stellar property estimation from spectra. These tasks empirically show that latent embeddings capture key physical properties of underlying stars.

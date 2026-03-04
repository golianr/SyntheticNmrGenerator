# Synthetic Generator of ¹H NMR Spectra

This project is a synthetic data generator for ¹H NMR spectra designed to create datasets for machine learning models that recognize chemical compounds from NMR spectra.

The generator takes peak lists (ppm, intensity) from NMR databases and produces realistic synthetic spectra by simulating typical NMR effects such as:
 - chemical shift variability

 - line broadening (Lorentzian peaks)

 - baseline drift

 - noise

 - solvent and contaminant peaks

The generated spectra can be exported as images or numerical vectors, making them suitable for training deep learning models (e.g. CNNs) for compound classification or spectral analysis.

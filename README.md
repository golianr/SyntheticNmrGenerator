# Synthetic NMR Generator

Synthetic **¹H NMR spectrum generator** for creating datasets used in machine learning applications.

This repository was developed specifically to generate training data for the companion project:

**NMR Spectra Analysis Model:**
https://github.com/golianr/NMR-Spectra_Analysis-Model

---

# Project Overview

Machine learning models require large amounts of labeled data, but real NMR datasets are often:

* limited in size
* difficult to obtain
* inconsistently formatted

To address this, this repository generates **synthetic 1D ¹H NMR spectra** based on peak lists.

The generated spectra simulate realistic experimental conditions including:

* chemical shift variability
* intensity variation
* linewidth variation
* baseline drift
* spectral noise
* solvent peaks

---

# Dataset Generation Pipeline

```
peak list dataset
(ppm + intensity)
        ↓
synthetic spectrum generator
        ↓
Lorentzian peak simulation
        ↓
noise + baseline artifacts
        ↓
spectral normalization
        ↓
vector spectra + PNG images
```

---

# Generated Data

For each compound the generator produces:

* **vector representation of the spectrum**
* **PNG visualization of the spectrum**
* metadata describing the compound label

Example dataset structure:

```
nmr_dataset/

images/
    ethanol/
    acetone/
    toluene/

vectors/
    ethanol/
    acetone/
    toluene/

index.csv
label_map.json
```

---

# Spectrum Simulation

Spectra are generated using Lorentzian peak models:

```
peak shape → Lorentzian distribution
```

Each generated spectrum includes randomized variations such as:

* referencing shift
* peak intensity scaling
* linewidth variation
* baseline distortion
* Gaussian noise

Optional contaminants such as solvent peaks may also be added.

---

# Technologies Used

Python 3.x

Main libraries:

* NumPy
* pandas
* matplotlib

---

# Use Case

The main purpose of this generator is to create datasets for training machine learning models capable of:

* recognizing compounds from NMR spectra
* classifying spectral patterns
* learning spectral features of organic molecules

The generated dataset is used by:

https://github.com/golianr/NMR-Spectra_Analysis-Model

---

# Example Usage

```
python generator.py
```

This will generate synthetic spectra based on the peak list dataset and export:

* PNG spectral plots
* vector spectra (.npy files)
* dataset index files

---

# Future Improvements

Potential future extensions include:

* simulation of multiplet structures
* more realistic J-coupling simulation
* mixture spectra generation
* larger compound libraries
* integration with public NMR databases

---

# Author:

Richard Golian

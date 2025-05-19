# Breast Cancer Wisconsin (Diagnostic) - Normality Testing Project

## Overview

This project utilizes the **Breast Cancer Wisconsin (Diagnostic)** dataset to build a machine learning model capable of classifying whether a tumor is **malignant** or **benign** based on features derived from digitized images of a fine needle aspirate (FNA) of a breast mass.

The goal is to aid early and accurate diagnosis using interpretable features extracted from the tumor cell nuclei present in the image.

---

## Background

This dataset stems from research by **Dr. William H. Wolberg** who aimed to diagnose breast cancer using only data obtained from FNAs. He collaborated with the University of Wisconsin to develop a classifier using the **Multisurface Method-Tree (MSM-T)**, which achieved approximately **97% accuracy** on new instances.

This dataset has since become a benchmark in binary classification and medical diagnosis research.

---

## Dataset Summary

- **Total Instances**: 569
- **Target Classes**: 
  - `Malignant` (cancerous)
  - `Benign` (non-cancerous)
- **Features**: 30 numeric features derived from:
  - 10 base features:
    - `radius`
    - `texture`
    - `perimeter`
    - `area`
    - `smoothness`
    - `compactness`
    - `concavity`
    - `concave points`
    - `symmetry`
    - `fractal dimension`
  - Each base feature has three measurements:
    - **Mean**
    - **Standard Error (SE)**
    - **Worst (largest value)**

---

## Statistical Assumptions & Normality Testing

As part of the preprocessing and exploratory phase, we assessed the **normality** of the features using a combination of visual and statistical methods:

### Techniques Used:
- **QQ Plot (Quantile-Quantile Plot)**  
  Visual tool to assess if a feature's distribution deviates from a normal distribution.

- **Shapiro-Wilk Test**  
  Suitable for small to moderate sample sizes; tests the null hypothesis that data was drawn from a normal distribution.

- **Anderson-Darling Test**  
  A robust test that returns critical values for several significance levels; helps evaluate how far data diverges from normality.

- **Kolmogorov-Smirnov (KS) Test**  
  Non-parametric test comparing the sample distribution with a reference (normal) distribution.

### Key Observations:
- Many of the features showed deviations from normality, especially skewness in size-related features (e.g., `area`, `radius`, `perimeter`).
- Normality tests informed decisions around data transformations, scaling, and the choice of machine learning models (parametric vs non-parametric).

---

## Feature Descriptions

| Feature             | Description                                                                 |
|---------------------|-----------------------------------------------------------------------------|
| `radius`            | Mean distance from center to boundary points                                |
| `texture`           | Standard deviation of gray-scale values                                     |
| `perimeter`         | Length of the perimeter of the mass                                         |
| `area`              | Area of the cell nuclei (in pixels)                                         |
| `smoothness`        | Variation in radius lengths (edge smoothness)                               |
| `compactness`       | Perimeter² / area - 1.0 (describes edge density and shape complexity)       |
| `concavity`         | Severity of inward curves on the contour                                    |
| `concave points`    | Number of concave portions of the contour                                   |
| `symmetry`          | Symmetry of the cell nuclei                                                 |
| `fractal dimension` | Coastline approximation - 1 (measures boundary complexity/roughness)        |

---


## Resources & References

- **Dataset Source**  
  [UCI Machine Learning Repository - Breast Cancer Wisconsin (Diagnostic)](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic)

- **Original Research Links**  
  - [Multisurface Method for Pattern Separation (MSM)](http://www.cs.wisc.edu/~olvi/uwmp/mpml.html)  
  - [Cancer Diagnostic Research Page](http://www.cs.wisc.edu/~olvi/uwmp/cancer.html)

---

## Project Goals

- Perform detailed EDA to understand feature distributions and correlations
- Preprocess the dataset (e.g., scaling, handling class imbalance)
- Conduct normality and assumption testing

---

## Disclaimer

This project is for educational and research purposes only and should not be used for real-world medical diagnosis without proper clinical validation.

---

## License

Refer to the original dataset license terms on the [UCI Repository](https://archive.ics.uci.edu/dataset/17/breast+cancer+wisconsin+diagnostic). This project otherwise follows an open-source spirit.

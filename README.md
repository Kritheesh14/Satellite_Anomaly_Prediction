# Satellite Anomaly Prediction

### Reproducing Machine Learning Approaches for Satellite Time-to-Anomaly Prediction

An academic machine learning project reproducing research on satellite anomaly prediction using regression, nonlinear learning, and survival analysis.

---

## Overview

Satellite anomalies can disrupt satellite operations and affect mission reliability. Predicting the time remaining until an anomaly occurs can help support monitoring and operational planning.

This project aims to reproduce the approaches presented in *Satellite Anomaly Prediction using Survival Analysis and Machine Learning*, investigating whether satellite characteristics and space-weather features can predict the **Time to Event (TTE)** — the number of days until the next satellite anomaly.

The primary objective is **reproducing and evaluating the original approaches**, with model improvements reserved for future work.

## Models Implemented

| Model | Approach |
|---|---|
| Linear Regression | Establishes a linear baseline for TTE prediction |
| Support Vector Regression (RBF) | Models potentially nonlinear relationships |
| Modified Gaussian Naive Bayes | Combines feature likelihoods with a Kaplan–Meier survival estimate |

## Input Features

The models use six features:

- **Starting Month** — temporal information
- **Sunspot Number** — solar activity
- **X-ray Flux** — space-weather activity
- **Perigee** — orbital characteristic
- **Inclination** — orbital orientation
- **Satellite Mass** — physical characteristic

**Prediction target:** Time to Event (TTE), measured in days.

## Methodology

1. Inspect and reconstruct the available datasets.
2. Prepare the six input features and TTE target.
3. Implement the three models described above.
4. Evaluate model performance using 10-fold cross-validation.
5. Measure prediction error using Mean Absolute Relative Error (MARE).
6. Compare reproduced results with the paper's reported results and a median baseline.

## Reproduction Results

| Model | Test Relative Error |
|---|---:|
| Linear Regression | 477% |
| RBF-SVR | 187% |
| Modified Naive Bayes | 172% |
| Median Baseline | 153% |

*These are reported reproduction results, not the original paper's reference values. Exact reproduction is limited by the availability of the paper's processed datasets and may also depend on preprocessing and evaluation details.*

### Key Observation

Although Modified Naive Bayes has the lowest test error among the three implemented models, all three perform worse than the median baseline in the reported reproduction. This highlights the difficulty of predicting satellite anomaly timing using the available features and implementations.

## Technology Stack

- **Language:** Python
- **Environment:** Jupyter Notebook
- **Data Processing:** NumPy, Pandas
- **Machine Learning:** Scikit-learn
- **Scientific Computing:** SciPy
- **Visualization:** Matplotlib

## Repository Structure

```text
satellite-anomaly-prediction/
├── notebooks/
│   ├── Satellite_Anomaly_Data_Reconstruction.ipynb
│   └── Satellite_Anomaly_Paper_Reproduction.ipynb
├── data/
│   └── README.md
├── results/
│   └── figures/
├── requirements.txt
├── .gitignore
└── README.md
```

*The structure above is the intended layout; folders and files should be adjusted to match the actual repository contents.*

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/satellite-anomaly-prediction.git
cd satellite-anomaly-prediction
```

### 2. Install dependencies

```bash
python -m pip install -r requirements.txt
```

### 3. Prepare the dataset

Obtain the required datasets from their documented sources. Review the notebook instructions for missing processed files and data preparation requirements.

### 4. Run the notebooks

Open Jupyter Notebook or JupyterLab and execute the data reconstruction notebook before running the paper reproduction notebook.

**Note:** The supplied data archive does not include every processed file referenced by the original preprocessing pipeline. Exact reproduction of the paper's dataset and results cannot be guaranteed until those requirements are resolved.

## Limitations

- Results depend on data availability, preprocessing and cross-validation configuration.
- The RBF-SVR implementation uses unscaled feature values, which can affect distance-based similarity calculations.
- High relative errors indicate limited predictive accuracy.
- The models have not demonstrated performance better than the median baseline in the reported reproduction.

## Future Work

Potential extensions, after completing the reproduction, include:

- Investigating feature scaling and feature engineering.
- Exploring alternative regression and survival-analysis methods.
- Evaluating more robust validation strategies.
- Comparing improvements against the same baseline and evaluation metric.

## Reference

**Original research:** *Satellite Anomaly Prediction using Survival Analysis and Machine Learning*.

Add the authors, publication venue, year, and original paper URL here after verifying the bibliographic details against the source.

---

**Project focus:** Research Reproduction | Machine Learning | Satellite Reliability | Survival Analysis

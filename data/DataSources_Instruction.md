
# Satellite Anomaly Prediction

Reproduction of research on predicting satellite anomaly timing using
machine learning and survival analysis.

## Overview

This project reproduces the approaches described in C. Naughton's
research on satellite anomaly prediction.

The objective is to predict the Time to Event (TTE), measured in days
until the next satellite anomaly.

## Models Implemented

1. **Linear Regression** — baseline linear prediction model.
2. **Support Vector Regression (SVR)** — nonlinear regression using
   an RBF kernel.
3. **Modified Gaussian Naive Bayes** — combines feature likelihoods
   with a Kaplan-Meier survival estimate.

## Input Features

- Starting month
- Sunspot number
- X-ray flux
- Perigee
- Inclination
- Satellite mass

**Target:** Time to Event (TTE), in days.

## Methodology

1. Inspect and reconstruct the available datasets.
2. Prepare the features and target variable.
3. Train and evaluate the three models.
4. Use 10-fold cross-validation.
5. Compare the results using mean absolute relative error.
6. Compare reproduced results with the paper's reference results.

## Reported Results

| Model | Test Relative Error |
|---|---:|
| Linear Regression | 477% |
| RBF-SVR | 187% |
| Modified Naive Bayes | 172% |
| Median baseline | 153% |

These values are reported reproduction results and must be
distinguished from the original paper's reference results.

## Repository Structure

- `notebooks/` — data reconstruction and model reproduction notebooks
- `data/` — data documentation and permitted datasets
- `results/` — generated figures and result summaries
- `requirements.txt` — Python dependencies

## Getting Started

1. Clone this repository.
2. Install the dependencies listed in `requirements.txt`.
3. Obtain the required datasets from their documented sources.
4. Run the data reconstruction notebook first.
5. Run the paper reproduction notebook.

See the notebook instructions for required input files and execution order.

## Limitations

- The supplied data archive does not contain all processed files
  referenced by the original preprocessing pipeline.
- Exact reproduction of the paper's dataset and results cannot be
  guaranteed without the required source data and matching procedure.
- The reported errors indicate that the tested models do not outperform
  the median baseline in this reproduction.

## Future Work

Potential future work includes investigating feature scaling,
alternative feature representations, and improved prediction models.
These improvements are outside the initial reproduction objective.

## Acknowledgements

This project is an academic reproduction of existing research.
Please consult the original paper for its full methodology and citations.

# Robust Beta Estimation: OLS vs. RANSAC

## Overview

This project investigates the sensitivity of financial beta estimation to outliers and changing market regimes.

The analysis compares the traditional Ordinary Least Squares (OLS) estimator with the robust RANSAC (Random Sample Consensus) approach, combining Monte Carlo simulations with empirical analysis of real financial data.

The main objective is to investigate whether robust regression can provide a more reliable measure of systematic risk when financial returns contain extreme observations.

## Research Question

How do outliers and market stress affect beta estimation, and can a robust estimator such as RANSAC provide a more stable measure of systematic risk than traditional OLS?

## Methodology

The analysis consists of two main components.

### 1. Monte Carlo Simulations

Synthetic stock and market returns are generated under different scenarios to evaluate the behaviour of OLS and RANSAC beta estimates.

The analysis considers:

- 10% outliers
- 0.25% outliers
- Calm vs. crisis market regimes
- Comparison of estimated betas with the true beta
- Hypothesis testing of the difference between OLS and RANSAC

### 2. Empirical Analysis

The methodology is applied to daily financial data for:

- GOOG vs. S&P 500
- TSLA vs. S&P 500

The empirical analysis covers the period 2015–2025 and uses log returns to estimate systematic risk through both OLS and RANSAC regression.

## Key Findings

### Simulation Results

When the data contain a high proportion of outliers, OLS becomes sensitive to extreme observations, while RANSAC remains much closer to the true beta.

With only 0.25% contamination, the two estimators converge, indicating that the divergence between OLS and RANSAC is primarily driven by extreme observations.

In the simulated calm regime:

- OLS beta: 1.4921
- RANSAC beta: 1.5000
- No statistically significant difference

In the simulated crisis regime:

- OLS beta: 1.3099
- RANSAC beta: 1.4792
- The difference is statistically significant

### Empirical Results

#### GOOG vs. S&P 500

- OLS beta: 1.144
- RANSAC beta: 1.201
- Approximately 35% of observations identified as outliers
- No statistically significant difference between the two estimators

#### TSLA vs. S&P 500

- OLS beta: 1.503
- RANSAC beta: 1.218
- Approximately 46% of observations identified as outliers
- The difference between the estimators is statistically significant

The results show that extreme observations can have a substantial impact on beta estimation, particularly for highly volatile assets such as TSLA.

## Main Takeaway

OLS performs adequately when returns are relatively stable and outliers are limited.

However, during periods characterized by high volatility, extreme observations and market stress, RANSAC can provide a more robust estimate of systematic risk.

The results highlight the importance of considering the characteristics of financial return distributions and market regimes when estimating systematic risk.

## Technologies

- Python
- NumPy
- Pandas
- SciPy
- scikit-learn
- yfinance
- Matplotlib
- Google Colab

## Project Structure

```text
robust-beta-ols-vs-ransac/
│
├── README.md
├── Robust_Beta_OLS_vs_RANSAC.ipynb
├── Paper_Robust_Beta.pdf
└── figures/
    ├── beta_comparison.png
    ├── crisis_vs_calm.png
    └── ...
## Reproducibility

The complete Python implementation is provided in the Jupyter Notebook.

The notebook includes:

- Financial return calculation
- OLS beta estimation
- RANSAC beta estimation
- Outlier detection
- Monte Carlo simulations
- Hypothesis testing
- Crisis vs. calm regime analysis
- Empirical analysis of GOOG and TSLA

The notebook can be run using Google Colab or a local Jupyter environment.

## Files

**`Robust_Beta_OLS_vs_RANSAC.ipynb`**

Complete Python implementation of the analysis.

**`Paper_Robust_Beta.pdf`**

Full research paper containing the theoretical framework, methodology, simulations and empirical results.

## Author

Andrea Ciliegio

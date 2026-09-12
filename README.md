# Robust Beta Estimation: OLS vs. RANSAC

## Overview

This project investigates the sensitivity of financial beta estimation to outliers and changing market regimes.

The analysis compares the traditional Ordinary Least Squares (OLS) estimator with the robust RANSAC (Random Sample Consensus) approach, combining controlled simulations with empirical analysis of real financial data.

The main objective is to investigate whether robust regression can provide a more reliable measure of systematic risk when financial returns contain extreme observations.

## Research Question

How do outliers and market stress affect beta estimation, and can a robust estimator such as RANSAC provide a more stable measure of systematic risk than traditional OLS?

## Methodology

The analysis consists of two main components.

### 1. Controlled Simulations

Synthetic financial data are generated from a known linear relationship with a true beta of 1.50.

The simulations examine the behaviour of OLS and RANSAC under different levels of data contamination:

- Low contamination: 0.25% outliers
- High contamination: 10% outliers
- Calm vs. crisis market regimes
- Vertical outliers in stock returns
- Leverage outliers in market returns
- Comparison of estimated betas with the true beta
- Hypothesis testing of the difference between OLS and RANSAC

The crisis regime is characterised by substantially higher volatility and a greater concentration of extreme observations, allowing the robustness of the two estimators to be evaluated under stressed market conditions.

### 2. Empirical Analysis

The methodology is applied to daily financial data for:

- GOOG vs. S&P 500
- TSLA vs. S&P 500

The empirical analysis covers the period 2015–2025 and uses log returns to estimate systematic risk through both OLS and RANSAC regression.

A separate crisis vs. calm analysis is also conducted for GOOG:

- Crisis period: 2020–2022
- Calm period: 2017–2019

## Key Findings

### Simulation Results

The controlled simulations show that beta estimation becomes increasingly sensitive to outliers as data contamination increases.

With 10% contamination, OLS deviates substantially from the true beta, while RANSAC remains much closer to the underlying relationship.

With only 0.25% contamination, the two estimators converge and produce estimates close to the true beta of 1.50.

The calm vs. crisis analysis further shows that OLS becomes significantly distorted under high volatility and heavy contamination, while RANSAC remains more stable.

### Empirical Results

#### GOOG vs. S&P 500

- OLS beta: 1.1442
- RANSAC beta: 1.2008
- 35.39% of observations identified as outliers
- No statistically significant difference between the two estimators

The relatively small difference indicates that outliers have a limited impact on GOOG's beta estimation over the full sample.

#### TSLA vs. S&P 500

- OLS beta: 1.5033
- RANSAC beta: 1.2181
- 45.81% of observations identified as outliers
- The difference between the estimators is statistically significant

The large discrepancy highlights the sensitivity of OLS to extreme observations in highly volatile assets such as TSLA.

#### GOOG: Crisis vs. Calm

During the crisis period (2020–2022):

- OLS beta: 0.9931
- RANSAC beta: 1.1095
- p-value: 0.0021
- Statistically significant difference

During the calm period (2017–2019):

- OLS beta: 1.3665
- RANSAC beta: 1.3774
- p-value: 0.8367
- No statistically significant difference

These results show that the divergence between OLS and RANSAC becomes much more pronounced during stressed market conditions.

## Main Takeaway

The results demonstrate that beta estimation is highly sensitive to the data environment in which it is performed.

OLS remains appropriate under relatively stable market conditions, where extreme observations are limited. However, during periods characterised by high volatility, shocks and irregular observations, OLS can become distorted.

RANSAC provides a more robust estimate of systematic risk by identifying and excluding anomalous observations, while producing results similar to OLS when the data are well behaved.

The findings suggest that combining classical and robust estimation techniques can provide a more complete assessment of systematic risk, particularly for volatile assets and stressed market regimes.

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

    robust-beta-ols-vs-ransac/
    │
    ├── README.md
    ├── Robust_Beta_OLS_vs_RANSAC.ipynb
    └── Paper_Robust_Beta.pdf

## Reproducibility

The complete Python implementation is provided in the Jupyter Notebook.

The notebook includes:

- Financial return calculation
- OLS beta estimation
- RANSAC beta estimation
- Outlier detection
- Controlled synthetic-data simulations
- Calm vs. crisis regime analysis
- Hypothesis testing
- Empirical analysis of GOOG and TSLA

The notebook can be run using Google Colab or a local Jupyter environment.

## Files

**`Robust_Beta_OLS_vs_RANSAC.ipynb`**

Complete Python implementation of the analysis.

**`Paper_Robust_Beta.pdf`**

Full research paper containing the theoretical framework, methodology, simulations and empirical results.

## Author

Andrea Ciliegio

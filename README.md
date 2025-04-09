# Uncovering Stock Market Trends: A Statistical Exploration and Predictive Analysis

**Authors:** Xin Jiang, Ziyue Yin, Yitong Zhou, Yunheng Wang \
**Course:** Duke COMPSCI 216: Everything Data

## Overview

This project investigates short-term risk and predictive modeling for the Dow Jones Industrial Average (DJIA) using advanced Bayesian statistical methods. We focus on estimating and forecasting key financial risk metrics—**Value-at-Risk (VaR)** and **Expected Shortfall (ES)**—while exploring the influence of statistical and sentiment indicators.

## Research Questions

1. **Statistical Indicators:**  
   How do daily indicators (e.g., returns, volatility, volume) for DJIA evolve, and can we detect statistically meaningful anomalies?

2. **Market Drivers:**  
   Which factors drive short-term fluctuations in DJIA stock prices, and how can we quantify their effects using statistical inference?

3. **Predictive Modeling:**  
   Can a Bayesian model accurately forecast DJIA movements and financial risks based on recent data?

## Data Sources

- **DJIA Daily Data (2021–2024)**  
  Source: [Yahoo Finance](https://finance.yahoo.com/quote/%5EDJI/history/)  
  Includes: adjusted close prices, trading volume, highs/lows, computed daily log returns.

- **Stock Market Headlines Dataset**  
  Source: [Kaggle - lykin22/stock-headlines](https://www.kaggle.com/datasets/lykin22/stock-headlines)  
  Includes: daily financial news headlines, processed for sentiment (positive/neutral/negative) using NLP techniques.

## Methods & Modules Used

### Tools & Libraries
- Python
- NumPy, Pandas
- Matplotlib, Seaborn
- Scipy/Statsmodels
- NLP libraries for sentiment scoring

### Relevant Course Modules
- **Module 3:** Visualization (time series, KDE, QQ plots)
- **Module 7:** Statistical Inference (Bayesian methods, hypothesis testing)
- **Module 8:** Prediction & Supervised ML (Bayesian forecasting for VaR and ES)

### Bayesian Modeling
Used **Gibbs Sampling** to estimate:
- Mean ($\mu$)
- Variance ($\sigma^{2}$)

Model: $x_i \sim N(\mu, \sigma^2)$

Priors:  
- $\mu \sim N(0, 1000)$
- $\sigma^2 \sim \text{Inv-Gamma}(0.1, 0.1)$

## Preliminary Results

- **Descriptive Stats for Log Returns (n=983):**  
  Mean: 0.0004, Std Dev: 0.00896, Skew: -0.206, Kurtosis: 1.72

- **Risk Measure Estimates (99% Confidence):**
  | Metric | Mean Estimate | Std. Dev |
  |--------|----------------|----------|
  | VaR    | -0.03882       | 0.00102  |
  | ES     | -0.04453       | 0.00112  |

Visual tools like KDE plots, QQ plots, and trace plots confirm mild deviation from normality and effective convergence of the Gibbs sampler.

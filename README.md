
# Statistical Learning & Data Analysis: Regression and Data Simulation

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Overview
This repository contains the code, data generation scripts, and presentation for **Statistical Learning and Data Analysis** course at the *Università degli Studi di Napoli Federico II*.

By controlling the data-generating process through simulation, this project investigates:
1. **Estimation Accuracy & Consistency** of Ordinary Least Squares (OLS) under classical linear regression assumptions.
2. **Model Diagnostics & Sensitivity**, including residual analysis, leverage, and Cook's distance for influential points.
3. **Shrinkage & Regularization Techniques** (Ridge, Lasso, and Elastic Net) for variable selection and high-dimensional sparse recovery.
4. **The Bias-Variance Tradeoff** in non-linear regression (polynomial models) and the moderating effect of sample size.

---

## Author
* **Ammar Gharaf** (D03000248)

*Department of Mathematics / Statistical Learning and Data Analysis*  
**Università degli Studi di Napoli Federico II**

---

## Key Findings & Summary

### 1. Linear Setup & OLS Recovery
We simulated a sparse dataset with $n = 300$ observations, $p = 10$ predictors, and standard normal noise $\varepsilon \sim \mathcal{N}(0,1)$, where only 3 predictors possessed non-zero true coefficients:
$$\beta_{\text{true}} = [2.0, 3.0, -2.5, 1.5, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0, 0.0]^T$$

* **OLS Performance:** OLS accurately recovered the underlying signals ($\hat{\beta}_1 \approx 2.997$, $\hat{\beta}_2 \approx -2.540$, $\hat{\beta}_3 \approx 1.505$) with high $R^2 = 0.994$.
* **Diagnostics:** Residuals confirmed homoscedasticity and linearity. Influence analysis (Cook's distance) identified minor high-leverage points without model instability.

### 2. Regularization & Feature Selection
Using cross-validated Ridge, Lasso, and Elastic Net models:
* **Lasso ($\mathcal{L}_1$):** Successfully drove the 7 noise predictor coefficients to exactly zero, isolating the true sparse signal.
* **Ridge ($\mathcal{L}_2$):** Continuous shrinkage stabilized parameters while retaining all features.

### 3. Non-Linear Modeling & Bias-Variance Tradeoff
Simulated non-linear data following $y = 2 + 3\sin(x) + \varepsilon$:
* **Degree-10 Polynomial ($n=10$):** Suffer from severe overfitting (high variance).
* **Degree-10 Polynomial ($n=200$):** Increasing sample size mitigates variance, stabilizing the fit toward the ground truth.

---

## Project Structure

```text
.
├── notebooks/
│   └── Assignment_3_Regression_and_Data_Simulation.ipynb   # Main Jupyter/Colab notebook
├── presentation/
│   └── Presentation-Third-Assignment.pdf                  # Summary slide deck
├── README.md                                               # Repository documentation
└── requirements.txt                                        # Dependencies

```

---

## Getting Started

### Prerequisites

Make sure you have Python installed. You can install the required dependencies using `pip`:

```bash
pip install -r requirements.txt

```

### Dependencies

* `numpy`
* `pandas`
* `matplotlib`
* `statsmodels`
* `scikit-learn`

---

## Usage

Run the Jupyter Notebook locally or open it in Google Colab to reproduce the simulations and plots:

```bash
jupyter notebook notebooks/Assignment_3_Regression_and_Data_Simulation.ipynb

```



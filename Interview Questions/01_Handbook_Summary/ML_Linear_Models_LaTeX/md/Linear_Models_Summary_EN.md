# Summary: Linear Models for Machine Learning

This document provides a concise overview of the key concepts covered in the master-level technical handbook.

## 1. Task Typology
- **Regression:** Predicting continuous values (Metrics: MSE, MAE).
- **Classification:** Categorizing objects (Metrics: Accuracy, F1, ROC-AUC).
- **Ranking:** Predicting the relative order of items (Metrics: nDCG, MRR).

## 2. Mathematical Foundation
- **OLS (Ordinary Least Squares):** Solved via the normal equation $\omega = (X^TX)^{-1}X^Ty$.
- **QR Decomposition:** A numerically stable way to compute OLS weights.
- **Gradient Descent:** Iterative optimization: $w_{t+1} = w_t - \eta \nabla Q$.

## 3. Data Preprocessing & Interpretability
- **One-Hot Encoding:** Categorical conversion. Requires dropping one column to avoid the **Dummy Variable Trap**.
- **Interpretability:** Standardized weights $\omega_i$ indicate feature importance.
- **Limitations:** Assumes linearity, sensitive to outliers, and unstable with multicollinearity.

## 4. Optimization & Regularization
- **SGD / Mini-batch:** Updating weights based on small subsets of data for efficiency.
- **L2 (Ridge):** Penalty on squared weights. Stabilizes the model against multicollinearity.
- **L1 (Lasso):** Penalty on absolute weights. Performs automatic **Feature Selection** by zeroing out coefficients.

## 5. Classification
- **Logistic Regression:** Uses the **Sigmoid** function and **Log-Loss**. Derived via Maximum Likelihood Estimation (MLE).
- **SVM:** Uses **Hinge Loss** to maximize the separating **Margin**.
- **Multiclass:** Implemented via **Softmax** and **Cross-Entropy**. Strategies include **One-vs-Rest (OvR)** and **One-vs-One (OvO)**.

## 6. Kernel Trick
- Enables linear models to work in non-linear spaces by replacing dot products with a Kernel function $K(x, y)$.
- **Key Kernels:** RBF (Gaussian), Polynomial, Linear, Sigmoid.
- **KDE:** Kernel Density Estimation for non-parametric distribution modeling.

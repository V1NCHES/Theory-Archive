# Quality Metrics: Executive Summary

Metrics bridge the gap between mathematical optimization and real-world business value.

---

## 1. Metrics Typology
*   **Offline Metrics**: Evaluated on historical data (test sets). Fast and cheap. Used for rapid model iteration. (e.g., ROC-AUC, RMSE).
*   **Online Metrics**: Measured via A/B tests on real users. Slow and expensive. Reflects actual business impact. (e.g., CTR, Conversion Rate, ARPU).

## 2. Loss Function vs Quality Metric
*   **Loss Function**: Used for **training** (optimization goal). Must be differentiable. (e.g., LogLoss, MSE).
*   **Metric**: Used for **evaluation** (human/business goal). Must be interpretable. (e.g., Accuracy, F1-score).

## 3. Classification Metrics
*   **Accuracy**: Percentage of correct predictions. Misleading in imbalanced datasets.
*   **Precision**: Quality of positive predictions (minimizes FP). Crucial when false alarms are costly.
*   **Recall**: Ability to find all positive instances (minimizes FN). Crucial when missing an event is dangerous.
*   **F1-Score**: Harmonic mean of Precision and Recall.
*   **ROC-AUC**: Ranking quality. Invariant to class distribution. Probability that a random (+) is ranked higher than a random (-).
*   **PR-AUC**: Superior for highly imbalanced datasets (fraud detection, rare diseases).

## 4. Regression Metrics
*   **MSE (Mean Squared Error)**: Heavily penalizes outliers. Great as a loss function.
*   **MAE (Mean Absolute Error)**: Robust to outliers. Interpretable in target units.
*   **MAPE / WAPE**: Percentage-based error. Intuitive for business stakeholders.
*   **RMSLE**: Log-scale error. Used when targets span multiple orders of magnitude. Penalizes underestimation more.

---

## Interview Cheat Sheet
1.  **Why not optimize Accuracy directly?** It is a step function with zero derivatives almost everywhere; gradient descent cannot optimize it.
2.  **ROC-AUC vs PR-AUC**: Use ROC-AUC for balanced classes. Use PR-AUC when you care about the rare positive class (imbalanced data).
3.  **Handling Outliers**: If your data is noisy with significant outliers, MAE is a safer choice than MSE for evaluation.

# Ensembles and Gradient Boosting: Topics and Questions

## Core Topics
1. **Bias-Variance Decomposition**
   - Error = Bias + Variance + Noise.
   - **Bagging**: Averaging predictions of independent models. Primary goal: **Reduce Variance**.
   - **Boosting**: Sequential error correction. Primary goal: **Reduce Bias**.

2. **Random Forest (RF)**
   - Combination of Bagging and Random Subspace method.
   - **Bootstrap**: Sampling $N$ objects with replacement. ~63.2% unique objects included.
   - **Out-of-bag (OOB) error**: Quality estimation on samples not included in the bootstrap (free validation).
   - Hyperparameters: $n = \sqrt{N}$ features for classification, $n = N/3$ for regression.

3. **Gradient Boosting (GBDT)**
   - Gradient descent in functional space. Training on the anti-gradient of the loss function (residuals).
   - **Shrinkage (Learning Rate)**: Slowing down training for better generalization.
   - Implementations: XGBoost (2nd derivatives), LightGBM (GOSS, EFB, Leaf-wise), CatBoost (Ordered Boosting, categorical features).

4. **Stacking**
   - Meta-model trained on top of base model predictions.
   - Training on **Out-of-fold** predictions (via cross-validation) to prevent the meta-model from overfitting.

---

## Interview Questions
1. **Why does Random Forest not overfit as the number of trees increases?**
   - *Answer*: Averaging independent models with the same bias doesn't change the ensemble's bias but reduces variance. The error stabilizes on a plateau.

2. **What is the significance of 63.2% in Bootstrap?**
   - *Answer*: The probability of an object NOT being sampled as $N \to \infty$ is $1/e \approx 0.368$. Thus, $1 - 1/e \approx 0.632$ unique objects are included.

3. **What is the difference between GBDT and AdaBoost?**
   - *Answer*: AdaBoost adjusts object weights (exponential loss), while GBDT minimizes any differentiable loss function by approximating its gradient.

4. **Why use Stacking if we have Boosting?**
   - *Answer*: Stacking combines models of different natures (e.g., k-NN and Linear Regression), learning which model performs better in specific data regions.

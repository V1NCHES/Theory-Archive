# Cross-Validation: Topics and Interview Questions

## Core Topics
1. **Basic Concepts**
   - Purpose of cross-validation (estimating generalization ability).
   - Bias-variance trade-off in model evaluation.
   - Training, validation, and test sets.

2. **Splitting Methods**
   - **K-Fold**: Standard approach, choosing the number of folds (K=5, K=10).
   - **Stratified K-Fold**: Preserving class proportions (critical for classification with imbalanced data).
   - **Leave-One-Out (LOOCV)**: Extreme case of K-Fold (K=N). Pros: Unbiased estimate. Cons: High computational cost and high variance of the estimate.
   - **Shuffle & Split**: Random permutations.

3. **Domain-Specific Data**
   - **Time Series Split**: Sliding/expanding window, avoiding "look-ahead bias" (using future data to predict the past).
   - **Group K-Fold**: When samples are grouped (e.g., multiple images of the same patient) — samples from one group must stay in the same fold to prevent data leakage.

4. **Advanced Techniques**
   - **Nested Cross-Validation**: Nested loops for unbiased hyperparameter tuning (inner loop for tuning, outer loop for quality estimation).

---

## Interview Questions
1. **Why use cross-validation instead of a simple train/test split?**
   - *Answer*: A single train/test split provides an estimate based on one specific partition, which might be lucky or unlucky. Cross-validation averages results over multiple splits, making the estimate more stable and using all data for evaluation.

2. **How does the number of folds (K) affect Bias and Variance?**
   - *Answer*: A large K (e.g., LOOCV) reduces Bias (the model is trained on almost all data) but increases the Variance of the estimate and computational cost. A small K increases Bias.

3. **What is Data Leakage in the context of cross-validation?**
   - *Answer*: For example, fitting a scaler (StandardScaler) on the entire dataset before splitting into folds. The correct way is to fit on train folds and transform the validation fold.

4. **When is it mandatory to use Stratified K-Fold?**
   - *Answer*: In classification tasks, especially with severe class imbalance, to ensure that each fold maintains the original class distribution.

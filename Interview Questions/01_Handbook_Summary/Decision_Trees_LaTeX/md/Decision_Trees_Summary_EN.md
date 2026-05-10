# Decision Trees: Topics and Interview Questions

## Core Topics
1. **Construction Algorithm**
   - Greedy recursive splitting (Top-down induction).
   - Defining predicates (thresholds for continuous features).
   - **Algorithmic Complexity**: Naive search is $O(ND^2)$ or $O(N \log N \cdot D)$. Optimization via sorting and Dynamic Programming (tracking sums/squares while moving the threshold) reduces complexity.

2. **Impurity Measures**
   - **Classification**: Misclassification error, Shannon Entropy, Gini Impurity.
   - **Regression**: MSE (Mean Squared Error), MAE (Mean Absolute Error).

3. **Regularization (Stopping Criteria)**
   - Maximum depth (max_depth).
   - Minimum samples in a leaf (min_samples_leaf) or for a split (min_samples_split).
   - Maximum number of leaves.
   - Minimum impurity decrease.
   - **Pruning**: Removing branches after construction to combat overfitting.

4. **Data Handling & Tricks**
   - **Categorical Features**: DP approaches to find the optimal category split.
   - **Missing Values**: Surrogate splits.
   - **Histogram Method**: Binning continuous features to accelerate split finding (key in GBDT implementations).

---

## Interview Questions
1. **Gini Impurity vs. Entropy? Which is better?**
   - *Answer*: Results are almost always identical. Gini is slightly faster (no logarithms), while Entropy is slightly more sensitive to node purity.

2. **Why are decision trees prone to overfitting?**
   - *Answer*: Trees have low Bias but very high Variance. They can perfectly memorize the training set (down to one sample per leaf), losing generalization ability.

3. **Can a decision tree extrapolate?**
   - *Answer*: No. A tree outputs a constant value within each leaf. Beyond the training data range, it will output the constant value of the corresponding boundary leaf.

4. **How does a tree handle continuous features efficiently?**
   - *Answer*: It sorts the values and tests midpoints as thresholds. Using DP (updating mean/variance in O(1) as the threshold moves), search complexity for one feature is $O(N \log N)$.

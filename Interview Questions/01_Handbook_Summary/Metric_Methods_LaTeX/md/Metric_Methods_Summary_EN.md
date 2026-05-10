# Metric Methods: Executive Summary

Metric-based learning is founded on the "compactness hypothesis": objects with similar features tend to have similar target values.

---

## 1. k-Nearest Neighbors (k-NN)
*   **Core Idea**: Predictions for object $x$ are based on the targets of its $k$ nearest neighbors.
*   **Classification**: Majority voting (mode of neighbor classes).
*   **Regression**: Arithmetic mean (or weighted mean) of neighbor targets.
*   **Parameter $k$**: 
    *   Small $k$ — Overfitting (High Variance).
    *   Large $k$ — Underfitting (High Bias).
*   **Critical**: Feature scaling (Normalization/Standardization) is mandatory.

## 2. Distance Metrics
*   **L1 (Manhattan)**: $\sum |x_i - z_i|$. Robust to outliers.
*   **L2 (Euclidean)**: $\sqrt{\sum (x_i - z_i)^2}$. Standard straight-line distance.
*   **Cosine**: $1 - \cos(\theta)$. Measures vector orientation (crucial for NLP/Embeddings).
*   **Jaccard**: $1 - \frac{|A \cap B|}{|A \cup B|}$. Used for sets and binary features.

## 3. Weighted k-NN and Kernel Smoothing
*   **Weights**: Can be rank-based (linear, exponential) or distance-based.
*   **Kernels ($K$)**: Epanechnikov (optimal), Gaussian (smooth), Quartic.
*   **Nadaraya-Watson Regression**: Estimating values as a weighted average of all training samples using kernel-based weights.
*   **Window ($h$)**: Fixed radius or adaptive (distance to the $(k+1)$-th neighbor).

## 4. Search Optimization
*   **Exact Methods**: k-d trees (best for $d < 20$), Ball trees.
*   **Approximate (ANN)**: 
    *   **LSH**: Hashing-based bucketing for rapid lookup.
    *   **HNSW**: Hierarchical Navigable Small World graphs (modern state-of-the-art).
    *   **IVF**: Inverted File Index based on Voronoi cells.

---

## Interview Cheat Sheet
1.  **Curse of Dimensionality**: In high dimensions, distances between points become nearly equal, making the concept of "nearest" meaningless.
2.  **KD-tree degradation**: When $d > 50$, search complexity approaches $O(N)$, potentially becoming slower than brute-force.
3.  **Why Scale Features?**: To prevent features with large numeric ranges (e.g., "Salary") from dominating those with smaller ranges (e.g., "Age").

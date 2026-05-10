# Hyperparameter Tuning: Topics and Interview Questions

## Core Topics
1. **Basic Strategies**
   - **Grid Search**: Exhaustive search over a specified subset of the hyperparameter space. Pros: Reliability. Cons: "Curse of dimensionality", inefficient if some parameters are unimportant.
   - **Random Search**: Randomly samples the parameter space. Often more efficient than Grid Search because it explores more unique values of important parameters.

2. **Bayesian Optimization**
   - Surrogate model concept (Gaussian Processes, TPE).
   - Acquisition functions (Expected Improvement, UCB).
   - Tools: Optuna, Hyperopt, Scikit-Optimize.

3. **Modern Accelerated Methods**
   - **Successive Halving**: Discarding poorly performing configurations at early stages.
   - **Hyperband**: Combination of Random Search and Successive Halving.

4. **Validation Nuances**
   - Overfitting to the validation set during extensive tuning.
   - Importance of fixing the Random Seed.

---

## Interview Questions
1. **Why is Random Search often better than Grid Search?**
   - *Answer*: In high-dimensional spaces, many parameters may have little effect on the result. Random Search allows for checking more unique values of the influential parameters.

2. **How does the Optuna library work?**
   - *Answer*: It uses the TPE (Tree-structured Parzen Estimator) algorithm for smart parameter selection and Pruning mechanisms to stop unpromising trials.

3. **What should you do if hyperparameter tuning takes too long?**
   - *Answer*: Use subsampling (training on a smaller portion of data), narrow the search space, apply Hyperband, or start with pre-tuned parameters from similar tasks.

4. **What is the difference between parameters and hyperparameters?**
   - *Answer*: Parameters are learned by the model (e.g., weights in regression), while hyperparameters are set by the user before training (e.g., tree depth, C in SVM).

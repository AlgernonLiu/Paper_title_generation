## Expectation-Maximization (EM) Results

EM is an iterative algorithm that aims to maximize the likelihood of the observed data under a GMM. It iteratively estimates the parameters of the mixture model and updates the log likelihood until convergence.

### Log Likelihoods by \( K \):

- **K = 2**: [-6869.86, -6828.08, -6776.21, ...]
- **K = 3**: [-10432.65, -10052.02, -9818.82, ...]
- **K = 4**: [-13788.56, -13700.87, -13310.89, ...]
- **K = 5**: [-15183.85, -14983.13, -14500.11, ...]

**Optimal \( K \) for EM**: \( K = 2 \)

**Reason**: The log likelihoods indicate that \( K = 2 \) achieves the highest likelihood without overfitting the data. It strikes a balance between model complexity and goodness-of-fit.

## Variational Bayesian (VB) Results

VB is a Bayesian approach that iteratively maximizes a lower bound on the model evidence. It provides a probabilistic framework to estimate the parameters and number of components in a GMM.

### Lower Bounds by \( K \):

- **K = 2**: [-6.30, -6.30, -6.30, -6.30]
- **K = 3**: [-6.00, -5.96, -5.96, -5.96, -5.96]
- **K = 4**: [-5.67, -5.67, -5.67, -5.67]
- **K = 5**: [-5.67, -5.67, -5.67, -5.67, ...]

**Optimal \( K \) for VB**: \( K = 3 \)

**Reason**: The lower bounds indicate that \( K = 3 \) provides the best balance between model complexity and evidence lower bound. It suggests that this configuration is most likely given the data.

## Output Files Explanation

### `params.dat`

- **pi**: The mixing coefficients \( \pi \) for each component in the GMM.
- **mu**: The mean vectors \( \mu \) for each component in the GMM.
- **Lambda**: The precision matrices \( \Lambda \) (inverse covariance matrices) for each component in the GMM.

This file records the parameters learned by the algorithms after convergence, representing the probabilistic description of the GMM.

### `z.csv`

This file contains the posterior probabilities (also known as responsibility matrix) \( \gamma \), which assigns each data point to each component of the mixture model. Each row corresponds to a data point, and each column corresponds to a component.

---

### Usage

To reproduce these results:

1. Ensure Python and necessary libraries (numpy, pandas, matplotlib, scikit-learn) are installed.
2. Clone this repository and navigate to the directory.
3. Place your dataset in `x.csv` format.
4. Run the main script or respective modules for EM and VB algorithms.

Adjust paths and details as per your actual implementation and dataset.

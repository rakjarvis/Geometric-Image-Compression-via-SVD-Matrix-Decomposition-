# Geometric Image Compression via SVD (Matrix Decomposition)

A from-scratch Computer Vision (CV) pipeline that demonstrates how to compress digital images using fundamental Linear Algebra principles. This project utilizes Singular Value Decomposition (SVD) to strip low-importance geometric data from an image matrix, saving over 75% in storage size while maintaining structural integrity.

---

## The Mathematics Behind the Project

This project treats an image as a pure numerical matrix $A$ and applies **Matrix Decomposition**:

1. **Singular Value Decomposition ($A = U \cdot \Sigma \cdot V^T$):** Breaks down the 400x400 image matrix into spatial feature maps ($U$ and $V^T$) and a sorted weight distribution ($\Sigma$).
2. **Dimension Reduction & Subspaces:** By selecting the top $K$ singular values, we project the image into a lower-dimensional subspace that captures the maximal variance (energy) of the visual data.
3. **Low-Rank Matrix Approximation:** We prove the Eckart-Young-Mirsky theorem in practice, demonstrating that a rank-$K$ approximation can preserve the global structural features of a high-resolution image while ditching localized noise.

---

## Tech Stack & Concepts Used

* **Python 3** (Functional programming and matrix indexing)
* **NumPy** (`np.linalg.svd` for high-performance decomposition and vectorization)
* **Matplotlib** (Image rasterization and multi-plot rendering layouts)
* **Scikit-Image** (Internal environment dataset manipulation)

---

## Performance Analytics

* **Original Size:** 160,000 values ($400 \times 400$)
* **Rank-5 Reconstruction:** Abstract, blurry silhouette; retains macroscopic spatial layout.
* **Rank-50 Reconstruction:** Captures high-frequency visual details (whiskers, fur textures) perfectly while dropping 75% of the underlying mathematical payload.

# SyntheticCircle Clustering Analysis

## 📌 Project Overview

This project explores **unsupervised machine learning clustering techniques** on a synthetic 2D dataset. The goal is to identify natural groupings in the data and compare the performance of different clustering algorithms using both **internal** and **external evaluation metrics**.

The study compares:

* K-Means Clustering
* Hierarchical (Agglomerative) Clustering
* DBSCAN (Density-Based Spatial Clustering)

Additionally, **Principal Component Analysis (PCA)** is used for visualization and interpretability of clustering results.

---

## 🎯 Objectives

* Apply multiple clustering algorithms to the same dataset
* Evaluate clustering performance using internal and external metrics
* Visualize cluster structures in both original and PCA-reduced space
* Compare algorithm strengths and weaknesses
* Understand the effect of data structure on clustering performance

---

## 🚀 Technologies Used

* Python 🐍
* NumPy
* Pandas
* Scikit-learn
* Matplotlib
* Seaborn

---

## 📊 Dataset

The dataset consists of:

* `x`, `y` → numerical features
* `class` → ground truth labels (used only for evaluation)

The dataset is suitable for clustering because it contains multiple natural group structures and potential non-linear separations.

---

## ⚙️ Methods Used

### 1. K-Means Clustering

* Partitions data into K clusters
* Minimizes within-cluster variance
* Requires predefined number of clusters

### 2. Hierarchical Clustering

* Builds clusters using a tree-based approach
* Uses Ward linkage method
* Does not require initialization

### 3. DBSCAN

* Density-based clustering algorithm
* Detects arbitrary-shaped clusters
* Identifies noise points automatically

---

## 📉 Evaluation Metrics

### Internal Metrics (No Ground Truth)

* **Silhouette Score** → Measures cluster separation quality
* **Davies-Bouldin Index** → Measures cluster compactness (lower is better)
* **Calinski-Harabasz Index** → Measures cluster separation strength

### External Metrics (Uses Ground Truth)

* **Adjusted Rand Index (ARI)** → Measures agreement with true labels
* **Normalized Mutual Information (NMI)** → Measures shared information between clusters and true labels

---

## 📦 Preprocessing Steps

* Missing value handling
* Feature scaling using StandardScaler
* Dimensionality reduction using PCA (for visualization only)

---

## 📈 Hyperparameter Tuning

* **K-Means:** Elbow method + Silhouette analysis
* **DBSCAN:** k-distance graph to estimate `eps`
* **Hierarchical:** Ward linkage with fixed cluster comparison

---

## 📊 Key Results Summary

| Algorithm    | Silhouette | DBI   | CHI    | ARI   | NMI   |
| ------------ | ---------- | ----- | ------ | ----- | ----- |
| K-Means      | ~0.41      | ~0.76 | ~10224 | ~0.06 | ~0.46 |
| Hierarchical | ~0.33      | ~0.89 | ~7660  | ~0.06 | ~0.46 |
| DBSCAN       | ~0.56      | ~0.67 | ~23902 | ~0.95 | ~0.98 |

---

## 🔍 Key Insights

* DBSCAN significantly outperformed centroid-based methods
* K-Means and Hierarchical clustering struggled with non-linear structures
* Internal metrics showed moderate clustering quality, but external metrics revealed poor label alignment for K-Means and Hierarchical
* PCA helped visualize cluster separation but did not alter clustering results

---


## 📈 Future Improvements

* Apply HDBSCAN or OPTICS for improved density clustering
* Test on higher-dimensional real-world datasets
* Use ensemble clustering techniques
* Explore alternative distance metrics (cosine, Manhattan, Mahalanobis)

---

## 📌 Conclusion

DBSCAN is the most suitable algorithm for this dataset due to its ability to detect non-linear cluster structures and handle noise effectively. K-Means and Hierarchical clustering perform adequately in terms of internal structure but fail to capture true underlying labels.

---

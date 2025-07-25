# Agglomerative-Clustering-Project
A Python project demonstrating Agglomerative (Hierarchical) Clustering using synthetic data with make_blobs. The project visualizes how the algorithm groups data points into clusters.
# Agglomerative Clustering Project

This project demonstrates **Agglomerative Clustering**, a hierarchical clustering algorithm, using synthetic datasets generated with `make_blobs`. The project visualizes how data points are grouped into clusters step by step.

---

## **What is Agglomerative Clustering?**
Agglomerative Clustering is a **bottom-up hierarchical clustering approach**:
1. Each data point starts as its own cluster.
2. The algorithm merges the closest clusters based on a distance metric (e.g., Euclidean distance).
3. This process continues until the required number of clusters is formed.

In this project, we use **4 clusters** and visualize the results.

---

## **Technologies Used**
- Python 3
- Scikit-learn
- Matplotlib

---

## **Project Steps**
1. **Generate synthetic data** with 300 points using `make_blobs`.
2. **Apply Agglomerative Clustering** with:
   - `n_clusters=4`
   - `metric="euclidean"`
   - `linkage="ward"`
3. **Visualize the clusters** using Matplotlib scatter plots.

---

## **Code Example**
```python
from sklearn.cluster import AgglomerativeClustering
from sklearn.datasets import make_blobs
import matplotlib.pyplot as plt

# Generate synthetic data
data, _ = make_blobs(n_samples=300, centers=4, cluster_std=0.60, random_state=0)

# Agglomerative Clustering
agg_cluster = AgglomerativeClustering(n_clusters=4, metric="euclidean", linkage="ward")
clusters = agg_cluster.fit_predict(data)

# Plotting the clusters
plt.figure(figsize=(8, 6))
plt.scatter(data[:, 0], data[:, 1], c=clusters, cmap="viridis", edgecolor='k')
plt.title("Agglomerative Clustering")
plt.xlabel("Feature 1")
plt.ylabel("Feature 2")
plt.show()

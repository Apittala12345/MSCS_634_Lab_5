# MSCS-634 Lab 5: Clustering Techniques Using DBSCAN and Hierarchical Clustering

**Student:** Anusha Pittala  
**Course:** MSCS-634 – Advanced Big Data and Data Mining  
**University:** University of the Cumberlands

## Project Overview

This lab focuses on applying Hierarchical Clustering and DBSCAN to the Wine dataset available in scikit-learn. The main purpose is to understand how these algorithms group similar data, compare their performance, and examine the effect of different clustering parameters.

## Dataset

The Wine dataset contains 178 samples and 13 numerical features representing chemical properties of wines. The dataset was explored using pandas functions such as `head()`, `info()`, and `describe()`.

No missing values were found. The features were standardized using StandardScaler before applying the clustering algorithms.

## Tools and Libraries

- Python
- Jupyter Notebook
- NumPy
- Pandas
- Matplotlib
- Scikit-learn
- SciPy

## Clustering Techniques

### Hierarchical Clustering

Agglomerative Hierarchical Clustering was applied using Ward linkage. Different numbers of clusters (2, 3, 4, and 5) were tested.

Scatter plots were generated to visualize the groupings, and a dendrogram was created to understand how the clusters were combined.

Among the tested settings, 3 clusters produced the highest Silhouette Score of approximately 0.277.

**Results for 3 clusters:**

- Silhouette Score: 0.277
- Homogeneity Score: 0.790
- Completeness Score: 0.783

### DBSCAN Clustering

DBSCAN was applied using different values of `eps` and `min_samples`. The results showed that these parameters significantly affect the number of clusters and noise points.

For `eps=2.5` and `min_samples=8`, the results were:

- Clusters identified: 2
- Noise points: 30
- Silhouette Score: 0.318 (excluding noise points)
- Homogeneity Score: 0.484
- Completeness Score: 0.545

The visualizations show the identified clusters and noise points marked with black X symbols.

## Key Insights

Hierarchical Clustering produced clear groupings when using 3 clusters. The dendrogram helped visualize the relationships between different groups of wine samples.

DBSCAN was more sensitive to parameter values. When `eps=1.5`, all 178 samples were classified as noise. Increasing `eps` allowed more samples to form clusters.

DBSCAN was useful for identifying noise points, while Hierarchical Clustering provided a more consistent grouping for this dataset.

The Silhouette Scores should be interpreted carefully because the Hierarchical score uses all samples, while the selected DBSCAN score excludes noise points.

## Challenges and Decisions

One challenge was choosing suitable parameter values for the clustering algorithms. For Hierarchical Clustering, I tested different numbers of clusters to compare the results.

For DBSCAN, some parameter combinations produced too many noise points, while others grouped most of the observations into one cluster.

Another challenge was understanding why the Silhouette Score was unavailable for certain DBSCAN settings. This happens when there are not enough non-noise clusters to calculate the score.

I used PCA to display the clustering results in two dimensions while performing the clustering on all 13 standardized features.

## Conclusion

This lab helped me understand the differences between Hierarchical Clustering and DBSCAN. Hierarchical Clustering was easier to interpret through the dendrogram, while DBSCAN demonstrated how density-based methods can identify noise points.

Testing different settings and comparing evaluation metrics showed how parameter selection can influence clustering results.

## Repository Files

- `MSCS_634_Lab_5.ipynb` – Jupyter Notebook containing the complete Python code, results, evaluation metrics, and visualizations.
- `README.md` – Project overview, findings, and challenges.

# K-Means Clustering in R — Data Mining Lab Report 3

**Student Index:** 23000422  
**Project Type:** Academic Data Mining Practical  
**Language:** R  
**Environment:** RStudio

## Overview

This assignment explores K-Means clustering using the Iris and Wine datasets. It covers data inspection, feature scaling, selecting the number of clusters, fitting clustering models, visualizing results, and evaluating clusters against known class labels.

## Objectives

- Apply K-Means clustering to the Iris and Wine datasets.
- Explore cluster sizes, centroids, and between-cluster variation.
- Visualize cluster assignments and centroids.
- Select a suitable number of clusters using the Elbow Method and NbClust.
- Standardize the Wine dataset's chemical features before clustering.
- Evaluate clustering using confusion matrices and the Adjusted Rand Index (ARI).
- Understand the principles, advantages, and limitations of K-Means.

## Datasets

### Iris
The built-in R `iris` dataset contains 150 observations, four numeric measurements, and a `Species` label with three species.

### Wine
The `winedata.csv` dataset contains 178 observations and 14 variables: 13 chemical measurements and a `Type` class label representing the wine cultivar.

> Ensure `winedata.csv` is included in the repository or provide clear instructions for obtaining it, subject to your course's sharing rules.

## Methods and Techniques

- **K-Means clustering:** Group observations based on feature similarity.
- **Reproducibility:** Use `set.seed()` and multiple initializations with `nstart = 20`.
- **Feature scaling:** Use `scale()` on the Wine chemical variables so measurements on larger numeric scales do not dominate distance calculations.
- **Cluster-count selection:** Compare the Elbow Method with the majority recommendation from `NbClust`.
- **Evaluation:** Compare cluster assignments with known labels using contingency tables and calculate the Adjusted Rand Index.
- **Visualization:** Create scatter plots, plot cluster centres, draw elbow/scree plots, and use `fpc::plotcluster()` for the Wine data.

## Reported Results

- **Iris:** The Elbow Method suggested approximately 3 clusters, while the reported NbClust majority recommendation was 2. This illustrates that different cluster-selection criteria can recommend different values of *k*.
- **Iris feature subset:** Using petal length and petal width produced a reported 6 mismatches after matching clusters to the dominant species labels (144/150, or 96%). This is a label-matching comparison, not a standard supervised classification accuracy.
- **Wine:** The Elbow Method and reported NbClust majority recommendation both suggested 3 clusters.
- **Wine evaluation:** The report recorded an Adjusted Rand Index of approximately **0.8975**, indicating strong agreement between the cluster assignments and known wine classes.

Results can vary with the chosen features, random initialization, package versions, and dataset file. Re-run the supplied R code to verify all numerical results and plots.

## R Packages and Tools

- `datasets` — built-in Iris dataset
- `NbClust` — cluster-count selection indices
- `fpc` — cluster visualization
- `flexclust` — Adjusted Rand Index calculation
- `MASS` — supporting statistical functions/package used in the lab setup
- `RStudio` — development environment

## How to Run

1. Install R and RStudio.
2. Open the `.R` script or R Markdown file for this lab in RStudio.
3. Place `winedata.csv` in the working directory used by the script.
4. Install required packages if they are not already installed:

   ```r
   install.packages(c("NbClust", "fpc", "MASS", "flexclust"))
   ```

5. Run the code section by section to generate console output, tables, and plots.

## Repository Contents

Suggested repository structure:

```text
k-means-clustering-r/
├── README.txt
├── lab_report_3.R
├── winedata.csv
└── plots/
```

Adjust these filenames to match the files actually included in your repository. Do not include `winedata.csv` unless you are permitted to share it.

## Key Learning Outcomes

- Practical experience with unsupervised machine learning.
- Data preprocessing and standardization.
- Cluster-count selection and model reproducibility.
- Cluster visualization and quantitative evaluation.
- Interpretation of clustering results and limitations.

---
Academic practical assignment completed as part of a Data Mining course.

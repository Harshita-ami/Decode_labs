# Data Science Project 3: Unsupervised Learning – Customer Segmentation

## 📌 Overview
This project is part of my Data Science Internship at **DecodeLabs** (Batch 2026).
The goal is to segment retail customers into distinct groups based on their
behavioral and demographic data, using unsupervised learning techniques, and
translate those groups into actionable business personas.

## 🎯 Objective
- Reduce a high-dimensional dataset into 2–3 dimensions using PCA
- Discover natural customer groupings using K-Means clustering
- Mathematically determine the optimal number of clusters using the Elbow
  Method and Silhouette Score
- Translate each cluster into a business-friendly persona with a suggested
  marketing action

## 📊 Dataset
This project uses the **Mall Customer Segmentation dataset** (Kaggle), containing
customer details such as Age, Annual Income, and Spending Score, with no
pre-labeled categories — making it suitable for unsupervised learning.

## 🛠️ Steps Performed

### 1. Feature Selection & Scaling
- Selected relevant numeric features: Age, Annual Income, and Spending Score
- Applied `StandardScaler` to bring all features to a common scale, preventing
  income (a large-magnitude variable) from dominating the distance calculations

### 2. Dimensionality Reduction — PCA
- Applied **Principal Component Analysis (PCA)** to compress the scaled features
  into 2 principal components
- Verified the amount of variance retained after reduction

### 3. Determining the Optimal Number of Clusters
- Used the **Elbow Method** to plot WCSS (Within-Cluster Sum of Squares)
  against different values of K, identifying the point of diminishing returns
- Confirmed the choice using the **Silhouette Score**, which measures how well
  each customer fits within their assigned cluster versus neighboring clusters
- Selected **K = [X]** as the optimal number of clusters based on both methods

### 4. K-Means Clustering
- Applied K-Means clustering with the chosen K on the PCA-reduced data
- Assigned each customer to a cluster label

### 5. Cluster Profiling & Business Personas
- Calculated the average Age, Income, and Spending Score per cluster
- Translated each cluster into a named business persona with a suggested
  marketing strategy

## 📈 Results — Customer Personas

| Cluster | Persona Name | Avg Age | Avg Income | Avg Spending Score | Suggested Action |
|---|---|---|---|---|---|
| 0 | [e.g., Budget-Conscious Seniors] | [X] | [$Xk] | [X] | [e.g., Basic value offers] |
| 1 | [e.g., Premium Trendsetters] | [X] | [$Xk] | [X] | [e.g., Early access, exclusive perks] |
| 2 | [e.g., Young Explorers] | [X] | [$Xk] | [X] | [e.g., Flash sales, influencer campaigns] |
| ... | ... | ... | ... | ... | ... |

*(Fill in the table above using the output from Cell 11/12 of the notebook.)*

## 🧰 Tools & Libraries
- Python
- Pandas, NumPy
- Scikit-Learn (StandardScaler, PCA, KMeans, silhouette_score)
- Matplotlib / Seaborn

## 📁 Files
- `Project_3_Customer_Segmentation.ipynb` — main notebook with all code and outputs

## 🙋 Author
[Harshita V Kundgol]
Data Science Intern @ DecodeLabs, Batch 2026

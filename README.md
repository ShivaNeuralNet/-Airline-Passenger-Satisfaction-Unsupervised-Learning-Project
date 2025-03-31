# ✈️ Airline Passenger Satisfaction — Unsupervised Learning Project

## Project Overview
This project applies **unsupervised learning** to analyze a dataset of airline passenger satisfaction surveys. The goal is to uncover hidden patterns, segment passengers, and understand what drives satisfaction using clustering and dimensionality reduction techniques.

---

## Tools & Libraries Used
- Python (Jupyter Notebook)
- pandas, numpy
- seaborn, matplotlib
- scikit-learn (KMeans, PCA, KernelPCA, Silhouette Score, Preprocessing Pipelines)
- scipy (Box-Cox transformation)

---

## Dataset Description
The dataset contains:
- **Demographic Info**: Gender, Age, Customer Type
- **Travel Details**: Flight Class, Distance, Travel Type
- **Service Ratings**: Seat Comfort, Boarding, Entertainment, etc.
- **Timing**: Departure/Arrival Delay
- **Target**: Passenger Satisfaction

Initial preprocessing steps:
- Removed unused columns
- Renamed columns for clarity
- Checked for missing values and outliers
- Analyzed distribution of features using histograms and `describe()`

---

## Exploratory Data Analysis (EDA)
- **Class vs Satisfaction**: Created proportional stacked bar charts to explore satisfaction levels by travel class.
- **Correlation Matrix**: 
  - Strong correlation between **Online Booking** and **Time Convenience** (0.72)
  - Extremely high correlation (0.97) between **Departure Delay** and **Arrival Delay**
- **FacetGrid Visualizations**: Used histograms to compare distributions of all categorical features against satisfaction.

---

## Feature Engineering
- Applied log and Box-Cox transformations to address skewness in delay variables
- Created preprocessing pipelines using `ColumnTransformer` and `OrdinalEncoder`
- Scaled numerical features with `StandardScaler`

---

## Clustering Analysis
- Started with 2-cluster and then 3-cluster **KMeans** models.
- Evaluated cluster quality using **Inertia** and the **Elbow Method**.
- Determined 3 clusters as optimal.

### Updated Cluster Summary (3 Clusters)
- **Cluster 0**: Majority neutral/dissatisfied (23,828 vs 4,679 satisfied)
- **Cluster 1**: Majority satisfied (32,207 vs 11,954 neutral/dissatisfied)
- **Cluster 2**: More neutral/dissatisfied than satisfied, but not as extreme as Cluster 0

**Insights**:
- Cluster 1 is the most satisfied group, ideal for retention strategies.
- Cluster 0 & 2 show dissatisfaction trends, indicating areas for improvement.

---

## Dimensionality Reduction with PCA & KernelPCA
- Applied PCA with 14 components to calculate feature contributions
- Compared **KernelPCA (3 components)** vs **PCA (14 components)** using **Silhouette Scores**
- Visualized clusters with color gradients based on distance in PCA space

**Conclusion**:
- Both methods provide good separation, but PCA with 14 components slightly outperforms KernelPCA based on Silhouette Score

---

## Final Thoughts
This project demonstrates end-to-end unsupervised learning using real-world survey data:
- Cleaned and explored data thoroughly
- Reduced skewness and scaled features
- Identified optimal clusters
- Applied and compared dimensionality reduction techniques

It highlights the power of clustering to understand customer satisfaction and create actionable insights.

---

## Next Steps
- Deep dive into features within each cluster
- Try DBSCAN or Gaussian Mixture Models
- Visualize with t-SNE or UMAP
- Build interactive dashboard to explore segments

---

## 👩‍💼 Author
Project completed by **Shiva Dorri** as part of her unsupervised learning journey into data science.

---

**Tags**: `#KMeans` `#PCA` `#KernelPCA` `#CustomerSegmentation` `#UnsupervisedLearning` `#DataScience`

# SmartCart Customer Segmentation

## Overview
This project performs customer segmentation on a retail dataset (SmartCart) using machine learning techniques. The main goal is to group customers based on their income, spending behavior, and demographics to better understand different customer types.

---

## Objective
- Identify distinct customer segments  
- Analyze spending patterns and customer behavior  
- Provide insights for targeted marketing  

---

## Dataset Details
The dataset includes:
- Customer demographics (Age, Education, Marital Status)
- Income information  
- Product spending (Wines, Fruits, Meat, Fish, Sweets, Gold)  
- Customer activity (Recency, Response)  
- Customer joining date  

---

## Project Workflow

### 1. Data Loading & Inspection
- Loaded dataset using Pandas  
- Checked structure using `.head()`, `.info()`, `.describe()`  

---

### 2. Data Cleaning
- Handled missing values in **Income** using median  
- Converted `Dt_Customer` to datetime format  

---

### 3. Feature Engineering
Created meaningful features:
- **Age** from Year_Birth  
- **Customer Tenure** (days since joining)  
- **Total Spending** (sum of all product categories)  
- **Total Children** (Kidhome + Teenhome)  

Simplified categories:
- Education → UnderGraduate, Graduate, PostGraduate  
- Marital Status → Partner / Alone  

---

### 4. Data Preprocessing
- Removed unnecessary columns (ID, Year_Birth, etc.)  
- Applied **One-Hot Encoding** on:
  - Education  
  - Living_with  
- Standardized features using **StandardScaler**  

---

### 5. Outlier Handling
- Removed unrealistic values:
  - Age > 90  
  - Income > 600,000  

---

### 6. Dimensionality Reduction
- Applied **PCA (Principal Component Analysis)**  
- Reduced data to 3 components for visualization and clustering  
- Captured most of the variance in reduced dimensions  

---

### 7. Clustering
Applied two clustering algorithms:

#### KMeans Clustering
- Used Elbow Method (WCSS)  
- Used Silhouette Score  
- Optimal clusters ≈ 4  

#### Agglomerative Clustering
- Applied hierarchical clustering with Ward linkage  

---

### 8. Visualization
- 3D PCA cluster visualization  
- Cluster distribution (countplot)  
- Income vs Spending scatter plot  

---

## Results & Insights
The model identified **4 customer segments**:

- **Cluster 0:** High income, high spending → Premium customers  
- **Cluster 1:** Low income, low spending → Budget customers  
- **Cluster 2:** High income, low spending → Potential targets  
- **Cluster 3:** Moderate income and spending → Regular customers  

---

## Technologies Used
- Python  
- Pandas, NumPy  
- Seaborn, Matplotlib  
- Scikit-learn  

---

## Conclusion
This project demonstrates how customer segmentation can help businesses understand customer behavior. By using PCA and clustering techniques, meaningful groups were identified, which can be used for better marketing strategies and decision-making.

---

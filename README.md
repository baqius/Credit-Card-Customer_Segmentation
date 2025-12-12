# Credit-Card-Customer_Segmentation
This project uses unsupervised machine learning (specifically, K-Means Clustering) to analyze a credit card dataset and automatically sort customers into distinct groups based on their spending and repayment habits over the last six months. The ultimate goal is to provide the credit card company with actionable customer segments for tailored marketing and risk management.


### The K-Means clustering algorithm identified four distinct groups of customers by grouping those with similar financial behaviors.

## Cluster Summary Table

| Cluster | Key Characteristics (Based on Mean Values) | Business Interpretation |
|---------|---------------------------------------------|--------------------------|
| Cluster 2 | Very high purchases (~$22k) and very high payments (~$24k), highest credit limit (~$15.6k). | High-value / VIP customers. Most profitable segment; they spend and repay large amounts. **Action:** Focus on retention and premium offers. |
| Cluster 0 | High balance (~$6k) and very high cash advance (~$5.8k), high credit limit (~$9.5k). | High-debt / revolving borrowers who carry large, high-interest balances and frequently use cash advances. **Action:** Offer debt management or balance transfer options. |
| Cluster 3 | Moderate purchases (~$2.1k), payments (~$2.7k), and balance (~$2.2k). | Average / mid-tier users with moderate activity and small revolving balances. **Action:** Encourage higher usage through rewards programs. |
| Cluster 1 | Low purchases, payments, cash advance, and balance across all metrics. | Low-activity / new users who show minimal usage or are newly onboarded. **Action:** Use re-engagement or introductory programs to boost activity. |



##  Data Preparation & Modeling Process

###  Data Preparation
- Missing values in the dataset were removed (specifically in **MINIMUM_PAYMENTS**).
- To choose the best features for clustering, **trimmed variance** was used (a robust method that reduces the impact of outliers).
- The top **5 selected features** were:
  - **PURCHASES**
  - **CASH_ADVANCE**
  - **PAYMENTS**
  - **BALANCE**
  - **CREDIT_LIMIT**

---

###  Model Training (K-Means)
- A **scikit-learn pipeline** was created using:
  - **StandardScaler** – to standardize feature scales  
  - **KMeans** – to perform clustering
- The model was evaluated using:
  - **Elbow Method (Inertia)**
  - **Silhouette Score**
- These metrics were tested for **k = 2 to k = 12**.
- The optimal number of clusters was determined to be **4**.

---

###  Visualization & Interpretation
- **Principal Component Analysis (PCA)** reduced the 5-dimensional data into **2 components (PC1 & PC2)** for visualization.
- A scatter plot displayed clear separation between the **4 clusters**.
- Mean values of the selected features were analyzed and plotted to define the **behavioral profile of each customer segment**.



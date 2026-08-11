#  Bank Customer Segmentation

> An end-to-end machine learning project that uses K-Means clustering to identify meaningful customer segments based on credit-card usage and financial behaviour.
Customer segmentation of bank customers using K-Means clustering to uncover financial and credit-card usage patterns and generate actionable business insights.

---

##  Project Overview

Banks have customers with very different spending, payment and credit-card usage patterns. Treating every customer in the same way can lead to ineffective marketing and customer engagement strategies.

This project applies **unsupervised machine learning** to identify groups of customers with similar financial behaviours.

The analysis uses **K-Means Clustering** to segment bank customers and translates the resulting clusters into actionable business insights.

###  Objective

The primary objective is to:

- Identify distinct customer behaviour patterns
- Segment customers using unsupervised machine learning
- Determine the optimal number of customer segments
- Profile each customer segment
- Develop business strategies for different customer groups

---

##  Dataset

The project uses a credit-card customer dataset containing approximately **9,000 customer records** and multiple behavioural and financial attributes.

### Key Features

| Feature | Description |
|---|---|
| `BALANCE` | Average balance maintained by the customer |
| `BALANCE_FREQUENCY` | Frequency of balance updates |
| `PURCHASES` | Total purchase amount |
| `ONEOFF_PURCHASES` | Total one-time purchase amount |
| `INSTALLMENTS_PURCHASES` | Installment purchase amount |
| `CASH_ADVANCE` | Cash advance amount |
| `PURCHASES_FREQUENCY` | Frequency of purchases |
| `CASH_ADVANCE_FREQUENCY` | Frequency of cash advances |
| `CREDIT_LIMIT` | Customer's credit limit |
| `PAYMENTS` | Amount paid by the customer |
| `MINIMUM_PAYMENTS` | Minimum payment amount |
| `PRC_FULL_PAYMENT` | Percentage of payments made in full |

---

#  Technologies Used

### Programming
- Python

### Data Analysis
- Pandas
- NumPy

### Data Visualization
- Matplotlib
- Seaborn

### Machine Learning
- Scikit-learn
- K-Means Clustering
- StandardScaler
- PCA
- Silhouette Score

### Environment
- Google Colab
- Jupyter Notebook

---

#  Project Workflow

```text
Dataset
   ↓
Data Cleaning
   ↓
Exploratory Data Analysis
   ↓
Missing Value Treatment
   ↓
Log Transformation
   ↓
Feature Scaling
   ↓
Elbow Method
   ↓
Silhouette Analysis
   ↓
K-Means Clustering
   ↓
Customer Profiling
   ↓
PCA Visualization
   ↓
Business Recommendations



##  Data Preprocessing

The following preprocessing steps were performed:

### 1. Duplicate Removal

Duplicate customer records were identified and removed to ensure data quality.

### 2. Missing Value Treatment

Missing values in:

- `MINIMUM_PAYMENTS`
- `CREDIT_LIMIT`

were handled using **median imputation**.

### 3. Customer ID Removal

`CUST_ID` was removed because it is an identifier and does not provide meaningful behavioural information for clustering.

### 4. Log Transformation

Financial variables showed significant right-skewness.

A `log1p()` transformation was applied to reduce the influence of extreme values while preserving zero-valued observations.

### 5. Feature Scaling

`StandardScaler` was applied so that features with different numerical ranges would contribute fairly to the K-Means distance calculations.

---

##  Exploratory Data Analysis

Exploratory Data Analysis (EDA) was performed to understand customer behaviour and identify patterns across important financial variables.

The analysis focused on:

- Balance
- Purchases
- Credit Limit
- Cash Advance
- Payments
- Full-Payment Behaviour

### Feature Distributions

![Feature Distributions](images/feature_distributions.png)

### Correlation Matrix

![Correlation Matrix](images/correlation_matrix.png)

---

##  Selecting the Number of Clusters

Two approaches were used to determine the appropriate number of clusters:

### 1. Elbow Method

The Elbow Method was used to examine the **Within-Cluster Sum of Squares (WCSS)** for different values of K.

![Elbow Method](images/elbow_method.png)

### 2. Silhouette Analysis

Silhouette Scores were calculated for K values ranging from **2 to 10**.

The highest score obtained during the analysis was:

###  K = 3

###  Silhouette Score = 0.2510

![Silhouette Scores](images/silhouette_scores.png)

Based on the evaluation, **3 clusters** were selected for the final K-Means model.

---

##  K-Means Clustering

The final model was trained using:

| Parameter | Value |
|---|---|
| **Algorithm** | K-Means |
| **Number of Clusters** | 3 |
| **Random State** | 42 |
| **Number of Initializations** | 10 |

Each customer was assigned to one of the three behavioural segments.

---

##  Customer Segments

The final clustering analysis identified three major customer groups.

###  Cluster 0 — High-Value Active Customers

#### Characteristics

- High purchase activity
- High payment activity
- Relatively high credit limit
- Relatively low cash-advance usage
- Higher full-payment behaviour

####  Business Strategy

Potential strategies include:

- Premium credit cards
- Exclusive rewards
- Cashback programs
- Personalized offers
- Loyalty programs
- Cross-selling relevant financial products

---

###  Cluster 1 — Low-Engagement Customers

#### Characteristics

- Lower purchase activity
- Lower payment activity
- Lower balance
- Lower credit limit compared with other segments

####  Business Strategy

Potential strategies include:

- Cashback campaigns
- Personalized promotions
- Loyalty incentives
- Card-usage campaigns
- Customer engagement programs

---

###  Cluster 2 — Cash-Advance Heavy Customers

#### Characteristics

- High balance
- Very high cash-advance usage
- Relatively low purchase activity
- Very low full-payment ratio

####  Business Strategy

Potential strategies include:

- Monitor cash-advance behaviour
- Encourage healthier repayment behaviour
- Offer appropriate financial-management products
- Provide personalized financial guidance
- Evaluate for additional credit-risk monitoring

> **Note:** The clustering model identifies behavioural patterns. It does not prove that customers are in default or are definitively high-risk.

---

## Customer Segment Distribution

The chart below shows the distribution of customers across the three identified behavioural segments.

![Customer Segment Distribution](images/cluster_distribution.png)

---

## Cluster Profile

The average behaviour of each cluster was analysed using:

- Balance
- Purchases
- Credit Limit
- Cash Advance
- Payments
- Percentage of Full Payment

### Key Cluster Profile Results

| Cluster | Balance | Purchases | Credit Limit | Cash Advance | Payments | Full Payment |
|---|---:|---:|---:|---:|---:|---:|
| **0** | 2,182.35 | 4,187.02 | 7,642.78 | 449.75 | 4,075.53 | 30% |
| **1** | 807.72 | 496.06 | 3,267.02 | 339.00 | 907.45 | 15% |
| **2** | 4,023.79 | 389.05 | 6,729.47 | 3,917.25 | 3,053.94 | 3% |

![Cluster Profile](images/cluster_profile.png)

---

## PCA Visualization

**Principal Component Analysis (PCA)** was used to reduce the dimensionality of the dataset to two dimensions for visualization.

The visualization provides a two-dimensional view of the identified customer groups.

![PCA Customer Segmentation](images/pca_clusters.png)

---

## Business Insights

The clustering analysis provides several actionable insights.

### 1. High-Value Active Customers

Customers with strong purchase and payment activity can be targeted with premium services, exclusive rewards and loyalty programs.

### 2. Low-Engagement Customers

Customers with lower activity can be targeted with personalized campaigns designed to increase card usage and customer engagement.

### 3. Cash-Advance Heavy Customers

Customers showing high cash-advance usage and low full-payment behaviour may benefit from closer behavioural monitoring and appropriate financial products.

---

## Business Applications

The segmentation framework can support:

- Customer profiling
- Personalized marketing
- Customer retention
- Loyalty programs
- Premium customer identification
- Cross-selling
- Upselling
- Campaign optimization
- Customer engagement
- Behaviour monitoring

---

##  Repository Structure

```text
bank-customer-segmentation/
│
├── bank_customer_segmentation.ipynb
├── README.md
│
└── images/
    ├── feature_distributions.png
    ├── correlation_matrix.png
    ├── elbow_method.png
    ├── silhouette_scores.png
    ├── cluster_distribution.png
    ├── cluster_profile.png
    └── pca_clusters.png





# Bank Customer Segmentation

> An end-to-end machine learning project that uses K-Means clustering to identify meaningful customer segments based on credit-card usage and financial behaviour.
Customer segmentation of bank customers using K-Means clustering to uncover financial and credit-card usage patterns and generate actionable business insights.


# Project Overview

Banks have customers with very different spending, payment and credit-card usage patterns. Treating every customer in the same way can lead to ineffective marketing and customer engagement strategies.

This project applies **unsupervised machine learning** to identify groups of customers with similar financial behaviours.

The analysis uses **K-Means Clustering** to segment bank customers and translates the resulting clusters into actionable business insights.

# Objective

The primary objective is to:

- Identify distinct customer behaviour patterns
- Segment customers using unsupervised machine learning
- Determine the optimal number of customer segments
- Profile each customer segment
- Develop business strategies for different customer groups

# Dataset

The project uses a credit-card customer dataset containing approximately **9,000 customer records** and multiple behavioural and financial attributes.

### Key Features

| Feature | Description |
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

# Technologies Used

# Programming
- Python

# Data Analysis
- Pandas
- NumPy

# Data Visualization
- Matplotlib
- Seaborn

# Machine Learning
- Scikit-learn
- K-Means Clustering
- StandardScaler
- PCA
- Silhouette Score

# Environment
- Google Colab
- Jupyter Notebook

---

# Project Workflow

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

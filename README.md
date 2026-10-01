# Customer Segmentation Analysis

## Project Overview

This project applies customer segmentation techniques to an e-commerce transaction dataset using RFM analysis and K-Means clustering.

The project was completed as part of the Oasis Infobyte Data Analytics Internship, Level 1, Task 2.

The analysis groups customers according to purchasing behaviour so that different customer groups can be approached with more targeted marketing strategies.

## Objectives

- Inspect the transaction dataset and identify missing or inconsistent records.
- Calculate customer-level Recency, Frequency, and Monetary features.
- Select behavioural features suitable for clustering.
- Standardize the clustering features using StandardScaler.
- Use the Elbow Method to determine a suitable number of clusters.
- Apply K-Means clustering.
- Visualize the resulting customer segments.
- Profile each cluster using mean RFM values.
- Recommend marketing actions for each segment.

## Dataset

The project uses the **Online Retail** dataset from the UCI Machine Learning Repository.

The dataset contains transactions from a UK-based registered non-store online retailer between 01 December 2010 and 09 December 2011.

Source: UCI Machine Learning Repository, Online Retail, Dataset ID 352.

The notebook retrieves the dataset through the `ucimlrepo` package rather than storing the large raw Excel file in this repository.

## Methodology

### 1. Data Inspection and Cleaning

The notebook:
- checks dataset shape and data types
- checks missing values
- removes records without CustomerID
- converts InvoiceDate to datetime
- removes cancelled/return transactions represented by non-positive quantities
- removes transactions with non-positive UnitPrice
- removes duplicate transaction rows

### 2. RFM Feature Engineering

**Recency:** number of days since the customer's most recent purchase.

**Frequency:** number of unique invoices/orders made by the customer.

**Monetary:** total amount spent by the customer.

An additional AveragePurchaseValue metric is calculated as Monetary divided by Frequency.

### 3. Standardization

RFM variables are log-transformed to reduce strong right skew and then standardized using `StandardScaler`.

### 4. K-Means Clustering

The Elbow Method is evaluated across multiple K values. A default K of 4 is used as a practical starting point and can be changed after reviewing the elbow curve.

### 5. Visualizations

The notebook includes:
- Recency vs Monetary scatter plot
- Frequency vs Monetary scatter plot
- customer count by segment
- cluster profile table

### 6. Customer Profiling

Each cluster is interpreted using average Recency, Frequency and Monetary values. Business-friendly labels are assigned from the observed RFM profile.

## Marketing Recommendations

| Customer profile | Suggested action |
|---|---|
| High-value / Loyal | VIP rewards, early access, premium offers and retention campaigns |
| Active Potential | Cross-sell, bundles and loyalty incentives |
| Regular Customers | Personalized promotions and repeat-purchase offers |
| At-Risk / Inactive | Win-back campaigns, reminders and targeted reactivation offers |

The notebook maps the actual clusters to these actions based on their calculated RFM characteristics.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn
- Jupyter Notebook
- UCI Machine Learning Repository

## Project Structure

```text
DataAnalytics-L1-CustomerSegmentation
│
├── Customer_Segmentation_RFM_KMeans.ipynb
├── README.md
├── requirements.txt
└── DATA_SOURCE.md
```

## How to Run

```bash
pip install -r requirements.txt
```

Then open:

```bash
jupyter notebook Customer_Segmentation_RFM_KMeans.ipynb
```

Run all cells from top to bottom.

The notebook retrieves the dataset through the UCI dataset interface at runtime and generates the RFM analysis, clustering visuals, cluster profiles and recommendations.

## Internship Requirement Coverage

- [x] Dataset inspection
- [x] Missing value and inconsistent data handling
- [x] Average purchase value and customer behaviour statistics
- [x] RFM feature selection
- [x] StandardScaler normalization
- [x] K-Means clustering
- [x] Elbow Method
- [x] Two cluster visualizations
- [x] Cluster profiling
- [x] Customer count bar chart
- [x] Segment-specific marketing recommendations

## Author

Devraj Parihar

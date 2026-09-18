# Retail Sales Data Analysis

## Project Overview

This project performs exploratory data analysis on a retail sales dataset using Python.

The analysis focuses on understanding sales performance, customer characteristics, product category revenue, and relationships between numerical variables.

The project was completed as part of the Oasis Infobyte Data Analytics Internship, Level 1, Task 1.

## Objectives

The main objectives of this project are,

- Inspect the structure and quality of the dataset.
- Identify and handle missing values.
- Calculate descriptive statistics.
- Analyze monthly and quarterly sales trends.
- Understand customer age and gender distribution.
- Analyze revenue across product categories.
- Examine relationships between numerical variables.
- Identify additional customer related insights.
- Provide actionable business recommendations based on the findings.

## Tools and Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Dataset

The analysis was performed using a retail sales dataset containing transaction level information.

The dataset includes information such as,

- Transaction ID
- Sale Date
- Sale Time
- Customer ID
- Gender
- Age
- Product Category
- Quantity
- Price per Unit
- Cost of Goods Sold
- Total Sale

The original dataset contains 2000 records and 11 columns.

## Data Cleaning

The dataset was inspected for missing values and duplicate records.

Three records containing missing values in important sales related columns were removed because they could not be reliably used for sales analysis.

Missing values in the age column were replaced using the median age.

No duplicate records were identified.

After cleaning, the dataset contained 1997 records with no remaining missing values.

## Analysis Performed

### Descriptive Statistics

Mean, median, mode, and standard deviation were calculated for the relevant numerical variables to understand the distribution and variation within the data.

### Monthly Sales Analysis

Sales were grouped by year and month to identify changes in revenue over time.

### Quarterly Sales Analysis

Sales were grouped by quarter to identify broader seasonal patterns in sales performance.

### Customer Age Analysis

Customer ages were analyzed using a distribution plot to understand the composition of the customer base.

### Gender Analysis

Total sales were compared across customer gender groups.

### Category Revenue Analysis

Revenue was analyzed across product categories to identify the categories contributing most to total sales.

The dataset does not contain a separate product name or product ID column, so the analysis focuses on product category revenue rather than individual products.

### Correlation Analysis

A correlation matrix and heatmap were created to examine relationships between numerical variables including age, quantity, price per unit, cogs, and total sale.

### Age Group Analysis

Customers were divided into age groups and their average transaction values were compared to identify differences in purchasing behaviour.

## Key Findings

The cleaned dataset contained 1997 transactions with total revenue of 911720.

The average transaction value was 456.54, while the median transaction value was 150.

Electronics generated the highest revenue among the product categories, with total sales of 313810.

The fourth quarter of 2022 recorded the highest quarterly sales, with revenue of 210030.

The under 20 age group recorded the highest average transaction value, at approximately 559.03.

## Business Recommendations

### 1. Focus on the Electronics Category

Electronics generated the highest revenue among the analyzed categories.

The business can maintain product availability in this category and consider targeted promotional campaigns to support continued sales.

### 2. Prepare for Stronger Q4 Demand

The fourth quarter recorded the highest sales in the dataset.

The business can plan inventory, staffing, and promotional activities ahead of this period to prepare for stronger demand.

### 3. Explore Younger Customer Segments

The under 20 age group recorded the highest average transaction value.

The business can test targeted offers, product bundles, and digital campaigns for younger customers while monitoring whether this pattern continues in future sales data.

## Conclusion

The exploratory analysis provided an overview of sales performance, customer characteristics, and category level revenue within the retail sales dataset.

The analysis demonstrates how data cleaning, statistical analysis, visualization, and interpretation can be combined to identify useful business insights.

The findings can support decisions related to inventory planning, seasonal promotions, customer segmentation, and category level sales strategies.

## Project Structure

```text
DataAnalytics-L1-Task1-RetailSalesEDA
│
├── Retail_Sales_EDA.ipynb
├── Data.csv
└── README.md

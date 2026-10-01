# Data Cleaning and Quality Analysis

## Project Overview

This project demonstrates a complete data-cleaning workflow on the Titanic passenger dataset.

The project was completed as part of the Oasis Infobyte Data Analytics Internship, Level 1, Task 3.

The focus is not on prediction. Instead, the project documents how a raw dataset is inspected, cleaned, standardized, checked for outliers, converted to appropriate data types, and exported as a reusable clean dataset.

## Objectives

- Produce a data quality report.
- Identify missing values, duplicate rows, data-type issues, and numeric range anomalies.
- Choose and document appropriate missing-data strategies.
- Remove duplicate records.
- Standardize inconsistent categorical formatting.
- Detect numeric outliers using the IQR method.
- Document whether outliers are capped, removed, or retained.
- Correct data types.
- Compare data quality before and after cleaning.
- Save the cleaned dataset to a new CSV file.

## Dataset

The project uses the Titanic dataset, one of the datasets suggested in the Oasis Infobyte task sheet for data-cleaning practice.

The dataset contains passenger information such as passenger class, sex, age, number of siblings/spouses aboard, parents/children aboard, fare, and embarkation port.

The notebook loads the dataset through the Seaborn dataset interface.

## Data Cleaning Workflow

### 1. Initial Data Quality Report

The notebook checks:

- row and column count
- null values by column
- duplicate rows
- data types
- unique values in categorical columns
- numeric minimum and maximum values

### 2. Missing Data

The cleaning strategy is documented in the notebook:

- Numeric variables such as Age are median-imputed.
- Fare is median-imputed.
- Embarked is mode-imputed.
- Cabin is converted to a simplified categorical indicator, `CabinKnown`, rather than filling individual cabin identifiers with fabricated values.

### 3. Duplicate Removal

Exact duplicate rows are identified and removed. The number removed is recorded for the before-versus-after report.

### 4. Standardization

Categorical fields are normalized so that values use consistent formatting.

For example:

- Sex values are standardized to `Male` and `Female`.
- Embarked values are stripped of unnecessary whitespace and converted to uppercase.
- Text columns are stripped of surrounding whitespace.

### 5. Outlier Detection

The IQR method is applied to numeric variables such as Age, Fare, SibSp and Parch.

The notebook records the number of observations outside the IQR bounds. Because extreme observations can contain useful information, the workflow caps selected numeric outliers at their IQR bounds instead of automatically deleting rows.

### 6. Data Type Correction

The notebook explicitly converts:

- Age to numeric
- Fare to numeric
- integer-count fields to nullable integer types where appropriate
- categorical variables to consistent string/category representations

## Before vs After

The notebook produces a summary containing:

- row count
- null count
- duplicate count
- dtype issues

for the dataset before and after cleaning.

## Output

The notebook exports:

`cleaned_titanic.csv`

This file is generated when the final notebook cell is executed.

## Tools

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

## Project Structure

```text
DataAnalytics-L1-DataCleaning
│
├── Data_Cleaning_Titanic.ipynb
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
jupyter notebook Data_Cleaning_Titanic.ipynb
```

Run all cells from top to bottom.

## Internship Requirement Coverage

- [x] Data quality report
- [x] Null-value handling with documented strategies
- [x] Duplicate identification and removal
- [x] Categorical standardization
- [x] IQR-based outlier detection and documented treatment
- [x] Data type correction
- [x] Before-versus-after quality summary
- [x] Cleaned CSV export

## Author

Devraj Parihar

# House Price Prediction with Linear Regression

## Project Overview

This project builds and evaluates a Linear Regression model for predicting residential house prices.

The project was completed as part of the Oasis Infobyte Data Analytics Internship, Level 2, Task 1.

The workflow covers exploratory data analysis, feature selection, missing-value handling, categorical encoding, correlation analysis, model training, regression metrics, residual analysis, coefficient interpretation, and a Ridge Regression comparison.

## Objectives

- Perform exploratory data analysis on house prices.
- Inspect missing values and descriptive statistics.
- Examine the target-price distribution.
- Discuss which features are useful predictors.
- Handle missing values.
- Encode categorical features using One-Hot Encoding.
- Analyze correlations with house price.
- Split data into training and testing sets using an 80/20 split.
- Train a scikit-learn Linear Regression model.
- Evaluate MSE, RMSE and R².
- Compare actual and predicted prices.
- Inspect residuals.
- Interpret regression coefficients.
- Compare Linear Regression with Ridge Regression.

## Dataset

The project uses the **Ames Housing** dataset.

The dataset contains residential property attributes such as living area, overall quality, year built, neighborhood, garage information, basement characteristics, and sale price.

The notebook loads the dataset from the OpenML repository using scikit-learn. The raw dataset is therefore not committed to this repository.

## Methodology

### 1. Exploratory Data Analysis

The notebook checks:

- dataset shape
- data types
- missing values
- descriptive statistics
- SalePrice distribution
- numeric relationships with SalePrice

### 2. Feature Selection

Potential predictors are selected from the available housing attributes.

Features such as overall quality, living area, garage capacity, year built and neighborhood are potentially informative because they describe property size, condition, age, location and facilities.

The model does not use the target variable as an input feature.

### 3. Missing Values

Numeric features are median-imputed.

Categorical features are filled with the most frequent category.

This treatment is implemented inside a scikit-learn preprocessing pipeline to prevent information leakage from the test set into training.

### 4. Categorical Encoding

Categorical variables are converted into numerical representations using One-Hot Encoding.

Unknown categories encountered during testing are ignored safely.

### 5. Correlation Analysis

A correlation heatmap is created for the numeric variables and SalePrice to identify linear relationships that may be useful for regression.

### 6. Linear Regression

The cleaned and encoded features are passed to `LinearRegression` after an 80/20 train-test split.

The model is evaluated with:

- Mean Squared Error
- Root Mean Squared Error
- R² score

### 7. Model Diagnostics

The notebook includes:

- actual vs predicted price scatter plot
- residual plot
- coefficient analysis

The residual plot is used to look for obvious systematic patterns.

### 8. Ridge Regression Bonus

Ridge Regression is trained using the same preprocessing pipeline.

Its metrics are compared with ordinary Linear Regression to demonstrate the effect of L2 regularisation.

## Output

The notebook generates:

- EDA tables and plots
- missing-value summary
- target distribution
- correlation heatmap
- Linear Regression metrics
- Ridge Regression metrics
- actual-vs-predicted plot
- residual plot
- positive and negative coefficient tables

## Project Structure

```text
DataAnalytics-L2-HousePriceRegression
│
├── House_Price_Linear_Regression.ipynb
├── README.md
├── requirements.txt
└── DATA_SOURCE.md
```

## How to Run

```bash
pip install -r requirements.txt
```

Then:

```bash
jupyter notebook House_Price_Linear_Regression.ipynb
```

Run the notebook from top to bottom.

The Ames Housing data is downloaded from OpenML when the notebook is executed.

## Internship Requirement Coverage

- [x] EDA: null check, descriptive statistics and target distribution
- [x] Feature selection discussion
- [x] Missing-value handling
- [x] One-Hot Encoding
- [x] Correlation heatmap
- [x] 80/20 train-test split
- [x] Linear Regression
- [x] MSE
- [x] RMSE
- [x] R²
- [x] Actual vs predicted scatter plot
- [x] Residual plot
- [x] Coefficient analysis
- [x] Ridge Regression comparison

## Author

Devraj Parihar

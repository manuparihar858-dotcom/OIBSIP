# Fraud Detection

## Project Overview

This project builds a machine learning pipeline for detecting fraudulent financial transactions in a heavily imbalanced credit-card transaction dataset.

It was completed as part of the Oasis Infobyte Data Analytics Internship, Level 2, Task 3.

The project focuses on the central challenge of fraud detection: fraudulent transactions are rare, so ordinary accuracy can give a misleading picture of model performance.

## Objectives

- Analyse the percentage of fraudulent transactions.
- Compare transaction amounts for fraud and non-fraud cases.
- Analyse transaction timing.
- Explain why accuracy is misleading for highly imbalanced fraud data.
- Use SMOTE to address class imbalance without leaking test-set information.
- Use a stratified train/test split.
- Train Logistic Regression and Random Forest models.
- Evaluate Precision, Recall, F1-score and ROC-AUC.
- Plot ROC curves.
- Analyse model coefficients and feature importance.
- Discuss the Recall versus Precision trade-off.
- Discuss how the pipeline could scale to very high transaction volumes.

## Dataset

The project uses the benchmark **Credit Card Fraud Detection** dataset containing anonymized European credit-card transactions.

The dataset contains 284,807 transactions, including 492 fraudulent transactions.

The raw dataset is not committed to this repository. It is expected to be downloaded separately from the Kaggle dataset referenced in `DATA_SOURCE.md`.

## Important Leakage Prevention

The workflow splits the data into training and testing sets **before** applying SMOTE.

SMOTE is therefore used only inside the training pipeline. The test set remains untouched and retains its original class distribution.

This is important because oversampling the full dataset before splitting can leak information from synthetic training examples into the test set and produce overly optimistic evaluation results.

## Models

### Logistic Regression

A linear baseline that produces fraud probabilities and interpretable feature coefficients.

### Random Forest

An ensemble tree model capable of capturing nonlinear relationships and interactions between features. It also provides feature importance estimates.

## Evaluation

Because the fraud class is extremely rare, the notebook focuses on:

- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion matrix
- ROC curve

Accuracy is shown only as supporting information and is explicitly not treated as the primary metric.

## Recall vs Precision

Higher recall means detecting more fraudulent transactions, reducing false negatives.

Higher precision means that a larger proportion of transactions flagged as fraud are actually fraudulent, reducing false positives.

The appropriate balance depends on the business cost of missed fraud versus customer friction and manual-review workload.

For many fraud-screening systems, recall is particularly important because missed fraudulent transactions can create direct financial loss. However, maximising recall without considering precision can generate excessive false alerts.

## Scalability

For a system processing approximately one million transactions per hour, a production design would need:

- streaming or distributed ingestion
- low-latency feature generation
- efficient model inference
- batch or incremental retraining
- monitoring for concept drift
- fraud feedback loops
- threshold tuning based on business costs
- horizontal scaling
- alert prioritisation and human review workflows

The notebook is a modelling exercise, not a production payment-processing system.

## Project Structure

```text
DataAnalytics-L2-FraudDetection
│
├── Fraud_Detection.ipynb
├── README.md
├── requirements.txt
└── DATA_SOURCE.md
```

## How to Run

Install dependencies:

```bash
pip install -r requirements.txt
```

Download the Credit Card Fraud Detection dataset and place `creditcard.csv` in the same directory as the notebook.

Then run:

```bash
jupyter notebook Fraud_Detection.ipynb
```

## Internship Requirement Coverage

- [x] Fraud class percentage
- [x] Fraud vs non-fraud amount EDA
- [x] Time-of-day analysis
- [x] Accuracy limitation discussion
- [x] SMOTE imbalance handling
- [x] Stratified train/test split
- [x] Logistic Regression
- [x] Random Forest
- [x] Precision
- [x] Recall
- [x] F1-score
- [x] AUC-ROC
- [x] Recall vs Precision discussion
- [x] Coefficient / feature importance analysis
- [x] Scalability discussion

## Author

Devraj Parihar

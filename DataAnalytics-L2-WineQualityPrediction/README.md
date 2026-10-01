# Wine Quality Prediction

## Project Overview

This project trains and compares three classification models to predict wine quality from physicochemical measurements.

It was completed as part of the Oasis Infobyte Data Analytics Internship, Level 2, Task 2.

The models used are:

- Random Forest
- Stochastic Gradient Descent (SGD)
- Support Vector Classifier (SVC)

The original Wine Quality score is transformed into three classes so the classification problem is easier to interpret:

- Low Quality
- Medium Quality
- High Quality

## Objectives

- Inspect the Wine Quality dataset.
- Analyse the distribution of quality scores.
- Explore the chemical features.
- Study correlations between variables.
- Discuss class imbalance.
- Engineer a three-class quality target.
- Preserve class ratios during train/test splitting.
- Train Random Forest, SGD and SVC classifiers.
- Evaluate accuracy, classification report and confusion matrix.
- Analyse Random Forest feature importance.
- Compare the three models side by side.
- Discuss model suitability for deployment.

## Dataset

The project uses the **UCI Wine Quality — Red Wine** dataset.

The dataset contains physicochemical measurements such as acidity, residual sugar, chlorides, sulphates, density, pH and alcohol, together with a quality score.

The notebook downloads the red wine CSV from the UCI Machine Learning Repository.

## Target Engineering

The original quality score is converted into three interpretable classes:

- **Low:** quality <= 5
- **Medium:** quality == 6
- **High:** quality >= 7

This creates a multiclass classification problem while retaining a meaningful relationship with the original quality rating.

The notebook prints the resulting class distribution so class imbalance can be assessed before modelling.

## Models

### Random Forest

An ensemble of decision trees that can capture nonlinear relationships and provides feature importance estimates.

### SGD Classifier

A linear classifier trained using stochastic gradient descent. It is computationally efficient and useful as a linear baseline.

### Support Vector Classifier

A margin-based classifier capable of modelling nonlinear boundaries when an appropriate kernel is used.

All models use a preprocessing pipeline with feature standardisation where appropriate.

## Evaluation

Each model is evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Classification report
- Confusion matrix

A final comparison table summarises the three models.

## Project Structure

```text
DataAnalytics-L2-WineQualityPrediction
│
├── Wine_Quality_Prediction.ipynb
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
jupyter notebook Wine_Quality_Prediction.ipynb
```

Run all cells from top to bottom.

## Internship Requirement Coverage

- [x] Dataset structure and class distribution
- [x] Chemical feature distribution plots
- [x] Correlation heatmap
- [x] Class imbalance discussion
- [x] Three-class quality engineering
- [x] Stratified train/test split
- [x] Random Forest
- [x] SGD Classifier
- [x] SVC
- [x] Accuracy
- [x] Classification reports
- [x] Confusion matrices
- [x] Random Forest feature importance
- [x] Side-by-side model comparison
- [x] Deployment-oriented conclusion

## Author

Devraj Parihar

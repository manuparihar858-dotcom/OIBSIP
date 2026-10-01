# Sentiment Analysis

## Project Overview

This project builds a machine-learning pipeline to classify text into three sentiment classes: **negative, neutral, and positive**.

The project was completed as part of the Oasis Infobyte Data Analytics Internship, Level 1, Task 4.

The workflow covers text preprocessing, TF-IDF feature extraction, two machine-learning classifiers, evaluation, sentiment visualisation, WordClouds, and error analysis.

## Dataset

The notebook uses the **TweetEval sentiment** dataset, a public benchmark containing three sentiment classes:

- `negative`
- `neutral`
- `positive`

The dataset is loaded through the Hugging Face `datasets` library at runtime, so raw dataset files do not need to be committed to GitHub.

Dataset source: TweetEval sentiment benchmark.

## Objectives

- Inspect the class distribution.
- Build a text preprocessing pipeline.
- Explain and use TF-IDF Vectorization.
- Split the data into 80% training and 20% testing data.
- Train at least two classifiers.
- Compare accuracy, precision, recall and F1-score.
- Generate confusion matrices.
- Visualise sentiment distribution.
- Generate a WordCloud for each sentiment class.
- Display five misclassified examples.
- Discuss possible causes of classification errors.
- Conclude with a real-world application.

## Methodology

### 1. Text Preprocessing

The notebook applies:

- lowercasing
- URL removal
- punctuation removal
- whitespace normalization
- tokenisation through the vectorizer
- English stopword removal

### 2. TF-IDF

TF-IDF, or Term Frequency-Inverse Document Frequency, converts text into numerical features.

It gives greater importance to words that are frequent in a particular document but relatively uncommon across the complete collection of documents.

### 3. Models

Two classifiers are trained:

1. Multinomial Naive Bayes
2. Logistic Regression

Both models use the same TF-IDF representation and the same 80/20 stratified train-test split.

### 4. Evaluation

Each model is evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix

Macro-averaged precision, recall and F1 are reported so that the three sentiment classes are considered equally in the comparison.

### 5. Error Analysis

The notebook identifies five test examples where the selected comparison model predicted the wrong sentiment. The examples are displayed with:

- original text
- actual label
- predicted label

The discussion considers common sources of errors such as sarcasm, ambiguous wording, context dependence, negation and informal language.

## Real-World Applications

A three-class sentiment classifier can support:

- customer feedback monitoring
- social-media opinion analysis
- product-review analysis
- brand monitoring
- customer-support triage

## Project Structure

```text
DataAnalytics-L1-SentimentAnalysis
│
├── Sentiment_Analysis_TFIDF.ipynb
├── README.md
├── requirements.txt
└── DATA_SOURCE.md
```

## How to Run

Install the dependencies:

```bash
pip install -r requirements.txt
```

Open:

```bash
jupyter notebook Sentiment_Analysis_TFIDF.ipynb
```

Run all cells from top to bottom.

The notebook downloads the dataset at runtime and generates all metrics and visualisations.

## Internship Requirement Coverage

- [x] Dataset and class distribution
- [x] Lowercase text preprocessing
- [x] Punctuation removal
- [x] Stopword removal
- [x] Tokenisation through TF-IDF vectorization
- [x] TF-IDF explanation
- [x] 80/20 train-test split
- [x] Naive Bayes classifier
- [x] Logistic Regression classifier
- [x] Accuracy, precision, recall and F1-score
- [x] Confusion matrices
- [x] Sentiment distribution bar chart
- [x] WordCloud for each sentiment class
- [x] Five misclassified examples
- [x] Error analysis
- [x] Conclusion and real-world application

## Author

Devraj Parihar

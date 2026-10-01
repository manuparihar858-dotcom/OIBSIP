# Unveiling the Android App Market — Google Play Store Analysis

## Project Overview

This project performs a comprehensive analysis of the Google Play Store ecosystem using two separate datasets:

1. Google Play Store Apps
2. Google Play Store User Reviews

The project was completed as part of the Oasis Infobyte Data Analytics Internship, Level 2, Task 4.

The workflow covers real-world data cleaning, category analysis, ratings, size and installs relationships, pricing, revenue estimation, and sentiment analysis of user reviews.

## Objectives

- Clean the Play Store apps and user-review datasets.
- Fix inconsistent data types such as `Installs` and `Price`.
- Handle missing values and duplicates.
- Analyse app category saturation.
- Analyse ratings overall and by category.
- Study app size versus installs.
- Compare free and paid apps.
- Analyse paid-app prices.
- Estimate potential revenue by category.
- Classify user reviews as positive, negative or neutral.
- Analyse sentiment by app category.
- Create an interactive Plotly visualisation.
- Produce three data-driven insights for a developer planning a new app.

## Datasets

The notebook expects two CSV files:

```text
googleplaystore.csv
googleplaystore_user_reviews.csv
```

These are the commonly distributed Google Play Store Apps and Google Play Store User Reviews datasets.

See `DATA_SOURCE.md` for source and filename information.

## Data Cleaning

The apps dataset includes fields stored as strings even when they represent numeric quantities.

The notebook converts:

- `Installs`: values such as `10,000+` → numeric installs
- `Price`: values such as `$4.99` → numeric price
- `Reviews`: numeric review count
- `Rating`: numeric rating
- `Size`: converted to approximate MB where possible

Nulls and duplicate app records are handled explicitly.

The user-review dataset is cleaned separately before sentiment analysis.

## Category Analysis

The project analyses the number of apps in each category as a measure of ecosystem saturation.

A category with many apps is described as more saturated in terms of app count. This does not by itself measure profitability or competition quality.

## Ratings Analysis

The notebook includes:

- rating distribution
- average rating by category
- category-level rating comparison

Only valid numeric ratings are used in rating calculations.

## Size and Installs

A scatter plot compares approximate app size in MB with install count.

Because app installs are highly skewed, the notebook also calculates Pearson correlation using available numeric values and discusses the limitations of interpreting simple correlation as causation.

## Pricing and Revenue

The notebook compares:

- free vs paid app counts
- price distribution among paid apps
- estimated gross revenue by category

### Revenue assumption

Revenue is estimated using:

```text
Estimated Revenue = Price × Installs
```

This is a simple gross-revenue proxy, not actual developer revenue.

It does not account for:

- Google Play's service fee
- taxes
- refunds
- discounts
- regional pricing
- subscriptions
- in-app purchases
- conversion differences

Therefore, category revenue values should be interpreted as relative estimates rather than financial statements.

## Sentiment Analysis

User reviews are classified using VADER sentiment analysis.

The compound score is mapped to:

- Positive
- Neutral
- Negative

Sentiment is then joined with app metadata so category-level sentiment can be analysed.

## Interactive Visualisation

The notebook includes a Plotly interactive chart for category-level app counts and average ratings.

## Three Developer Insights

The conclusion is generated from the actual notebook outputs rather than hard-coded claims.

The notebook asks the analyst to identify:

1. A category or market structure signal.
2. A rating or sentiment signal.
3. A monetisation or installs signal.

These are then translated into practical considerations for a developer planning a new app.

## Project Structure

```text
DataAnalytics-L2-GooglePlayStoreAnalysis
│
├── Google_Play_Store_Analysis.ipynb
├── README.md
├── requirements.txt
└── DATA_SOURCE.md
```

## How to Run

Install dependencies:

```bash
pip install -r requirements.txt
```

Place both CSV files beside the notebook:

```text
googleplaystore.csv
googleplaystore_user_reviews.csv
```

Then run:

```bash
jupyter notebook Google_Play_Store_Analysis.ipynb
```

## Internship Requirement Coverage

- [x] Apps and reviews datasets loaded separately
- [x] Incorrect data types fixed
- [x] Nulls handled
- [x] Duplicates removed
- [x] Category distribution
- [x] Category saturation analysis
- [x] Rating distribution
- [x] Average rating by category
- [x] Size vs installs scatter
- [x] Size/install correlation
- [x] Free vs paid analysis
- [x] Paid price distribution
- [x] Revenue estimate by category
- [x] VADER sentiment analysis
- [x] Sentiment by category
- [x] Plotly interactive visualisation
- [x] Three developer-oriented insights

## Author

Devraj Parihar

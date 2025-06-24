
# Trader Performance & Market Sentiment Analysis

## Overview

This project explores the relationship between **Bitcoin market sentiment** (Fear/Greed) and **trader performance**, using historical trading data from Hyperliquid. The goal is to identify patterns that connect sentiment with trade outcomes (profit/loss) and build a classification model to predict sentiment from trader behavior.

---

## Datasets Used

### 1. Historical Trader Data (Hyperliquid)
- Contains detailed trading records.
- **Columns include**: 'Account', 'Coin', 'Execution Price', 'Size Tokens', 'Size USD', 'Side', 'Timestamp IST', 'Start Position', 'Direction', 'Closed PnL', 'Fee', etc.
- **Link for Dataset**: 'https://drive.google.com/file/d/1TOT1pH4Q8QbyzPMVgK-z7WXmcLGZT-7a/view?usp=drive_link'

### 2. Bitcoin Market Sentiment (Fear & Greed Index)
- Daily sentiment classification as either **Fear** or **Greed**.
- **Columns include**: 'date', 'value', 'classification'
- **Link for Dataset**: 'https://drive.google.com/file/d/1oflwMNio13uwOlHqs_YIUSQkR9Ti0JF5/view?usp=drive_link'

---

## Objective

- Merge market sentiment data with trader activity.
- Analyze whether market **sentiment affects trader profits/losses**.
- Build a machine learning model to **classify sentiment based on trade behavior**.

---

## Key Steps

### 1. Data Preprocessing
- Converted 'Timestamp IST' to proper 'datetime' format.
- Extracted date to align with sentiment data.
- Merged both datasets on 'date'.

### 2. Exploratory Data Analysis (EDA)
- Analyzed how 'Closed PnL' varied across **Fear** and **Greed** days.
- Plotted distributions of profit/loss vs. sentiment.
- Visualized trade size, direction, and volume impact.

### 3. Feature Engineering
- Encoded categorical features (e.g., sentiment classification).
- Selected key features such as: 'Execution Price', 'Size USD', 'Direction', 'Fee', etc.

### 4. Model Building: XGBoost Classifier
- Applied 'XGBoostClassifier' for classifying market sentiment.
- Used 'RandomizedSearchCV' for hyperparameter tuning.
- Evaluated using **confusion matrix** and **feature importance**.

---

## Results

- Achieved good accuracy in classifying Fear/Greed sentiment based on trader behavior.
- Identified that **Closed PnL**, 'Side', and 'Fee' had strong influence on sentiment predictions.
- Feature importance and confusion matrix supported model reliability.

---

## Insights

- **Greed** periods generally see **higher profits** and **larger trade sizes**.
- **Fear** periods show more conservative trading behavior and smaller profits or losses.
- Sentiment can **influence trader decisions** and potentially be used to **optimize strategy**.

---

## Tech Stack

- Python, Pandas, NumPy, Matplotlib, Seaborn
- Scikit-learn, XGBoost
- Google Colab (GPU-backed runtime)

---

## Files Included

- 'trader_data.csv' – Historical trade data (raw)
- 'sentiment_data.csv' – Daily market sentiment (raw)
- 'trader-behavior-insights.ipynb' – Main notebook with code and analysis
- 'README.md' – Project documentation

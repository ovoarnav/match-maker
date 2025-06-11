# 💔 Predicting Non-Matches in Speed Dating with Machine Learning

## Overview
Everyone’s been on a bad date — the kind where you know it’s not going anywhere. This project uses machine learning to predict when **two people are unlikely to go on a second date**, based on real speed dating data.

## Why This Matters
Instead of matching for compatibility, we’re flipping the problem — we want to know when people **won’t** click. This insight is useful for dating platforms, social experiments, or just anyone curious about human behavior.

## Dataset
- **Source:** [Kaggle Speed Dating Dataset](https://www.kaggle.com/datasets/annavictoria/speed-dating-experiment)
- **Size:** 8,293 rows
- **Target:** `match` (1 = mutual interest, 0 = no match)
- **Class imbalance:** ~84% class 0 (non-match), 16% class 1 (match)

## Objective
Our primary goal was to **maximize recall on class 0** (non-matches). Missing a possible match is okay — but **incorrectly assuming someone will match when they won’t** is what we want to avoid.

## Best Model: 🔥 Logistic Regression (Tuned)
| Metric     | Class 0 Value |
|------------|----------------|
| **Recall** | **89%**        |
| **Precision** | 91%        |
| **F1 Score** | 90%         |
| **ROC AUC** | 0.821        |
| **Accuracy** | 84%         |

> Class 0 (non-matches) was correctly captured 89% of the time — making this model extremely effective at filtering out poor matches.

## Top Features (by Importance & Significance)
- `like`
- `funny_o`
- `shared_interests_o`
- `attractive_partner`
- `guess_prob_liked`

These were selected using **Cohen’s d**, **p-values**, and Random Forest feature importance.

## Project Structure
Data_wrangling: https://github.com/ovoarnav/match-maker/blob/main/data_wrangling.ipynb
EDA: https://github.com/ovoarnav/match-maker/blob/main/eda.ipynb
Modeling: https://github.com/ovoarnav/match-maker/blob/main/modelling.ipynb

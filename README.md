# Adult Income Prediction

A Machine Learning project that predicts whether an individual's annual income exceeds **$50,000** based on demographic and employment-related attributes from the UCI Adult Income Dataset.

This project was developed as part of the **ML Training Program - Final Assignment (Assignment 03)** focusing on model development, hyperparameter tuning, model persistence, and production-ready inference. :contentReference[oaicite:0]{index=0}

---

## Project Overview

The objective of this project is to build a robust classification model capable of predicting income categories:

- **<=50K**
- **>50K**

The project includes:

- Data cleaning and preprocessing
- Feature engineering
- Exploratory Data Analysis (EDA)
- Baseline model comparison
- Hyperparameter tuning using `RandomizedSearchCV`
- Model persistence using `joblib`
- Production-ready inference script

---

## Dataset

Dataset: **UCI Adult Income Dataset**

The dataset contains demographic and employment information collected from the 1994 US Census and is widely used for binary classification tasks. :contentReference[oaicite:1]{index=1}

Features include:

- Age
- Education
- Occupation
- Marital Status
- Hours per Week
- Capital Gain/Loss
- Native Country
- Relationship Status
- Race
- Gender

Target Variable:

```text
income
0 → <=50K
1 → >50K

# House Price Prediction using Machine Learning

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![Pandas](https://img.shields.io/badge/Pandas-2.x-150458?logo=pandas)
![NumPy](https://img.shields.io/badge/NumPy-2.x-013243?logo=numpy)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.7-F7931E?logo=scikitlearn)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-11557C)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-4C72B0)
![License](https://img.shields.io/badge/License-MIT-green)

---

## Project Overview

This project presents an end-to-end Machine Learning pipeline for predicting house prices using supervised regression techniques.

The project covers the complete workflow of a typical regression problem, including:

- Data Cleaning
- Exploratory Data Analysis (EDA)
- Feature Engineering
- Manual Target Encoding with Smoothing
- Log Transformation
- Feature Scaling
- Model Training
- Hyperparameter Tuning
- Model Evaluation
- Model Persistence

Four regression algorithms were implemented and compared to identify the most suitable model for predicting house prices.

---

## Objectives

The primary goals of this project are:

- Build a complete regression pipeline from raw data to prediction.
- Explore and analyze the dataset through EDA.
- Apply feature engineering to improve predictive performance.
- Compare multiple regression algorithms.
- Optimize the best model using GridSearchCV.
- Save the trained model together with preprocessing objects for future inference.

---

## Dataset

**Source**

Kaggle – House Price Dataset

### Dataset Information

| Property | Value |
|-----------|------:|
| Samples | 3,479 |
| Features | 8 |
| Target | Price (USD) |

### Features Used

| Feature | Description |
|----------|-------------|
| Area | House area (square meters) |
| Room | Number of rooms |
| Parking | Parking availability |
| Address | District (Target Encoded) |

---

## Target Variable

The original **Price (USD)** distribution was highly right-skewed.

To reduce skewness and improve model performance, a logarithmic transformation was applied before training.

---

## Project Structure

```text
House-Price-Prediction-Regression/

├── data
│   └── housePrice.csv
│
├── images
│   ├── heatmap.png
│   ├── house_price_distribution.png
│   ├── feature_importance.png
│   ├── model_comparison.png
│   ├── actual_vs_predicted.png
│   └── residual_plot.png
│
├── models
│   ├── house_price_model.pkl
│   ├── scaler.pkl
│   └── smoothing_map.pkl
│
├── notebooks
│   └── House_Price_Regression.ipynb
│
├── README.md
├── requirements.txt
└── .gitignore
```

---

## Machine Learning Workflow

```text
Raw Dataset
      │
      ▼
Data Cleaning
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Feature Engineering
      │
      ▼
Log Transformation
      │
      ▼
Train / Test Split
      │
      ▼
Manual Target Encoding
      │
      ▼
StandardScaler
      │
      ▼
Model Training
      │
      ▼
Hyperparameter Tuning
      │
      ▼
Model Evaluation
      │
      ▼
Model Persistence
```

This workflow minimizes data leakage by ensuring preprocessing is consistently applied before model training.

---

## Key Features

- End-to-end Machine Learning workflow
- Comprehensive Exploratory Data Analysis (EDA)
- Data Cleaning and preprocessing
- Manual implementation of Target Encoding with smoothing
- Log transformation of the target variable
- Feature scaling using StandardScaler
- Comparison of four regression models
- Hyperparameter tuning using GridSearchCV
- Feature importance analysis
- Residual analysis
- Model persistence using Joblib
- Prediction-ready trained model
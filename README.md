````markdown

\\# House Price Prediction using Machine Learning



!\\\[Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)

!\\\[Pandas](https://img.shields.io/badge/Pandas-2.x-150458?logo=pandas)

!\\\[NumPy](https://img.shields.io/badge/NumPy-2.x-013243?logo=numpy)

!\\\[Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.7-F7931E?logo=scikitlearn)

!\\\[Matplotlib](https://img.shields.io/badge/Matplotlib-3.x-11557C)

!\\\[Seaborn](https://img.shields.io/badge/Seaborn-0.13-4C72B0)

!\\\[License](https://img.shields.io/badge/License-MIT-green)



\\---



\\# Project Overview



This project presents an end-to-end machine learning pipeline for predicting house prices using supervised regression techniques.



The project covers the complete machine learning workflow, including data preprocessing, exploratory data analysis, feature engineering, model development, hyperparameter optimization, model evaluation, and model persistence.



Several regression algorithms were trained and compared to identify the most effective approach for predicting house prices.



\\---



\\# Objectives



The primary objectives of this project are:



\\- Build an end-to-end regression pipeline for house price prediction.

\\- Perform exploratory data analysis to better understand the dataset.

\\- Apply feature engineering techniques to improve predictive performance.

\\- Compare the performance of multiple regression algorithms.

\\- Optimize the best-performing model using GridSearchCV.

\\- Save the trained model together with all required preprocessing components for future inference.



\\---



\\# Dataset



\\### Source



Kaggle – House Price Dataset



\\### Dataset Information



| Property | Value |

|-----------|-------|

| Samples | 3,479 |

| Features | 8 |

| Target Variable | Price (USD) |



\\### Features Used for Training



| Feature | Description |

|----------|-------------|

| Area | House area (square meters) |

| Room | Number of rooms |

| Parking | Parking availability |

| Address | District (Target Encoded) |



\\---



\\# Target Variable



The target variable (\\\*\\\*Price (USD)\\\*\\\*) exhibited a highly right-skewed distribution.



To reduce skewness and improve model learning, a logarithmic transformation was applied before training the regression models.



\\---



\\# Project Structure



```text

House-Price-Prediction-Regression/

│

├── data/

│   └── housePrice.csv

│

├── notebooks/

│   └── House\\\_Price\\\_Regression.ipynb

│

├── models/

│   ├── house\\\_price\\\_model.pkl

│   ├── scaler.pkl

│   └── smoothing\\\_map.pkl

│

├── images/

│   ├── heatmap.png

│   ├── house\\\_price\\\_distribution.png

│   ├── feature\\\_importance.png

│   ├── model\\\_comparison.png

│   ├── actual\\\_vs\\\_predicted.png

│   └── residual\\\_plot.png

│

├── requirements.txt

├── README.md

└── .gitignore

````



\---



\# Machine Learning Workflow



```text

Raw Dataset

\&#x20;     │

\&#x20;     ▼

Data Cleaning

\&#x20;     │

\&#x20;     ▼

Exploratory Data Analysis

\&#x20;     │

\&#x20;     ▼

Feature Engineering

\&#x20;     │

\&#x20;     ▼

Log Transformation

\&#x20;     │

\&#x20;     ▼

Train / Test Split

\&#x20;     │

\&#x20;     ▼

Manual Target Encoding

\&#x20;     │

\&#x20;     ▼

Standard Scaling

\&#x20;     │

\&#x20;     ▼

Model Training

\&#x20;     │

\&#x20;     ▼

Hyperparameter Tuning

\&#x20;     │

\&#x20;     ▼

Model Evaluation

\&#x20;     │

\&#x20;     ▼

Model Persistence

```



This workflow ensures that preprocessing is consistently applied before model training while minimizing the risk of data leakage.



\---



\# Key Features



\* End-to-end machine learning workflow

\* Comprehensive Exploratory Data Analysis (EDA)

\* Data cleaning and preprocessing

\* Manual implementation of Target Encoding with smoothing

\* Log transformation of the target variable

\* Feature scaling using StandardScaler

\* Comparison of multiple regression algorithms

\* Hyperparameter tuning using GridSearchCV

\* Feature importance analysis

\* Residual error analysis

\* Model persistence using Joblib

\* Prediction-ready trained model



```

```

```markdown

\\# Exploratory Data Analysis (EDA)



A comprehensive exploratory data analysis was performed to better understand the dataset before model development.



The analysis included:



\\- Distribution analysis of numerical variables

\\- Correlation analysis between features

\\- Missing value inspection

\\- Duplicate record detection

\\- Outlier visualization

\\- Target variable distribution analysis



The insights obtained during EDA guided the preprocessing and feature engineering steps used throughout the project.



\\---



\\## House Price Distribution



The original target variable (\\\*\\\*Price (USD)\\\*\\\*) exhibited a highly right-skewed distribution.



To reduce skewness and stabilize the variance, a logarithmic transformation was applied before model training.



<p align="center">

\&#x20;   <img src="images/house\\\_price\\\_distribution.png" width="650">

</p>



\\---



\\## Correlation Analysis



A Pearson correlation heatmap was generated to investigate relationships between numerical variables.



This analysis helped identify the most influential features affecting house prices and detect potential multicollinearity.



<p align="center">

\&#x20;   <img src="images/heatmap.png" width="650">

</p>



\\---



\\# Data Cleaning



The dataset was cleaned before model development.



The following preprocessing steps were performed:



\\- Checked for missing values

\\- Removed duplicate records

\\- Verified data consistency

\\- Converted Boolean variables into numerical format

\\- Prepared categorical variables for feature engineering



These steps ensured that the dataset was suitable for machine learning algorithms.



\\---



\\# Feature Engineering



Feature engineering played an important role in improving model performance.



The following techniques were applied:



\\## Manual Target Encoding



The \\\*\\\*Address\\\*\\\* feature contains categorical district names.



Instead of applying One-Hot Encoding, a custom Target Encoding approach was implemented manually.



To reduce overfitting, smoothing was incorporated into the encoding process.



The generated encoding dictionary was saved as:



\\- `smoothing\\\_map.pkl`



This allows new input data to be encoded consistently during inference.



\\---



\\## Log Transformation



The target variable (\\\*\\\*Price (USD)\\\*\\\*) was transformed using the natural logarithm.



Benefits of this transformation include:



\\- Reduced skewness

\\- Improved numerical stability

\\- Better regression performance

\\- Lower influence of extremely expensive houses



\\---



\\## Feature Scaling



All numerical features were standardized using \\\*\\\*StandardScaler\\\*\\\* before model training.



The fitted scaler was saved as:



\\- `scaler.pkl`



This ensures that future input data undergoes the exact same preprocessing used during training.



\\---



\\# Machine Learning Models



Four regression algorithms were implemented and evaluated.



| Model | Purpose |

|---------|----------|

| Linear Regression | Baseline model |

| Polynomial Regression | Capture nonlinear relationships |

| Random Forest Regressor | Ensemble learning |

| Gradient Boosting Regressor | Boosted ensemble learning |



Additionally, a simple Linear Regression model was developed during the exploratory stage to visualize the relationship between house area and price.



\\---



\\# Hyperparameter Tuning



To improve predictive performance, \\\*\\\*GridSearchCV\\\*\\\* was applied to optimize the Random Forest model.



Several hyperparameter combinations were evaluated using cross-validation.



The optimized model was then used for final evaluation.



\\---



\\# Model Evaluation



Model performance was evaluated using the following regression metrics:



\\- Mean Absolute Error (MAE)

\\- Mean Squared Error (MSE)

\\- Coefficient of Determination (R²)



The comparison demonstrates the performance differences between linear models and ensemble learning methods.



<p align="center">

\&#x20;   <img src="images/model\\\_comparison.png" width="700">

</p>



Both \\\*\\\*Random Forest\\\*\\\* and \\\*\\\*Gradient Boosting\\\*\\\* achieved very similar performance on the test dataset, significantly outperforming the linear regression models.



\\---



\\# Feature Importance



Feature importance analysis was performed using the best tree-based model.



This analysis provides insight into how much each feature contributes to the prediction process.



<p align="center">

\&#x20;   <img src="images/feature\\\_importance.png" width="700">

</p>



\\---



\\# Prediction Analysis



The predicted house prices were compared against the actual prices to evaluate the model's predictive capability.



<p align="center">

\&#x20;   <img src="images/actual\\\_vs\\\_predicted.png" width="650">

</p>



A well-performing regression model should produce predictions close to the diagonal line.



\\---



\\# Residual Analysis



Residual analysis was performed to assess prediction errors.



<p align="center">

\&#x20;   <img src="images/residual\\\_plot.png" width="650">

</p>



Randomly distributed residuals around zero indicate that the model captures the underlying relationships effectively without obvious systematic bias.

```

\---



\# Model Performance Summary



The performance of all regression models is summarized below.



| Model | MAE ↓ | MSE ↓ | Test R² ↑ | Train R² |

|--------|-------:|-------:|-----------:|----------:|

| Linear Regression | 0.2841 | 0.1686 | 0.8618 | 0.8336 |

| Polynomial Regression | 0.2448 | 0.1360 | 0.8885 | 0.8651 |

| \*\*Random Forest\*\* | \*\*0.2285\*\* | \*\*0.1229\*\* | \*\*0.8993\*\* | \*\*0.9709\*\* |

| Gradient Boosting | \*\*0.2285\*\* | \*\*0.1229\*\* | \*\*0.8993\*\* | \*\*0.9114\*\* |



The ensemble learning models (Random Forest and Gradient Boosting) significantly outperformed the linear regression models across all evaluation metrics.



\---



\# Key Findings



The experiments conducted in this project led to several important observations:



\- Applying a logarithmic transformation to the target variable reduced skewness and improved regression performance.

\- Manual Target Encoding effectively transformed the high-cardinality \*\*Address\*\* feature into a meaningful numerical representation while reducing overfitting through smoothing.

\- Ensemble learning algorithms achieved noticeably better predictive performance than linear models, indicating the presence of nonlinear relationships within the dataset.

\- Random Forest and Gradient Boosting produced nearly identical performance on the test dataset, demonstrating strong generalization capability.

\- Although Random Forest achieved a higher training R² score than Gradient Boosting, both models obtained the same predictive accuracy on unseen data. This suggests that Gradient Boosting generalized slightly more conservatively, while Random Forest captured more complex patterns in the training set.

\- Feature importance analysis showed that house address is the most influential predictor of house prices, with the remaining features contributing to different degrees.



Based on the overall evaluation, the \*\*Random Forest Regressor\*\* was selected as the final model for deployment after hyperparameter optimization using GridSearchCV.



\---


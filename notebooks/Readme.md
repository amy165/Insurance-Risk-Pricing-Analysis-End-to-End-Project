# Notebooks Overview

This folder contains the Python notebooks used throughout the analytical workflow of the project.

The notebooks cover:
- Data cleaning and exploratory analysis
- Machine Learning modeling
- Historical pricing simulations
- Inflation-adjusted portfolio analysis

### 01_eda_cleaning.ipynb

Main tasks:
- Data cleaning
- Missing value handling
- Exposure normalization
- Inflation adjustment preparation
- Exploratory portfolio analysis

Key analytical decisions:
- Policies with `policy_duration = 0` were excluded from pricing simulations because exposure normalization requires valid duration values.
- Inflation adjustment factors were merged into the portfolio data to express monetary values in constant 2017 ETB.
- Claim frequency and severity analyses were normalized using annualized exposure.

### 02_modeling.ipynb

Main tasks:
- Feature engineering
- Claim probability classification
- Model evaluation
- Threshold optimization

Models evaluated:
- XGBoost
- Random Forest
- Logistic Regression

Evaluation metrics:
- ROC-AUC
- PR-AUC
- Precision
- Recall
- Confusion Matrix

### 03_inflation.ipynb

Main tasks:
- Inflation data preparation
- Cumulative inflation factor calculation
- Construction of inflation normalization factors relative to the 2017 base year

The resulting inflation factors were later integrated into Power BI and pricing simulation workflows to normalize monetary values into constant 2017 ETB.

### 04_insurance_pricing_simulation.ipynb

Main tasks:
- Inflation-adjusted pricing analysis
- Historical expected loss calculation
- Previous-year repricing simulations
- Multi-year historical repricing simulations
- Promotional policy scenario analysis

Key analytical decisions:
- Simulated pricing only increased premiums when historical expected loss exceeded observed premium levels.
- Previous-year repricing used only historical information available prior to the evaluated year.
- Multi-year repricing used cumulative historical claim experience from all previous years.
- Promotional policies (`premium = 0`) were analyzed both as fully repriced and preserved promotional scenarios.

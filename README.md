
# 🚗 Insurance Risk & Pricing Analysis – End-to-End Project

An end-to-end insurance analytics project exploring portfolio performance, pricing adequacy, claim prediction, inflation-adjusted diagnostics, and historical risk-based repricing simulations using Power BI, Python, and Machine Learning.

# Project Overview

This project started as a descriptive insurance portfolio analysis and gradually evolved into a multi-stage analytical case study involving:

- Portfolio performance analysis
- Risk & pricing diagnostics
- Claim probability prediction
- Inflation-adjusted portfolio analysis
- Historical pricing strategy simulations

The project follows an iterative analytical workflow where each stage generated new business questions and deeper investigations.

---

# Business Problem

The insurance portfolio showed persistent underwriting losses across several years.

This project aimed to investigate:

- Whether premiums were aligned with observed risk
- Which vehicle categories were significantly underpriced
- How inflation distorted historical pricing interpretation
- Whether alternative pricing strategies could improve portfolio sustainability
- Whether claim probability could be predicted using policy characteristics

---

# Key Business Findings

- The insurance portfolio consistently operated at extremely high loss ratios, exceeding 250% in some periods.

- Several vehicle categories, particularly Bus, Truck, Pick-Up, and Trailers, showed significant underpricing relative to observed risk costs.

- Inflation-adjusted analyses provided a more consistent view of historical portfolio performance using constant-value monetary comparisons.

- Premium growth did not keep pace with inflation-adjusted claim costs over time.

- Machine Learning models identified vehicle type, exposure-related variables, and insured value groups as major drivers of claim probability.

- Historical risk-based repricing simulations substantially improved underwriting sustainability.

- Simulated loss ratios decreased from approximately 269% to below 90% under some historical repricing strategies.

- Multi-year historical repricing produced more stable pricing adjustments than single-year reactive repricing approaches.

# Project Evolution and Dashboard Gallery

## D1 — Portfolio Performance Overview

Initial descriptive analysis of premiums, claims, exposure, severity, and loss ratios.

<p align="center">
  <img src="https://raw.githubusercontent.com/amy165/Insurance-Risk-Pricing-Analysis-End-to-End-Project/main/images/Overview.jpg" width="750">
</p>

---

## D2 — Risk & Pricing Analysis

Identification of pricing gaps, expected losses, and risk segmentation by vehicle categories.

<p align="center">
  <img src="https://raw.githubusercontent.com/amy165/Insurance-Risk-Pricing-Analysis-End-to-End-Project/main/images/Pricing.jpg" width="750">
</p>

---

## D3 — Claim Risk Prediction & Model Evaluation

Development and evaluation of claim probability classification models.

 <p align="center">
  <img src="https://raw.githubusercontent.com/amy165/Insurance-Risk-Pricing-Analysis-End-to-End-Project/main/images/ML.jpg" width="750">
</p>

---

## D4 — Inflation-Adjusted Portfolio Analysis

Re-evaluation of portfolio performance using inflation-adjusted monetary values expressed in constant 2017 ETB.

<p align="center">
  <img src="https://raw.githubusercontent.com/amy165/Insurance-Risk-Pricing-Analysis-End-to-End-Project/main/images/Inflation.jpg" width="850">
</p>

---

## D5 — Pricing Strategy Simulation Overview

Simulation of alternative pricing strategies using historical risk experience and inflation-adjusted losses.

<p align="center">
  <img src="https://raw.githubusercontent.com/amy165/Insurance-Risk-Pricing-Analysis-End-to-End-Project/main/images/Repricing.jpg" width="850">
</p>

---

# Dataset

Source: Kaggle – Vehicle Insurance Dataset  
🔗 [Kaggle link](https://www.kaggle.com/datasets/imtkaggleteam/vehicle-insurance-data)

The dataset contains policy-level information, including:

- Policy information
- Vehicle categories
- Premium values
- Claim payments
- Policy duration
- Insured values
- Claim indicators

---

# Methodology

## Data Preparation
- Data cleaning
- Exposure normalization
- Inflation adjustment
- Feature engineering

## Portfolio Analytics
- Loss ratio analysis
- Severity & frequency analysis
- Pricing gap analysis

## Machine Learning
- XGBoost
- Random Forest
- Logistic Regression
- Threshold optimization

## Inflation Adjustment

Historical monetary values were adjusted to constant 2017 ETB using annual inflation rates.
Adjusted variables included:
- Premiums
- Claim payments
- Insured values

Inflation adjustment factors were calculated cumulatively relative to the 2017 base year.

The inflation data was obtained from publicly available macroeconomic sources for Ethiopia in the WorldBank.
[WorldBank link](https://datos.bancomundial.org/indicador/FP.CPI.TOTL.ZG?end=2024&locations=ET&start=2001)

## Pricing Simulations
- Previous-year repricing
- Multi-year historical repricing
- Promotional policy scenarios

### Simulation Notes

The repricing simulations focused on claim-cost adequacy and did not incorporate operational expenses, commissions, taxes, reinsurance costs, or profit margins.

Simulated premiums were estimated directly from expected losses using historical risk experience and inflation-adjusted claim costs.

Additional scenarios preserving promotional policies (`premium = 0`) were also evaluated.

---

# Tools & Technologies

## Analytics & Visualization
- Power BI
- DAX
- Python

## Python Libraries
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- XGBoost

---

# Project Structure

├── images/
├── notebooks/
│   └── README.md
├── powerbi/
│   └── README.md
├── README.md

Additional technical explanations are included inside specific folders where appropriate.

---

# Future Improvements

Potential future extensions include:

- Advanced actuarial pricing models
- Time-series forecasting
- Explainable AI techniques
- Combined ratio simulations
- Automated pricing recommendation systems


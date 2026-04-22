# 🚗 Insurance Risk & Pricing Analysis – End-to-End Project

## Overview

This project started with a critical business question:

*Is this insurance portfolio actually profitable, or is it silently losing money?*

Using a real-world motor insurance dataset, I built an end-to-end data science workflow to analyze **risk, pricing adequacy, and data quality issues**.

The goal was not just to build predictive models, but to simulate a realistic insurance scenario where:

- Data is imperfect  
- Pricing decisions may be inconsistent  
- Risk is not properly aligned with premiums  

The project combines **exploratory analysis, actuarial-style risk decomposition, and machine learning modeling**.

---

## 📂 Dataset

Motor insurance portfolio dataset (2011–2018)

Includes:

- Policy details (duration, type, usage)
- Vehicle characteristics (type, capacity, engine size)
- Financial variables (premium, insured value)
- Claims data (occurrence and severity)

---

## 🚀 What I Did

- Cleaned and validated a large insurance dataset with real-world inconsistencies  
- Engineered key variables:
  - Policy duration  
  - Vehicle age  
  - Risk segmentation  
  - Data quality flags (red flags)  
- Built a full **risk decomposition framework**:
  - Frequency  
  - Severity  
  - Expected loss (risk)  
- Compared premiums vs expected loss (pricing gap)  
- Developed ML models:
  - Logistic Regression  
  - Random Forest  
  - XGBoost  
- Handled class imbalance and tuned thresholds  
- Interpreted model outputs for business insights  

---

## 🧠 Business Questions

- Is the portfolio profitable?  
- Which segments generate the highest losses?  
- Are premiums aligned with expected risk?  
- Can we predict claim occurrence?  
- Are data quality issues impacting pricing decisions?  

---

## 📈 Portfolio Performance

- **Total Premium:** 5.94B  
- **Total Claims:** 15.41B  
- **Loss Ratio:** **2.6** 🚨  

👉 The portfolio is heavily unprofitable.

---

## ⚠️ Special Case – Zero Insured Value Policies

- Total claims paid: **8,250**
- Claim frequency: **~4.08%**
- Only a very small number of policies generated claims

👉 While most of these policies do not generate losses, their presence indicates **data quality issues**, as policies without insured value should not normally produce claims.

---

## 📊 Risk Decomposition (Key Insight)

Risk defined as:

> **Risk = Frequency × Severity**

### 🔥 Highest Risk Segments

| Vehicle Type | Risk | Avg Premium | Gap |
|-------------|------|------------|------|
| Truck | 46,581 | 14,247 | **-32,334** |
| Tanker | 39,737 | 16,906 | **-22,830** |
| Trailers | 29,791 | 6,522 | **-23,269** |
| Bus | 26,143 | 10,666 | **-15,476** |

👉 **Severe underpricing in heavy/commercial vehicles**

---

### 🟢 Low Risk Segments

| Vehicle Type | Risk | Avg Premium | Gap |
|-------------|------|------------|------|
| Motor-cycle | 185 | 588 | +403 |
| Tractor | 2,324 | 7,459 | +5,135 |

👉 These segments are **overpriced or profitable**

---

## 📊 Risk by Insured Value

| Segment | Risk | Premium | Gap |
|--------|------|--------|------|
| Low | 432 | 598 | +166 |
| Medium | 10,832 | 4,180 | **-6,651** |
| High | 21,095 | 8,006 | **-13,089** |
| Very High | 45,347 | 17,222 | **-28,124** |

👉 **Risk increases sharply with insured value, but pricing does not keep up**

---

## 📉 Visual Insight

![Risk vs Premium](./image.png)

👉 Clear mismatch between expected risk and pricing across vehicle types.

---

## 🤖 Modeling Approach

### Target
- `has_claim` → binary classification

---

### Model Comparison

| Model | ROC-AUC | Recall (Claims) | Notes |
|------|--------|----------------|------|
| Logistic | ~0.76 | Low | Baseline |
| Logistic (Balanced) | ~0.76 | High | Improved recall |
| Random Forest | ~0.78 | High | Tuned (max_depth=10) |
| XGBoost | **~0.79–0.80** | High | Best overall |

---

### 🔥 Best Model: XGBoost

- Strongest risk ranking (highest ROC-AUC)  
- High recall (~0.84–0.91 depending on threshold)  
- Suitable for **risk prioritization**

---

## 🔍 Feature Importance (XGBoost)

Top drivers:

- `insured_redflag` 🔥  
- Vehicle type  
- Carrying capacity  
- Seats number  
- Policy duration  
- Usage type  

👉 Data quality (missing insured value) is a **major risk indicator**

---

## ⚠️ Data Challenges

| Issue | Solution |
|------|----------|
| Missing/zero insured values | Flagged + group imputation |
| Inconsistent numeric variables | Median by group |
| Outliers | Retained (valid risk signal) |
| Class imbalance | Weighted models + threshold tuning |
| Premium inconsistencies | Excluded from modeling |

---

## 📊 Key Insights

- Portfolio is **structurally unprofitable**  
- Heavy vehicles drive most losses  
- Pricing is **not aligned with risk**  
- Risk increases with insured value  
- Data quality issues impact modeling  
- Models are better at **ranking risk than precise prediction**

---

## 🚀 Business Impact

This analysis can support:

- Pricing optimization  
- Risk segmentation  
- Underwriting decisions  
- Data quality improvements  
- Loss reduction strategies  

---

## 🛠 Tools & Tech

- Python (Pandas, NumPy, Scikit-learn, XGBoost)  
- Feature engineering  
- Classification modeling  
- Risk decomposition  

---

## ⏱ Project Scope & Limitations

This project was developed within a short time frame (~3 days) to simulate a real-world exploratory analysis scenario.

Given more time, further improvements could include:
- Hyperparameter tuning (GridSearch / Bayesian optimization)
- Advanced feature engineering
- Separate severity modeling (expected loss)
- Model calibration and probability tuning

---

## 📎 Notes

*AI tools were used for debugging and workflow support. All analytical decisions, modeling logic, and business interpretations are my own.*


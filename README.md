
# 🚗 Insurance Risk & Pricing Analysis – End-to-End Project

## 📌 Project Overview

This project analyzes a vehicle insurance portfolio to evaluate **business performance, pricing adequacy, and claim risk prediction**.

The goal was to connect **data analysis, business insights, and machine learning** in a real-world insurance context.

The analysis is structured into three main parts:

- Portfolio performance analysis  
- Pricing and risk evaluation  
- Claim prediction modeling  

---

## 📊 Dataset

Source: Kaggle – Vehicle Insurance Dataset  
🔗 [Kaggle link](https://www.kaggle.com/datasets/imtkaggleteam/vehicle-insurance-data)

The dataset contains policy-level information, including:

- Premiums and claims  
- Vehicle characteristics (type, usage, engine, etc.)  
- Policy periods (start/end dates)  
- Insured value   

### ⚠️ Data Challenges

One of the main challenges of this project was understanding the meaning and consistency of certain fields:

- `OBJECT_ID`: likely represents a grouped vehicle or policy identifier, not a unique policy  
- `EFFECTIVE_YR`: inconsistent and not clearly aligned with policy or vehicle timelines  

These ambiguities limited some cleaning decisions and highlight the importance of **domain knowledge in insurance datasets**.

---

## 🧹 Data Preparation

The data cleaning process was structured into **three datasets**, each aligned with a specific goal:

### 1. Performance Dataset
- No records removed  
- Missing `CLAIM_PAID` and `PREMIUM` filled with 0  
- Used for business-level portfolio analysis
- Feature engineering:
  - `has_claim`
  - `policy_duration`
  

### 2. Modeling Dataset
- Records with `policy_duration = 0` removed
- Invalid `vehicle_age` removed (< -3). Values of -1 and -2 imputed to 0  
- Missing `PROD_YEAR` removed  
- Null numerical features imputed using hierarchical grouping  
- Feature engineering:
  - `vehicle_age`
  - Grouping of insured value into risk-based segments
  - Creation of categorical buckets for vehicle age and policy duration

---

## 📈 Dashboard Analysis (Power BI)

Three dashboards were developed:

### 1. Portfolio Performance Overview
- Premium vs Claims over time  
- Loss Ratio evolution  
- Exposure growth  

📌 Key insights:
- Performance improves from 2015 onwards  
- Loss ratio remains above 100%  
- Premium growth is lower than exposure growth → **underpricing signal**

---

### 2. Risk & Pricing Analysis

- Exposure calculated based on policy duration  
- Metrics annualized for fair comparison  
- Expected Loss vs Premium (per year)  
- Claim frequency vs severity (Segmentation by vehicle type and insured value)  

📌 Key insights:
- Systematic underpricing in early years  
- Improvement by 2017 (underpriced segments reduced)  
- Loss ratio improvement driven by lower claims paid, not frequency
- This reduction in claims paid, while frequency remains relatively stable, may indicate improvements in claims validation processes or fraud detection.  

---

### 3. Claims Prediction (Machine Learning)
- Model comparison  
- Precision vs Recall trade-off  
- Feature importance analysis  
- Confusion matrix  

📌 Key metrics (XGBoost):
- ROC-AUC: ~0.76  
- PR-AUC: ~0.19 (vs baseline ~0.075)  
- Recall: ~78%  
- Precision: ~14%  

---

## 🤖 Machine Learning

Models tested:

- Logistic Regression  
- Logistic Regression (balanced)  
- Random Forest  
- Tuned Random Forest  
- XGBoost  

### ⚖️ Model Selection

The final model selected was:

👉 **XGBoost without data-quality flag variables**

Although including redflag variables improved performance, they were excluded to ensure:

- Better interpretability  
- Reduced dependence on data quality artifacts  

---

## 🧠 Key Insights

- Premiums do not scale proportionally with risk exposure  
- Underpricing is concentrated in specific vehicle segments  
- Portfolio improvement is driven by reduced claims severity, not frequency  
- Data quality issues (missing values, inconsistencies) strongly impact modeling results  

---

## 🛠️ Tools & Technologies

- Python (Pandas, NumPy, Scikit-learn, XGBoost)  
- Power BI  
- Google Colab  
- GitHub  

📌 Additional learning:
- Integration of Python scripts within Power BI  

---

## ⚠️ Limitations

- Lack of clear data dictionary for some variables  
- Potential inconsistencies in policy-level aggregation  
- Exposure approximation based on available dates  

---

## 📌 Key Learnings

- The importance of understanding business meaning behind data fields  
- Trade-offs between model performance and interpretability  
- Handling imbalanced datasets using appropriate metrics (PR-AUC, recall)  
- Designing dashboards aligned with business decision-making  

---

## 📷 Dashboard Preview

| Overview | Pricing | ML |
|----------|------------|----------|
| ![Overview](https://raw.githubusercontent.com/amy165/Insurance-Risk-Pricing-Analysis-End-to-End-Project/main/images/Overview.jpg) | ![Pricing](https://raw.githubusercontent.com/amy165/Insurance-Risk-Pricing-Analysis-End-to-End-Project/main/images/Pricing.jpg) | ![ML](https://raw.githubusercontent.com/amy165/Insurance-Risk-Pricing-Analysis-End-to-End-Project/main/images/ML.jpg) |


---

## 🚀 Next Steps

- Improve feature engineering with domain-driven variables  
- Explore claim severity modeling  
- Validate results with real insurance benchmarks  




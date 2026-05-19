# Power BI Dashboards & Data Modeling

## Overview

This folder contains the Power BI dashboards, data model, and DAX measures used throughout the insurance portfolio analysis project.

The Power BI solution evolved iteratively from descriptive portfolio monitoring into inflation-adjusted diagnostics and historical pricing strategy simulations.

---

# Dashboards

## D1 — Portfolio Performance Overview
Descriptive portfolio monitoring dashboard including:
- Premiums vs Claims
- Loss Ratios
- Exposure
- Severity
- Frequency

## D2 — Risk & Pricing Analysis
Pricing adequacy and portfolio segmentation dashboard including:
- Expected Loss analysis
- Pricing gap diagnostics
- Frequency vs Severity segmentation
- Vehicle risk profiling

## D3 — Claim Risk Prediction & Model Evaluation
Machine Learning monitoring dashboard including:
- Model comparison
- ROC-AUC and PR-AUC evaluation
- Threshold optimization
- Feature importance
- Confusion Matrix

## D4 — Inflation-Adjusted Portfolio Analysis
Inflation-normalized portfolio diagnostics including:
- Inflation-adjusted claims and premiums
- Monetary values normalized to constant 2017 ETB
- Adjusted pricing gap analysis

## D5 — Historical Risk-Based Pricing Simulation
Interactive repricing simulation dashboard including:
- Previous-year repricing
- Multi-year historical repricing
- Promotional policy scenarios
- Simulated underwriting performance

---

# Data Model

The Power BI model combines:
- Portfolio transaction data
- Inflation normalization factors
- Date dimensions
- Simulation tables

Key modeling decisions:
- Exposure normalization based on policy duration
- Inflation normalization relative to 2017 ETB
- Separate simulation tables generated from Python-based repricing workflows
- Disconnected slicer tables and dynamic DAX measures were used for scenario selection.

---

# DAX & Analytical Logic

The project uses extensive DAX calculations for:
- Loss ratio calculations
- Exposure normalization
- Inflation-adjusted metrics
- Expected loss calculations
- Pricing gap diagnostics
- Dynamic scenario selection
- Simulation KPI aggregation and visualization

Important analytical concepts:
- Frequency × Severity = expected loss estimation
- Inflation-normalized pricing analysis
- Historical repricing methodologies
- Promotional policy preservation scenarios

---

# Pricing Simulation Workflow

Historical repricing simulations were developed in Python and integrated into Power BI for scenario analysis and visualization.

The simulation workflow included:
- Previous-year repricing
- Multi-year historical repricing
- Promotional policy preservation scenarios

Power BI was then used for:
- Dynamic scenario exploration
- KPI tracking
- Vehicle-level performance analysis
- Interactive visualization

---

# Simulation Assumptions & Limitations

The pricing simulations focused exclusively on claim-cost adequacy.

The simulated repricing strategies:
- considered historical claim experience,
- exposure normalization,
- inflation-adjusted losses,
- and optional preservation of promotional policies (`premium = 0`),

but did not incorporate:
- operational expenses,
- commissions,
- reinsurance costs,
- taxes,
- or target profit margins.

Additionally, repricing was performed using estimated expected losses directly, without applying additional safety or profitability loadings.

Therefore, the simulations should be interpreted as simplified underwriting adequacy scenarios rather than complete actuarial pricing models.

The simulations assumed stable exposure and policy volumes after repricing.

Potential behavioral effects such as:
- customer attrition,
- portfolio mix changes,
- or exposure reductions resulting from premium increases

were not modeled.

---

# Visual Design Decisions

The dashboards follow a consistent visual language across the project:

- Dark blue → Claims
- Light blue → Premiums
- Dashed lines → Simulated scenarios
- Solid lines → Historical observed values
- Neutral gray palettes → Machine Learning evaluation metrics

The goal was to maintain analytical consistency while keeping dashboards visually clean and business-oriented.

# Power BI File

Main file:
- Insurance_Risk_Pricing_Analysis.pbix



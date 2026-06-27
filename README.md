# Demand Forecasting using Rolling Forecasting

## Project Overview

This project predicts weekly product demand for each supermarket–SKU combination eight weeks in advance using a rolling forecasting approach.

The objective is to help demand planners reduce stock-outs while minimizing excess inventory and write-offs.

---

## Dataset

Two datasets are used:

- demand.csv
- promotions.csv

The demand dataset contains historical daily sales.

The promotions dataset contains promotional periods for each supermarket and SKU.

---

## Workflow

- Data Cleaning
- Exploratory Data Analysis
- Weekly Aggregation
- Promotion Integration
- Feature Engineering
- Rolling Forecasting
- Model Evaluation
- Business Insights

---

## Feature Engineering

The model uses:

- Lag Features
- Rolling Mean
- Rolling Standard Deviation
- Calendar Features
- Promotion Indicator

---

## Model

Random Forest Regressor

Forecast Horizon:
8 Weeks

Forecast Strategy:
Rolling Origin Forecasting

---

## Evaluation

Metrics:

- MAE
- RMSE
- MAPE

---

## Business Impact

The forecasting model helps:

- Reduce Stock-outs
- Reduce Write-offs
- Improve Production Planning
- Support Inventory Optimization

---

## Technologies

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

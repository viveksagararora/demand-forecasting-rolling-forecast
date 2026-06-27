# 📈 Demand Forecasting using Rolling-Origin Forecasting

A machine learning-based demand forecasting solution that predicts **weekly demand for each SKU at each supermarket 8 weeks in advance** using a **Rolling-Origin Forecasting** strategy and **Random Forest Regression**.

The project was developed as part of a Demand Forecasting Case Study to simulate a real-world retail demand planning workflow.

---

## 📌 Problem Statement

A beverage company aims to improve production planning by forecasting product demand across multiple supermarket chains.

The objective is to:

- Forecast demand **8 weeks ahead** for every **Supermarket–SKU** combination.
- Reduce **stock-outs** caused by underproduction.
- Minimize **inventory write-offs** caused by overproduction.
- Build forecasts using only historical information available at the time of prediction (Rolling Forecasting).

---

## 📂 Dataset

Two datasets were provided:

### 1. demand.csv
Historical daily demand from **1 January 2019 to 9 September 2021**.

| Column | Description |
|---------|-------------|
| date | Calendar Date |
| supermarket | FreshMart, GreenBasket, DailyNeeds |
| sku | Organic Milk, Whole Wheat Bread, Free Range Eggs |
| demand | Daily Units Sold |

---

### 2. promotions.csv

Contains promotion start dates for each supermarket–SKU combination.

Promotions remain active for **one week**.

---

# 🚀 Project Workflow

```
Data Loading
      │
      ▼
Data Cleaning & Quality Checks
      │
      ▼
Exploratory Data Analysis
      │
      ▼
Weekly Aggregation
      │
      ▼
Promotion Integration
      │
      ▼
Feature Engineering
      │
      ▼
Rolling-Origin Forecasting
      │
      ▼
Model Evaluation
      │
      ▼
Feature Importance Analysis
      │
      ▼
Business Insights
```

---

# 🔍 Exploratory Data Analysis

The following analyses were performed:

- Missing value analysis
- Duplicate detection
- Demand trend analysis
- Weekly demand visualization
- Seasonality analysis
- Promotion impact analysis
- Demand distribution
- Correlation analysis
- Demand comparison across supermarkets and SKUs

These analyses helped identify the major factors influencing demand before model development.

---

# ⚙️ Feature Engineering

The following features were created using only historical information.

### Calendar Features

- Year
- Month
- Week Number

### Lag Features

- Previous Week Demand (Lag-1)
- Lag-2
- Lag-4
- Lag-8

### Rolling Statistics

- 4-Week Rolling Mean
- 8-Week Rolling Mean
- 4-Week Rolling Standard Deviation

### External Features

- Promotion Indicator

These features capture historical demand behaviour, short-term trends, and promotional effects.

---

# 🤖 Forecasting Model

### Model

**Random Forest Regressor**

### Forecast Horizon

**8 Weeks Ahead**

### Forecasting Strategy

The project uses **Rolling-Origin Forecasting**.

For every forecasting week:

1. Train using all historical data available up to that point.
2. Predict demand exactly **8 weeks ahead**.
3. Move the forecasting origin forward by one week.
4. Retrain the model.
5. Repeat until the end of the dataset.

This closely replicates how demand forecasting is performed in production environments.

---

# 📊 Model Evaluation

The model was evaluated using a **Rolling-Origin Forecasting** strategy, ensuring that predictions were generated using only historical data available at each forecast origin. This approach closely simulates a real-world demand planning workflow and prevents future data leakage.

### Evaluation Metrics

| Metric | Value |
|---------|-------|
| **MAE** | **27.17** |
| **RMSE** | **63.53** |
| **MAPE** | **5.00%** |

### Why These Metrics?

- **MAE (Mean Absolute Error)** is the primary business metric because it measures the average forecasting error in units sold. This directly reflects how much production may differ from actual demand, making it valuable for estimating the risk of stock-outs and excess inventory.

- **RMSE (Root Mean Squared Error)** places greater emphasis on larger forecasting errors, helping identify periods where demand deviates significantly from predictions.

- **MAPE (Mean Absolute Percentage Error)** expresses forecasting error as a percentage, making model performance easy to interpret across different supermarket–SKU combinations.

A **MAPE of 5.00%** indicates that the model predicts weekly demand with high accuracy while maintaining a realistic rolling forecasting evaluation strategy.

---

# 📈 Key Demand Drivers

Feature importance analysis showed that demand is primarily influenced by:

- Historical demand (Lag Features)
- Recent demand trends
- Promotional events
- Weekly seasonality
- Calendar effects

Historical demand was identified as the strongest predictor of future demand.

---

# 💼 Business Impact

The proposed forecasting solution can help demand planners:

- Reduce stock-outs by improving production planning.
- Minimize inventory write-offs caused by overproduction.
- Improve inventory allocation across supermarkets.
- Support data-driven production scheduling.
- Enable more accurate demand planning.

---

# 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

---


# 👨‍💻 Author

**Vivek Sagar Arora**

B.Tech Computer Science & Engineering (AI/ML)  
Bennett University

- LinkedIn: https://www.linkedin.com/in/vivek-sagar-arora-33b84b2bb/
- GitHub: https://github.com/viveksagararora

---

# ⭐ Results Summary

- ✔ Forecasted demand **8 weeks ahead**
- ✔ Used **Rolling-Origin Forecasting**
- ✔ Predicted demand for **each Supermarket–SKU combination**
- ✔ Achieved **4.12% MAPE**
- ✔ Built an interpretable machine learning forecasting pipeline suitable for retail demand planning.

---

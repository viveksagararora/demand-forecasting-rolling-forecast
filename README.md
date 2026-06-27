# Demand Forecasting using Rolling-Origin Forecasting

## Project Overview

This project develops a machine learning-based demand forecasting solution to predict weekly demand for each SKU at each supermarket **8 weeks in advance**. The objective is to support demand planners in improving production planning, reducing stock-outs, and minimizing excess inventory and write-offs.

The forecasting model follows a **rolling-origin forecasting strategy**, ensuring that predictions are generated using only the information available up to each forecast date, closely simulating a real-world demand planning process.

---

## Business Problem

The demand planning team previously maintained an effective balance between production and customer demand. Following the departure of the senior demand planner, forecasting accuracy declined, resulting in:

- Frequent stock-outs for high-demand products.
- Excess production leading to inventory write-offs.
- Reduced efficiency in production planning.

The objective of this project is to build a forecasting model capable of predicting demand **8 weeks ahead** for every supermarket–SKU combination.

---

## Dataset

Two datasets were provided for the case study.

### demand.csv

Daily historical demand from **1 January 2019 to 9 September 2021**.

| Column | Description |
|---------|-------------|
| date | Calendar date |
| supermarket | Supermarket chain |
| sku | Product (SKU) |
| demand | Units sold |

---

### promotions.csv

Promotion start dates for supermarket–SKU combinations.

| Column | Description |
|---------|-------------|
| promotion_date | First day of promotion |
| supermarket | Supermarket chain |
| sku | Product |

Promotions last for one week from the listed promotion date.

---

## Project Workflow

1. Data Loading
2. Data Cleaning and Preprocessing
3. Exploratory Data Analysis
4. Weekly Demand Aggregation
5. Promotion Integration
6. Feature Engineering
7. Rolling-Origin Forecasting
8. Model Evaluation
9. Feature Importance Analysis
10. Business Insights

---

## Exploratory Data Analysis

The following analyses were performed:

- Data quality assessment
- Missing value analysis
- Demand trend visualization
- Demand distribution
- Weekly demand patterns
- Promotion impact analysis
- Seasonality analysis
- Correlation analysis

These analyses helped identify historical demand behavior and understand the major drivers influencing demand.

---

## Feature Engineering

The forecasting model uses multiple time-series features generated from historical demand.

### Calendar Features

- Year
- Month
- Week Number

### Historical Demand Features

- Lag 1 Week
- Lag 2 Weeks
- Lag 4 Weeks
- Lag 8 Weeks

### Rolling Statistics

- 4-Week Rolling Mean
- 8-Week Rolling Mean
- 4-Week Rolling Standard Deviation

### External Feature

- Promotion Indicator

These features were created using only historical observations to avoid future data leakage.

---

## Forecasting Strategy

Instead of using a random train-test split, the project follows a **Rolling-Origin Forecasting** approach.

For every forecast origin:

1. Train the model using all historical data available up to that week.
2. Predict demand exactly **8 weeks ahead**.
3. Move the forecasting origin forward by one week.
4. Retrain the model.
5. Repeat until the end of the dataset.

This evaluation strategy closely resembles how forecasting systems operate in production environments.

---

## Machine Learning Model

**Random Forest Regressor**

Model Parameters:

- 200 Decision Trees
- Maximum Depth = 10
- Random State = 42

The Random Forest model was selected because it effectively captures nonlinear demand patterns while remaining robust to noisy retail demand data.

---

## Model Evaluation

The forecasting model was evaluated using a rolling-origin forecasting strategy.

| Metric | Score |
|---------|-------|
| **MAE** | **24.14** |
| **RMSE** | **56.73** |
| **MAPE** | **4.12%** |

### Interpretation

- The model predicts weekly demand with an average percentage error of only **4.12%**.
- On average, forecasts differ from actual demand by approximately **24 units**.
- The model successfully captures the majority of weekly demand patterns while maintaining realistic forecasting conditions.

---

## Demand Drivers

Feature importance analysis indicates that demand is primarily influenced by:

- Historical demand patterns
- Recent sales trends
- Promotional events
- Seasonal variations
- Calendar effects

Historical demand (lag features) was identified as the strongest predictor of future demand.

---

## Business Impact

The proposed forecasting solution can help demand planners:

- Reduce stock-outs by improving demand visibility.
- Reduce inventory write-offs caused by overproduction.
- Improve production scheduling.
- Support better inventory allocation across supermarkets.
- Enable more informed operational planning.

---

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

---

## Repository Structure

```
Demand-Forecasting/
│
├── data/
│   ├── demand.csv
│   └── promotions.csv
│
├── notebook/
│   └── Demand_Forecasting.ipynb
│
├── presentation/
│   └── Business_Summary.pdf
│
├── images/
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## Future Improvements

Potential future enhancements include:

- Gradient Boosting and XGBoost models
- LightGBM or CatBoost for improved forecasting accuracy
- Hyperparameter optimization
- Additional external variables such as holidays, weather, and pricing
- Automated retraining pipeline for production deployment

---

## Author

**Vivek Sagar Arora**

B.Tech Computer Science & Engineering (AI/ML)

Bennett University

LinkedIn: https://www.linkedin.com/in/vivek-sagar-arora-33b84b2bb/

---

## License

This project was developed as part of a Demand Forecasting Case Study for educational and internship evaluation purposes.

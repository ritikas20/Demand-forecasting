# Demand-forecasting
# 📦 Demand Forecasting using LightGBM

This project forecasts **6-month product demand** using historical data and advanced machine learning techniques. It focuses on generating accurate predictions to support inventory management and supply chain decision-making.

---

## 📌 Project Overview

- **Objective:** Predict demand for different products for the upcoming 6 months.
- **Model Used:** LightGBM Regressor
- **Evaluation Metrics:**
  - **Validation MAE:** 899.87
  - **Validation WMAPE:** 15.57%

---

## 🧠 Key Features & Methodology

### 🔍 Feature Engineering

Extensive feature engineering was performed to enrich the dataset:

- **Temporal Features**
  - Extracted from date column:
    - `year`, `month`, `quarter`, etc.

- **Lag Features**
  - Created lag variables such as:
    - `demand_lag_1`, `demand_lag_3`, etc.

- **Rolling Statistics**
  - Computed moving averages and variability measures:
    - `rolling_mean_3`, `rolling_mean_6`, etc.

- **Weighted Lag Features**
  - Applied exponential decay to give more weight to recent data:
    - e.g., `weighted_lag_3`

- **Correlation-based Feature Selection**
  - From features `x2` to `x112`, only features highly correlated with the dependent variable (target) were retained.

---

## 🏗️ Model Training

- **Model:** LightGBM Regressor
- **Training Strategy:**
  - Time-based validation to simulate future predictions
  - Early stopping to prevent overfitting
- **Hyperparameters:**
  - Default settings with minor tuning on learning rate and boosting rounds

---

## 📈 Results

| Metric | Value     |
|--------|-----------|
| MAE    | 899.87    |
| WMAPE  | 15.57%    |

The model shows strong forecasting performance, especially given the product diversity and temporal variance in demand.

---



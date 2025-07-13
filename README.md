# 🧠 M5 Forecasting - Retail Sales Prediction

This project solves a real-world business problem using the **M5 Forecasting - Accuracy dataset** from Kaggle. It applies machine learning to forecast product-level daily sales, helping retailers optimize inventory, pricing, and promotions.

---

## 🏢 Business Problem

Walmart and similar large retailers need accurate **daily sales forecasts** for thousands of products across different stores. Accurate predictions help:
- Reduce overstock/understock
- Optimize promotional events
- Manage supply chain and pricing strategies

---

## 📚 Dataset

- Source: [Kaggle M5 Forecasting - Accuracy](https://www.kaggle.com/competitions/m5-forecasting-accuracy)
- Files used:
  - `sales_train_validation.csv`
  - `calendar.csv`
  - `sell_prices.csv`

---

## 📊 Exploratory Data Analysis (EDA)

Key patterns observed:
- **Weekly seasonality** in item sales
- **Holiday/event-based spikes**
- **Price-sensitive demand**
- **SNAP days** increased demand for essential goods

---

## 🧠 Approach & Methodology

### 1. **Data Preparation**
- Merged all three datasets
- Created lag features (`lag_7`, `lag_14`, `lag_28`)
- Rolling means (`rolling_mean_7`, `rolling_mean_28`)
- Date-based features (day, weekday, month, year)
- Flags for events and SNAP days
- Price change feature

### 2. **Model Selection**
- Used `LightGBM` (`lgb.train`)
- Chosen for high speed, accuracy, and native support for categorical data

### 3. **Model Training**
- Used last 28 days as test set
- TimeSeriesSplit cross-validation
- Evaluation Metric: **RMSE**
- Final RMSE: 1.58 

### 4. **Reporting**
- Visualized prediction vs actual sales
- Analyzed feature importance (lags, price, day-of-week, events)
- Documented key insights for business use

---

## 📌 Insights

- Short-term lags (7, 14, 28) are powerful predictors
- Price changes directly affect sales
- SNAP and event days significantly impact sales trends
- Model supports real-world applications in **demand planning**, **pricing**, and **inventory control**

---

## 🚀 Future Work

- Hyperparameter tuning with Optuna
- Deploy forecasting as a web app (Streamlit/Dash)
- Compare with models like Facebook Prophet or LSTM

---

## 📁 Files

- `M5_Forecasting_Accuracy_Task1.ipynb`: full notebook
- `README.md`: project summary
- `m5_sales_model.pkl`: optional exported model

---

## 🏷️ Tags
`Machine Learning` `Retail Forecasting` `LightGBM` `Time Series` `M5 Dataset` `Python` `EDA`

---

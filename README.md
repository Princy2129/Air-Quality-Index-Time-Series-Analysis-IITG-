# 🌫️ Air Quality Forecasting — CO(GT) Prediction

This project focuses on forecasting Carbon Monoxide (CO) levels using time series and machine learning techniques on the UCI Air Quality dataset.

---

## 📌 Project Overview

Air pollution is a serious concern in many cities, and being able to predict pollutant levels can help with better planning and early warnings.

In this project, I built an end-to-end pipeline to predict **CO(GT)** levels using three different approaches:

* ARIMA (statistical model)
* XGBoost (machine learning model)
* Prophet (time-series decomposition model)

The idea was to compare these models and understand which works best for short-term forecasting.

---

## 🎯 Objectives

* Explore and understand the dataset
* Create useful time-based and lag features
* Train multiple forecasting models
* Compare their performance using MAE, RMSE, and MAPE
* Extract meaningful insights from the data

---

## 📊 Dataset

* Source: UCI Machine Learning Repository
* ~9,357 hourly observations
* Time period: March 2004 – February 2005
* Target variable: **CO(GT)** (mg/m³)

The dataset includes:

* Sensor readings (e.g., PT08.S1(CO), NOx, NO2)
* Weather data (temperature, humidity)
* Missing values encoded as **-200**

---

## ⚙️ Models Used

### ARIMA

A classic time series model used to capture trends. It worked as a baseline but struggled with the variability in hourly data.

### XGBoost ⭐ (Best Performing)

This model performed the best after adding:

* Lag features
* Rolling statistics
* Time-based (cyclical) features

It was able to capture both short-term patterns and nonlinear relationships in the data.

### Prophet

Useful for understanding overall trends and seasonality. It’s easy to interpret but less accurate for short-term fluctuations.

---

## 📈 Results

| Model   | Performance |
| ------- | ----------- |
| ARIMA   | Baseline    |
| Prophet | Moderate    |
| XGBoost | ⭐ Best      |

---

## 🔍 Key Insights

* CO levels spike during **rush hours (8–9 AM and 6–8 PM)**
* Pollution is generally higher on **weekdays** than weekends
* **Winter months** show higher CO levels
* The sensor **PT08.S1(CO)** is the strongest predictor

---

## 🛠️ Tech Stack

* Python
* Pandas, NumPy
* Matplotlib, Seaborn
* Statsmodels
* XGBoost
* Prophet
* Scikit-learn

---

## 📂 Project Structure

```id="eqnm47"
air-quality-forecasting/
│
├── data/
│   └── AirQualityUCI.xlsx
│
├── notebooks/
│   └── air_quality_forecasting.ipynb
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## 🚀 Installation

```bash id="buj9e1"
git clone https://github.com/your-username/air-quality-forecasting.git
cd air-quality-forecasting
pip install -r requirements.txt
```

---

## ▶️ Usage

```bash id="l3kmr6"
jupyter notebook notebooks/air_quality_forecasting.ipynb
```

---

## 🚀 Future Work

* Try SARIMA/SARIMAX to better capture seasonality
* Build hybrid models (e.g., ARIMA + XGBoost)
* Experiment with deep learning models like LSTM/GRU
* Add proper time-series cross-validation
* Deploy the model using FastAPI
* Build a simple alert system for high pollution levels

---

## 📚 References

* UCI Air Quality Dataset
* XGBoost paper (Chen & Guestrin, 2016)
* Prophet (Facebook)
* Forecasting: Principles and Practice — Hyndman

---

## 👨‍💻 Author

This project was built as part of a data science portfolio.

---

# ⚡ Predicting Household Power Consumption with Machine Learning

![Made with R](https://img.shields.io/badge/Made%20with-R-1f425f.svg)
![Language](https://img.shields.io/badge/language-R-blue.svg)
![Status](https://img.shields.io/badge/status-Completed-brightgreen)

This project analyzes 4 years of detailed household power consumption data to predict daily electricity usage using machine learning models in R. It was completed as part of the **DataCamp Real-World Projects** series.

---

## 🔍 Project Overview

Modern smart homes generate granular electricity consumption data. This project leverages that data to:

- Explore seasonal and weekly usage patterns
- Engineer time-based features for modeling
- Train and compare **Random Forest** and **XGBoost** models
- Predict daily electricity usage for future time points

By improving consumption forecasting, such models can benefit energy providers and consumers alike through **load balancing**, **personalized recommendations**, and **grid efficiency**.

---

## 🧾 Dataset

The dataset consists of **train** and **test** sets:

- `df_train.csv`: Historical data used for training models  
- `df_test.csv`: Future data used to evaluate model predictions  

| Column             | Type   | Description                                                  |
|--------------------|--------|--------------------------------------------------------------|
| `date`             | chr    | Date of measurement                                          |
| `power_consumption`| dbl    | Daily electricity usage (kW)                                 |
| `year`             | int    | Year of observation                                          |
| `semester`         | int    | Semester (1: Jan–Jun, 2: Jul–Dec)                            |
| `quarter`          | int    | Quarter (1–4)                                                |
| `month`            | int    | Month (1–12)                                                 |
| `day_in_week`      | chr    | Weekday (e.g., Mon, Tue, ...)                                |
| `week_in_year`     | int    | Week number                                                  |
| `day_in_year`      | int    | Day number in the year                                       |

> ℹ️ Source: UCI Machine Learning Repository

---

## 🧠 Methodology

### 📊 Exploratory Data Analysis (EDA)

- Temporal patterns: average consumption by **year**, **month**, and **day of week**
- NA handling and categorical encoding (e.g., `day_in_week`)

### 🔨 Feature Engineering

- One-hot encoding using `model.matrix()`
- Creation of time-based predictors (e.g., semester, quarter)

### 🤖 Models Trained

- **Random Forest** (`ranger`)  
- **XGBoost** (`xgboost` with `reg:squarederror`)

Both models were trained on the same feature set and evaluated on the test set using **Root Mean Squared Error (RMSE)**.

---

## 📈 Results

| Model           | RMSE       |
|----------------|------------|
| Random Forest  | **391.50** |
| XGBoost        | 435.69     |

The Random Forest model outperformed XGBoost in predictive accuracy.

### ✅ Trend Matching

Both models captured **weekday-level patterns** in electricity usage, showing good alignment between observed and predicted daily trends.

---

## 🛠 Tech Stack

- **Language**: R  
- **Libraries**: `dplyr`, `lubridate`, `ggplot2`, `ranger`, `xgboost`, `caret`, `model.matrix`

---

## 📂 Files

| File | Description |
|------|-------------|
| `power_consumption.Rmd` | Full R Markdown script with EDA, modeling, and visualizations |
| `power_consumption.html` | HTML output (knitted) of the analysis *(optional upload)* |
| `df_train.csv` *(not uploaded)* | Training dataset |
| `df_test.csv` *(not uploaded)* | Testing dataset |

---

## 📌 Notes

- This project was completed as part of the **DataCamp Associate Data Scientist (R)** certification track.  
- Raw CSV data is not included to respect licensing.  
- Cover image (`imagegeneratedbyai.png`) is optional and AI-generated for illustration purposes.
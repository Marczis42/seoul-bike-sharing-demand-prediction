# Seoul Bike Sharing Demand Prediction

A Machine Learning and Time Series project in R to forecast hourly bike-sharing demand in urban environment, comparing traditional statistical forecasting methods with supervised machine learning algorithm.

---

## Project Overview
Bike-sharing systems provide a sustainable and flexible transportation mode in modern cities. Accurately forecasting demand is important for fleet rebalancing, operational efficiency, and maintenance planning.

The goal of this project is to model and predict the target variable **`Rented Bike Count`** (hourly rentals) using weather conditions, seasonal patterns, and calendar features.

* **Dataset Source:** [UCI Machine Learning Repository - Seoul Bike Sharing Demand](https://archive.ics.uci.edu/dataset/560/seoul+bike+sharing+demand)

---

## Tech Stack & Libraries
* **Language:** R
* **Data Manipulation & Visualization:** `tidyverse`, `dplyr`, `readr`, `ggplot2`, `corrplot`
* **Time Series Modeling:** `forecast`, `vars`, `zoo`, `lubridate`
* **Machine Learning Framework:** `tidymodels`

---

## Data Preprocessing
1. **Operating Days Filtering:** Removed 12 full non-functioning days and 1 partially affected day where rental counts were structurally zero due to system shutdowns, avoiding artificial bias in demand estimation.
2. **Missing Value & Quality Checks:** Confirmed no missing values or data type parsing errors across all meteorological columns.
3. **Exploratory Data Analysis (EDA):** Evaluated rental distribution (spread, variance, outliers) using jitter plots and density curves.
4. **Feature Engineering:** Extracted hour, day-of-week, season, holiday indicators, and weather interaction factors (temperature, dew point, humidity, solar radiation).

---

## Models Compared
* **Statistical Time Series:**
  * ARIMA
  * SARIMA
  * Vector Autoregression (VAR)
* **Machine Learning:**
  * Random Forest Regressor (Non-linear interactions, weather sensitivities)

---

## Key Results

| Model | RMSE | MAE | R² |
| :--- | :---: | :---: | :---: |
| **ARIMA** | *412.5* | *260.1* | *0.65* |
| **VAR** | *385.2* | *p235.4* | *0.71* |
| **Random Forest** | *182.4* | *104.8* | *0.89* |

> **Key Takeaway:** Random Forest significantly outperformed classical linear time series models by capturing complex non-linear interactions between peak commute hours and meteorological thresholds (e.g., rainfall, freezing temperatures).

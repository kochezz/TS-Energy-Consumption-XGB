# ⚡ Hourly Energy Demand Forecasting using XGBoost + R Shiny

[![Built With Python](https://img.shields.io/badge/Built%20With-Python-blue?logo=python)](https://www.python.org/)
[![Built With R](https://img.shields.io/badge/Built%20With-R-lightgrey?logo=r)](https://www.r-project.org/)
[![Dashboard](https://img.shields.io/badge/Dashboard-R%20Shiny-green)](https://shiny.posit.co/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

---

## 📘 Project Overview

This project delivers an end-to-end **energy demand forecasting solution** using Python for model development and R for interactive visualization.

It includes:
- A **Python pipeline** for preprocessing, feature engineering, XGBoost training, and forecasting.
- A **Shiny dashboard** to visualize actual vs. predicted demand, explore forecasts, and download results.

The dataset (`PJME_hourly.csv`) represents hourly electrical energy demand (in megawatts) across the PJM East region.

---

## 📂 Repository Structure

```
TS_Energy_Consumption_XGB/
├── data/
│   ├── raw/                       # Original PJME_hourly.csv
│   ├── processed/                 # Feature-engineered datasets, test/train splits
├── models/
│   └── xgb_model.joblib           # Trained XGBoost model
├── notebooks/
│   └── 01_EDA.ipynb               # Jupyter notebook (EDA + modeling + forecasting)
├── scripts/
│   └── pipeline.py                # Full reusable forecasting pipeline
├── reports/
│   └── 7_day_forecast.csv         # Final forecast exported to CSV
└── README.md                      # Project documentation

TS_Energy_Consumption_XGB_R/
├── app.R                          # Shiny app (forecast explorer UI)
├── data/
│   └── actual_forecast_combined.csv
├── images/
│   └── BEDA_logo.png              # Custom dark logo for dashboard
```

---

## 🧠 Python Model Development Summary

| Step                | Outcome                                                                 |
|---------------------|-------------------------------------------------------------------------|
| Data Cleaning       | Time-indexed, timezone-naive datetime column created                    |
| Feature Engineering | Extracted hour, dayofweek, dayofyear, etc.                              |
| Model               | `XGBRegressor` with hyperparameter tuning + early stopping              |
| RMSE on Test Set    | ~3743.56 MW                                                             |
| Forecast Horizon    | 7–14 days (with auto feature generation)                                |
| Export              | Model saved as `xgb_model.joblib` for reuse                             |

---

## 📊 Visualization & R Shiny Dashboard

The R-based dashboard includes:

| Feature                        | Description |
|-------------------------------|-------------|
| 🗂 Collapsible Panels           | Summary table, Accuracy metrics, and Plot panels |
| 🌗 Theme Toggle                | Dark and Light theme switching with auto-styling |
| 📅 Date Range Controls         | User input for forecast horizon control |
| 📈 Interactive Plotly Charts   | Line, Bar, and Pie chart toggle views |
| 📥 Download Button             | Export filtered forecast data |
| 📌 Accuracy Metrics            | MAE, RMSE, MAPE |
| 📊 Daily Summary Stats         | Peak load and total forecast |

> Deployment is set up for [shinyapps.io](https://shinyapps.io) and supports `.Rproj` structure and `renv` lock files.

---

## 📈 Forecast Example

> Sample visualization below showing Actual vs Forecasted Load:

![Forecast Demo](images/demo_forecast.png)

---

## 💾 Files Saved

- `xgb_model.joblib`: Serialized model for future use
- `actual_forecast_combined.csv`: Merged actual + forecast data
- `7_day_forecast.csv`: Clean forecast export for dashboard
- `app.R`: Fully functional and styled R Shiny dashboard

---

## 🚀 Next Steps

- Integrate confidence intervals (Python + R)
- Add model comparison (e.g., LSTM, Prophet)
- Enable user-uploadable data in the dashboard
- Serve dashboard via containerized deployment (Docker)

---

## 📬 Contact

Developed by **Business Enterprise Data Architecture (BEDA)**  
📩 Email: [wphiri@beda.ie](mailto:wphiri@beda.ie)  
🔗 LinkedIn: [William Phiri](https://www.linkedin.com/in/william-phiri-866b8443/)  
🧭 _"Get it done the BEDA way"_

---

## 📄 License

This project is licensed under the MIT License.

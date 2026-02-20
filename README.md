# FUTURE-ML-01
# Sales & Demand Forecasting – Grocery Retail  
**Machine Learning Task 1 (2026) | Future Interns**

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)  
[![XGBoost](https://img.shields.io/badge/Model-XGBoost-orange)](https://xgboost.readthedocs.io/)  
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

## Project Overview
This repository contains a complete **sales and demand forecasting solution** built for the **Future Interns Machine Learning Task 1 (2026)**.  
The goal was to predict future sales using historical time-series data from Corporación Favorita (Ecuadorian grocery retailer), with a strong focus on **business impact** — helping store owners/managers with inventory planning, staffing, cash flow, and promotion decisions.

**Dataset:** Kaggle – [Store Sales – Time Series Forecasting](https://www.kaggle.com/competitions/store-sales-time-series-forecasting)  
**~3 million rows** of daily sales across 54 stores and 33 product families (2013–2017).

## Key Features & Approach
- **Data Preparation** — Cleaned missing values, merged oil prices, holidays, store metadata
- **Feature Engineering** — 
  - Time-based: year, month, dayofweek, payday, cyclic sin/cos seasonality
  - Lags & rolling: sales_lag_7/14/28/365, rolling mean 7/14 days
  - External: promotions (onpromotion), real holidays, oil price
  - Target: log1p(sales) transformation
- **Model:** XGBoost Regressor with categorical support, early stopping, and RMSE monitoring
- **Evaluation:** Time-based split (train until mid-2017, validate last months)

## Results
**Validation Performance (June–August 2017):**
- **RMSLE** (Root Mean Squared Log Error): **0.3380** (strong baseline)
- **MAE** (original units): **51.73** units per prediction
- **Best iteration:** 798 trees

**Business Value:**
- Captures weekly cycles (weekends/paydays +15–25%), holiday lifts, promotion effects
- Helps reduce stockouts/overstock → estimated 10–25% efficiency gain in inventory
- Enables better staffing & cash flow planning

## Project Structure

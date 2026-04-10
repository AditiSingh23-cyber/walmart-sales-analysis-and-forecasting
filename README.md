# walmart-sales-analysis-and-forecasting
Analyzed Walmart store sales data, identified trends and factors affecting weekly sales, and forecasted future sales using SARIMA time series modeling.

## Project Overview
This project analyzes Walmart store sales data to understand the factors affecting weekly sales and forecast future sales using time series forecasting techniques.

The project focuses on:
- Identifying weekly sales trends and seasonal patterns
- Comparing performance across different Walmart stores
- Studying the effect of unemployment, CPI, fuel price, temperature, holidays, and markdowns on weekly sales
- Forecasting future weekly sales for a selected Walmart store using the SARIMA model

---

## Problem Statement
Walmart store sales are affected by several external and internal factors such as holidays, seasonal demand, unemployment, fuel price, and store-specific performance. The aim of this project is to analyze these factors and predict future sales.

Objectives:
- Analyze historical weekly sales
- Discover major business trends and patterns
- Identify which factors influence sales the most
- Forecast the next 12 weeks of sales for a selected store

---

## Dataset Information

The dataset contains weekly Walmart sales data with the following columns:

| Column Name | Description |
|------------|------------|
| Store | Store number |
| Date | Weekly date |
| Weekly_Sales | Total weekly sales for the store |
| Holiday_Flag | Indicates whether the week includes a holiday |
| Temperature | Average temperature during the week |
| Fuel_Price | Fuel price during the week |
| CPI | Consumer Price Index |
| Unemployment | Unemployment rate |

---

## Project Workflow

### 1. Data Collection and Cleaning
- Loaded the Walmart dataset
- Converted the `Date` column into datetime format
- Checked and removed missing values and duplicate records
- Filtered data for the selected Walmart store

### 2. Exploratory Data Analysis (EDA)
Performed various analyses to understand the data:

- Weekly sales trend over time
- Comparison of sales between stores
- Effect of unemployment on weekly sales
- Relationship between temperature and sales
- Holiday vs non-holiday sales comparison
- Correlation between CPI, fuel price, unemployment, and weekly sales
- Identification of the highest and lowest performing stores

### 3. Time Series Preparation
- Set `Date` as the index
- Checked whether the data was stationary
- Applied differencing when required
- Prepared the data for forecasting

### 4. Sales Forecasting
Used the SARIMA model to forecast weekly sales for the next 12 weeks.

Steps:
- Selected one store for forecasting
- Split the data into training and testing sets
- Built the SARIMA model
- Predicted future sales
- Compared actual and predicted sales values
- Evaluated model performance using RMSE

---

## Why SARIMA Was Used
The SARIMA (Seasonal AutoRegressive Integrated Moving Average) model was chosen because Walmart sales data contains both trend and seasonal patterns.

For example:
- Sales usually increase during holiday seasons
- Similar sales patterns repeat every year
- Weekly sales rise and fall over time

SARIMA is useful because it can capture:
- Trend
- Seasonality
- Time-based changes in the sales data

Example model used:

```python
SARIMA(1,1,1)(1,1,1,12)

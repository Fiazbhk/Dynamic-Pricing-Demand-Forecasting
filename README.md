# Dynamic Pricing Demand Forecasting

A machine learning project that applies demand forecasting models to evaluate dynamic pricing strategies in retail. Built using five years of daily sales data from the Kaggle Store Item Demand Forecasting Challenge.

---

## Overview

This project investigates whether machine learning models can forecast retail demand accurately enough to support dynamic pricing decisions. It compares three pricing strategies, trains four forecasting models, and derives optimal price and marketing budget recommendations using price elasticity of demand.

---

## Dataset

- Source: [Store Item Demand Forecasting Challenge — Kaggle](https://www.kaggle.com/competitions/demand-forecasting-kernels-only)
- Size: 913,000 records
- Stores: 10
- Items: 50
- Period: January 2013 to December 2017 (daily)
- Columns: date, store, item, sales

---

## Project Structure

| Step | Description |
|------|-------------|
| 1 | Environment setup and data loading via Kaggle API |
| 2 | Exploratory Data Analysis |
| 3 | Feature Engineering |
| 4 | Dynamic Pricing Simulation |
| 5 | Demand Forecasting Models |
| 6 | Model Evaluation and Comparison |
| 7 | Budget and Price Optimization |
| 8 | Project Summary |

---

## Models Used

- Linear Regression (baseline)
- Random Forest
- Gradient Boosting
- Prophet (Meta)

---

## Results

### Model Performance

| Model             | MAE    | RMSE   | R2     |
|-------------------|--------|--------|--------|
| Linear Regression | 6.8779 | 8.9676 | 0.9192 |
| Random Forest     | 6.4860 | 8.4750 | 0.9279 |
| Gradient Boosting | 6.2046 | 8.0602 | 0.9347 |
| Prophet           | 10.5694| 13.1083| 0.8102 |

### Pricing Simulation (Store 2, Item 15)

| Strategy        | Total Revenue  | vs Static |
|-----------------|----------------|-----------|
| Static Pricing  | 1,712,170 USD  | Baseline  |
| Myopic Pricing  | 1,663,544 USD  | -2.84%    |
| Dynamic Pricing | 1,652,951 USD  | -3.46%    |
| Optimal Pricing | 515,950 USD*   | +11.8%    |

*Applied to 2017 test period only

---

## Key Findings

- Gradient Boosting is the best model with R2 of 0.9347 on unseen 2017 data
- rolling_mean_7 and lag_7 account for 82% of predictive power
- Sunday is the peak sales day and July is the peak month every year
- Under elastic demand (PED = -1.5), variable pricing underperforms static pricing
- The optimal price of 8.00 USD generates 11.8% more revenue than static pricing
- A 10,000 USD marketing budget optimally allocated produces 998.85 units of total sales lift

---

## Tech Stack

- Python 3.12
- Google Colab
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn
- Prophet
- SciPy

---

## How to Run

1. Open the notebook in Google Colab
2. Upload your kaggle.json API token when prompted
3. Run all cells in order from top to bottom

---

## Author

Muhammad Fiaz

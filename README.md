
# Sentiment Signal: Financial News–Driven NASDAQ Forecast  
**By Or Ben Haim**  
_Last updated: July 2025_

## Project Overview

This project investigates whether financial news sentiment can help forecast short-term movements in the NASDAQ index. By collecting headlines from CNBC, Reuters, and The Guardian, and applying pre-trained NLP models to score sentiment, the goal was to evaluate whether trends in news tone reflect or even anticipate market behavior.

Two forecasting models were implemented:
- A **Linear Regression** using sentiment as the sole explanatory variable
- A more advanced **SARIMAX** model that incorporates both past NASDAQ values and external sentiment as exogenous input

The models were evaluated based on their ability to predict NASDAQ movements from **December 2017 to July 2020**, and then forecasted the index for **August–October 2020**, using bootstrapped confidence intervals to express uncertainty.

---

## Repository Contents

| File | Description |
|------|-------------|
| `Sentiment Signal Financial News Driven NASDAQ Forecast Project By Or Ben Haim.ipynb` | Main Jupyter notebook with full code, analysis, modeling, and visualizations |
| `Sentiment Signal Financial News Driven NASDAQ Forecast Project By Or Ben Haim.pdf` | Clean PDF version of the report (suitable for sharing or reviewing offline) |
| `non_synthetic_with_nasdaq_final.csv` | Preprocessed dataset of monthly sentiment scores and corresponding NASDAQ index values |

---

## Key Results

- **SARIMAX outperformed** the linear model across all metrics:  
  - RMSE dropped from ~819 to ~433  
  - R² increased from 0.09 to 0.74  
  - The Paired T-Test showed statistically significant improvement (p = 0.0060)
- The model correctly identified **historical market shifts** corresponding to changes in news sentiment
- Forecasts included **confidence intervals** based on 1,000 bootstrap resamples

---

## 🤖 Tools & Technologies

- `transformers` (Hugging Face) – for sentiment scoring using BERT/GPT models  
- `yfinance` – for fetching historical NASDAQ data  
- `pandas`, `numpy`, `matplotlib`, `scikit-learn`, `statsmodels` – for data analysis, modeling, and visualization

---

## Reflections & Limitations

- Lightweight models (e.g., GPT‑2) were used for text augmentation and sentiment scoring. Using more advanced, domain-specific models like **FinBERT** or **GPT‑4** may yield more accurate sentiment extraction.
- The forecasting relied only on sentiment scores. Incorporating **macroeconomic indicators** (e.g., interest rates, inflation, VIX) could enhance performance.
- Despite limitations, this project serves as a successful **proof of concept** that shows sentiment can carry explanatory power when modeled properly.

---

## How to Run

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt

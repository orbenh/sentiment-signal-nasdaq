---

##  **Sentiment Signal: Financial News–Driven NASDAQ Forecast**

## 📓 Notebook

[ View Full Notebook](notebooks/sentiment_signal_nasdaq.ipynb)

[View Full Report (PDF)](reports/sentiment_signal_nasdaq.pdf)

---

###   Project Overview

This project investigates whether shifts in the tone of financial news correspond with changes in the NASDAQ index. By aggregating monthly sentiment scores from real-world headlines (CNBC, Reuters, and The Guardian), and aligning them with historical NASDAQ averages, the project explores how media sentiment relates to market behavior.

Sentiment analysis was performed using pre trained models from Hugging Face  combining **GPT-2** (for generating missing text summaries) and **BERT-based models** (for scoring sentiment on a 2–10 scale). The resulting sentiment scores were aggregated monthly and used to build predictive models for the NASDAQ.

---

###   Models Used

####  NLP Models (Hugging Face)

* **GPT‑2**  used to generate brief textual descriptions for headlines missing context.
* **BERT (base-uncased)**  applied to headline + description pairs to classify sentiment scores on a 1–10 scale.

> Note: These models were not fine-tuned on financial texts. Accuracy may improve with FinBERT or domain-specific large language models.

####  Predictive Models

* **Linear Regression**: A baseline model mapping sentiment scores to NASDAQ averages.
* **SARIMAX**: A time series model that incorporates both past NASDAQ trends and external sentiment signals.

---

###  Forecast Results

Two models were compared using historical data from **December 2017 through July 2020**:

| Metric | Linear Regression | SARIMAX |
| ------ | ----------------- | ------- |
| RMSE   | 818.80            | 432.77  |
| MAE    | 621.44            | 339.86  |
| R²     | 0.092             | 0.741   |

A **paired t-test** on prediction errors confirmed SARIMAX's statistical superiority (*p = 0.006*).

---

###  Key Insights

* SARIMAX outperformed linear regression by accounting for both **internal market dynamics** and **external sentiment shifts**.
* The model successfully captured **real historical turning points**, demonstrating the explanatory power of sentiment trends.
* Using more advanced or fine-tuned NLP models (e.g., **FinBERT**, **GPT‑4**, or custom transformers) could further improve sentiment precision.
* Expanding the feature set to include **macroeconomic indicators** (interest rates, inflation, earnings) is a logical next step.

---

###  Repository Contents

```bash
├── Sentiment Signal Financial News Driven NASDAQ Forecast Project By Or Ben Haim.ipynb
├── Sentiment Signal Financial News Driven NASDAQ Forecast Project By Or Ben Haim.pdf
├── requirements.txt
├── README.md  ← You are here
└── data/
    └── non_synthetic_with_nasdaq_final.csv
```

---

### Requirements

Install all dependencies using:

```bash
pip install -r requirements.txt
```

---

### Credits

Project by **Or Ben Haim**
Sentiment models via **Hugging Face Transformers**
Market data from [Yahoo Finance](https://finance.yahoo.com/) via `yfinance`
News data sourced from [Kaggle](https://www.kaggle.com/datasets/notlucasp/financial-news-headlines)

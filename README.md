

## **Sentiment Signal: Financial News–Driven NASDAQ Forecast**

###  [ View Full Report (PDF)](./Sentiment%20Signal%20Financial%20News%20Driven%20NASDAQ%20Forecast%20Project%20By%20Or%20Ben%20Haim.pdf)

###  [ Open Jupyter Notebook](./Sentiment%20Signal%20Financial%20News%20Driven%20NASDAQ%20Forecast%20Project%20By%20Or%20Ben%20Haim.ipynb)

---

###  Project Overview

This project investigates whether shifts in the tone of financial news correspond with changes in the NASDAQ index. By aggregating monthly sentiment scores from real-world headlines (CNBC, Reuters, and The Guardian), and aligning them with historical NASDAQ averages, the project explores how media sentiment relates to market behavior.

Sentiment analysis was performed using pretrained Hugging Face models (including GPT-2 and BERT variants). The resulting sentiment scores were aggregated monthly and used to build predictive models for the NASDAQ.

---

###  Models Used

* **Linear Regression**: A basic benchmark model that establishes a direct relationship between sentiment and index movement.
* **SARIMAX**: A more advanced time-series model that captures both temporal momentum and external sentiment signals.

---

### 📈 Forecast Results

Two models were compared using historical data from December 2017 through July 2020:

| Metric | Linear Regression | SARIMAX |
| ------ | ----------------- | ------- |
| RMSE   | 818.80            | 432.77  |
| MAE    | 621.44            | 339.86  |
| R²     | 0.092             | 0.741   |

A **paired t-test** on prediction errors confirmed SARIMAX's statistical superiority (*p = 0.006*).

---

###  Key Insights

* **SARIMAX significantly outperformed** linear regression by incorporating time dynamics and reacting more sensitively to sentiment shifts.
* The model successfully **captured real historical market turning points**, demonstrating the potential explanatory power of sentiment signals.
* **Limitations** included the use of non-finetuned NLP models (GPT-2, base BERT), and **lack of macroeconomic variables** like interest rates, inflation, or earnings.
* Future improvements could include **FinBERT**, **GPT-4**, or models fine-tuned on financial corpora, as well as incorporation of broader economic indicators.

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

###  Requirements

Install all dependencies using:

```bash
pip install -r requirements.txt
```

---

###  Credits

Project by **Or Ben Haim**
Sentiment scoring powered by Hugging Face Transformers
Market data from [Yahoo Finance](https://finance.yahoo.com/) via `yfinance`
News data sourced from [Kaggle](https://www.kaggle.com/datasets/notlucasp/financial-news-headlines)

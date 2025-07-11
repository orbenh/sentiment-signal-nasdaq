# Sentiment Signal: Financial News–Driven NASDAQ Forecast

This project explores how financial news sentiment aligns with movements in the NASDAQ index. By analyzing headlines from **CNBC**, **Reuters**, and **The Guardian**, we assess whether shifts in language can anticipate market trends.

To complete this analysis, we:
- Collected and cleaned news headlines
- Used **GPT-2** to generate missing descriptions
- Applied **BERT-based sentiment models** from Hugging Face to assign sentiment scores (on a 2–10 scale)
- Aggregated sentiment monthly and compared with average NASDAQ values

We then trained two forecasting models:
-  A simple **linear regression**
-  A **SARIMAX** time series model (including sentiment as an external regressor)

---

## Repository Contents

| Folder/File     | Description |
|------------------|-------------|
| `data/`         | Cleaned sentiment + NASDAQ CSVs |
| `notebooks/`    | Full Jupyter Notebook (analysis + modeling) |
| `reports/`      | Final report (PDF export of the notebook) |
| `requirements.txt` | All Python dependencies used |

---

## 🔗 View the Project

-  Notebook: [`notebooks/Sentiment%20Signal%20Financial%20News%20Driven%20NASDAQ%20Forecast%20Project%20By%20Or%20Ben%20Haim%20(1).ipynb`](notebooks/Sentiment%20Signal%20Financial%20News%20Driven%20NASDAQ%20Forecast%20Project%20By%20Or%20Ben%20Haim%20(1).ipynb)
- Report (PDF): [`reports/Sentiment%20Signal%20Financial%20News%20Driven%20NASDAQ%20Forecast%20Project%20By%20Or%20Ben%20Haim.pdf`](reports/Sentiment%20Signal%20Financial%20News%20Driven%20NASDAQ%20Forecast%20Project%20By%20Or%20Ben%20Haim.pdf)

---

##  NLP and LLM Models Used

-  **GPT-2** (via Hugging Face) — to generate summaries for headlines missing descriptions
-  **BERT (Sentiment Analysis variant)** — to score sentiment on combined headline + summary pairs

These models were applied using the Hugging Face `transformers` pipeline.

---

##  Technologies

- Python, Pandas, Matplotlib
- Hugging Face Transformers (GPT-2, BERT)
- `statsmodels` for SARIMAX
- `ruptures` for structural break detection
- `yfinance` for stock data

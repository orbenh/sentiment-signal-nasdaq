# sentiment-signal-nasdaq
## Sentiment Signal: Financial News–Driven NASDAQ Forecast

This project investigates how shifts in financial news sentiment sourced from CNBC, Reuters, and The Guardian align with movements in the NASDAQ index. Using NLP tools, GPT-2–based augmentation, and time-series analysis, we demonstrate how media tone can both reflect and forecast market behavior.
[Download the Full PDF Report](reports/Sentiment%20Signal%20Financial%20News%20Driven%20NASDAQ%20Forecast%20Project%20By%20Or%20Ben%20Haim.pdf)


---

##  Objectives

- Analyze sentiment in ~143K financial headlines (2017–2020)
- Augment missing descriptions using GPT-2 generation
- Score headline sentiment using a BERT-based model
- Aggregate sentiment monthly per source and overall
- Merge sentiment trends with NASDAQ index data
- Detect structural breaks in news tone and price
- Build a regression model to forecast market trends

---

##  Highlights

- Detected structural breaks during:
  - US–China Trade War (late 2019)
  - COVID-19 market crash (early 2020)
- GPT-2 augmentation preserved tone but introduced mild noise
- Non-synthetic sentiment had **stronger correlation** with NASDAQ  
  _(Pearson r ≈ –0.31)_
- Simple linear regression predicted NASDAQ movements  
  3 months ahead with bootstrapped confidence intervals

---

## Dataset Summary

This project processes a total of **142,756 records** across all stages:

- 3,080 CNBC headlines  
- 32,770 Reuters headlines  
- 17,800 Guardian headlines  
- 17,800 GPT-2 generated descriptions for Guardian  
- 71,170 fully processed and sentiment-scored records  
- 34 monthly sentiment points (mixed)
- 34 monthly sentiment points (non-synthetic)
- 34 rows: sentiment + NASDAQ (mixed)
- 34 rows: sentiment + NASDAQ (non-synthetic)

---

## Tools & Stack

- **Hugging Face Transformers**:  
  `nlptown/bert-base-multilingual-uncased-sentiment`, `gpt2`
- **Datasets**:  
  [Kaggle Financial News](https://www.kaggle.com/datasets/notlucasp/financial-news-headlines),  
  NASDAQ via `yfinance`
- **Libraries**:  
  `pandas`, `matplotlib`, `ruptures`, `scikit-learn`, `torch`, `datasets`

---

##  Repository Structure

```bash
notebooks/
├── SentimentSignal_Final.ipynb       # End-to-end pipeline notebook

reports/
├── SentimentSignal_Report.pdf        # Business-style project summary

data/
├── cnbc_headlines.csv
├── reuters_headlines.csv
├── guardian_headlines.csv
├── guardian_with_descriptions_gpt2.csv
├── news_all_sources_sentiment_mixed.csv
├── monthly_sentiment_mixed.csv
├── monthly_sentiment_non_synthetic.csv
├── mixed_with_nasdaq_final.csv
├── non_synthetic_with_nasdaq_final.csv

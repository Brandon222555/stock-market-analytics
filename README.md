# Stock Market Analytics & ML Prediction System

![Python](https://img.shields.io/badge/Python-3.8+-blue?logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-ML-orange?logo=scikit-learn&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-Database-lightgrey?logo=sqlite)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

> End-to-end stock market analytics and ML prediction system. Simulates 3 years of OHLCV price data, engineers 16 technical indicators, and benchmarks 4 classification models using time-series cross-validation.

---

## What This Project Does

Most stock ML tutorials make a critical mistake: they train on future data (look-ahead bias), producing fake results that would fail in production. This project fixes that by applying **time-series cross-validation** — the same technique used by professional quant teams — to ensure every model is only ever tested on data it couldn't have seen.

Built as a full analytics system with a structured SQL backend, feature engineering pipeline, model benchmarking suite, and publication-quality visualizations.

---

## Key Results

| Model | AUC-ROC | Notes |
|---|---|---|
| Gradient Boosting | Best | Strongest on RSI + volatility features |
| Random Forest | Strong | Most stable across folds |
| Logistic Regression | Baseline | Fast, interpretable |
| SVM | Competitive | Best on normalized feature sets |

- **16 technical indicators** engineered as ML features
- **3 years** of daily OHLCV data across 5 tickers (AAPL, MSFT, GOOGL, AMZN, TSLA)
- **10 publication-quality charts** including candlesticks, ROC curves, confusion matrices, feature importances

---

## Technical Highlights

**Data Generation**
- Simulated realistic price data using **Geometric Brownian Motion** — the standard stochastic model in quantitative finance (Black-Scholes pricing model)
- Configurable volatility and drift parameters per ticker

**Feature Engineering (16 indicators)**
- Momentum: RSI, MACD, MACD Signal
- Trend: EMA (10, 20, 50-day), Bollinger Bands (upper/lower/width)
- Volatility: Rolling 20-day volatility, Average True Range
- Volume: Volume ratio, On-Balance Volume
- Price action: Daily return, High-Low range

**ML Pipeline**
- Time-series cross-validation (no shuffle — respects temporal order)
- Standardization scoped to training folds only (no data leakage)
- Hyperparameter grid search within each fold

**Data Layer**
- SQLite schema with normalized tables and pre-built analytical views
- Fast querying without re-processing raw data

---

## Tech Stack

```
Python 3.8+     — core language
Pandas / NumPy  — data processing
Scikit-Learn    — ML models, cross-validation, metrics
Matplotlib      — visualization
SQLite          — data storage and analytical views
```

---

## Project Structure

```
stock-market-analytics/
├── data/               # SQLite database + raw OHLCV CSVs
├── features/           # Technical indicator engineering
├── models/             # Training, CV, benchmarking
├── visualizations/     # Chart outputs (ROC, confusion matrix, etc.)
├── sql/                # Schema + analytical views
└── main.py             # End-to-end pipeline runner
```

---

## Why This Matters for Real-World DS Work

This project demonstrates skills directly relevant to production Data Scientist and Analytics Engineer roles:

- **No data leakage** — time-series CV mirrors real deployment constraints
- **SQL-backed analytics** — not just notebook outputs; queryable data layer
- **Business framing** — feature importances tell *why* the model works, not just that it does
- **Reproducible pipeline** — modular code, not a single spaghetti notebook

---

## Author

**Brandon Quansah** — Data Scientist | Physics B.S., Rowan University

[LinkedIn](https://linkedin.com/in/brandonquansah) · [GitHub](https://github.com/Brandon222555) · quansahb21@gmail.com

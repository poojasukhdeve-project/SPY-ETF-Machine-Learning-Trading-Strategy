# SPY ETF Machine Learning Trading Strategy

**Author:** Pooja Sukhdeve

---

## The Story Behind This Project

Like many people interested in Data Science and Finance, I often wondered:

> "If we have years of historical stock market data, can Machine Learning learn from the past and help us make better investment decisions?"

At first, the idea seemed simple: collect data → train a model → predict tomorrow → beat the market. But after building this project, I realized that financial markets are far more complex than they appear. This project was my attempt to explore that question using Python and machine learning.

---

## Objective

The goal was to build an end-to-end machine learning pipeline capable of analyzing historical SPY ETF data and generating predictions for the next trading day.

More importantly, I wanted to answer a practical question: **Can a machine learning strategy outperform a simple Buy & Hold investment?**

---

## My Approach

### Feature Engineering

Instead of using raw stock prices, I engineered several financial features that traders and analysts commonly use:

- Daily Returns
- 5-Day Returns
- 10-Day Returns
- Rolling Volatility
- Moving Averages (MA5, MA20, MA50)
- Moving Average Signals
- Volume Ratios
- Price-to-Moving-Average Ratios

These features were used to predict the next day's SPY return.

### Machine Learning Models

I implemented and compared three approaches:

**1. Linear Regression** — a simple baseline capturing linear relationships between market features and future returns.

**2. Random Forest Regressor** — an ensemble model designed to identify more complex, non-linear market patterns.

**3. Random Forest Classifier** — a classification model predicting whether the market would move up or down.

### Strategy Evaluation

Rather than stopping at prediction accuracy, I built a complete backtesting framework. Each model generated trading signals, evaluated using:

- Total Return
- Sharpe Ratio
- Positive Trading Days
- Equity Curves

Every strategy was then compared against a passive Buy & Hold benchmark.

---

## Final Results

| Strategy | Total Return | Sharpe Ratio | Positive Days |
|---|---|---|---|
| **Buy & Hold** | **24.99%** | **1.897** | **59.50%** |
| Random Forest Regressor | 8.60% | 0.737 | 50.41% |
| Linear Regression | 0.68% | 0.119 | 52.07% |
| Random Forest Classifier | 0.68% | 0.119 | 52.07% |

---

## Key Challenges & Solutions

### 1. Fairly comparing active strategies against Buy & Hold
**Problem:** A naive comparison risks being unfair in either direction — giving the ML strategies credit for information they wouldn't have had in real time, or penalizing them with unrealistic trade timing.
**Fix:** Standardized every strategy on the same evaluation window, the same starting capital, and signals generated strictly from information available before the trading day being predicted, so no strategy had a hidden timing advantage over Buy & Hold.
**Takeaway:** A backtest is only meaningful if every strategy, including the passive benchmark, is held to the same rules — otherwise "beating Buy & Hold" doesn't actually mean anything.

### 2. Identical results from Random Forest Classifier and Linear Regression
**Problem:** The Random Forest Classifier and Linear Regression strategies produced exactly matching metrics (0.68% return, 0.119 Sharpe, 52.07% positive days) — a result too precise to be coincidence, and worth investigating rather than reporting at face value.
**Investigation:** This pattern points to the two models converging on the same sequence of buy/sell decisions during backtesting — most likely because the classifier's predicted direction and the regression's predicted sign agreed on every test day, which would make their resulting trade sequences (and therefore their backtest metrics) identical even though the underlying models are different.
**Takeaway:** Suspiciously clean overlaps in results are worth chasing down, not just reporting — a real difference in model type should generally show up as at least some difference in outcome, and understanding when and why it doesn't is itself useful diagnostic information about how the signals were generated.

---

## What I Learned

When I started this project, I thought the goal was to build a model that could beat the market. By the end, I realized the real value was understanding how difficult that challenge actually is.

The Random Forest Regressor became the strongest machine learning model, but the simple Buy & Hold strategy still outperformed every active trading strategy. That result taught me one of the most important lessons in quantitative finance:

> A model should not only make predictions — it should be evaluated against realistic benchmarks to determine whether it actually creates value.

---

## Technologies Used

Python • Pandas • NumPy • Scikit-Learn • Matplotlib • Google Colab • GitHub

---

## Future Improvements

- Walk-Forward Validation
- Hyperparameter Optimization
- Transaction Cost Modeling
- XGBoost / LightGBM Models
- Real-Time Prediction Dashboard
- Portfolio Optimization

---

## Final Thoughts

This project strengthened my understanding of Data Science, Machine Learning, Feature Engineering, Financial Data Analysis, Quantitative Trading, and Strategy Backtesting.

More importantly, it reinforced a lesson that applies far beyond finance:

> Good Data Science isn't about proving that a model works. It's about honestly testing ideas, learning from the results, and letting the data challenge your assumptions.

If you have suggestions or ideas for improving this project, I'd love to connect and discuss them.

# 📈 SPY ETF Machine Learning Trading Strategy

## The Story Behind This Project

As an aspiring Data Scientist and Machine Learning Engineer, I wanted to answer a simple but challenging question:

> Can machine learning help predict tomorrow's stock market movement?

To explore this question, I built a complete quantitative trading pipeline using historical data from the SPY ETF (S&P 500 ETF), one of the most widely traded market indices in the world.

Instead of jumping directly into advanced models, I followed the same process used by professional quantitative analysts:

1. Collect and understand financial data.
2. Engineer meaningful market features.
3. Evaluate statistical relationships.
4. Build predictive machine learning models.
5. Backtest trading strategies.
6. Compare performance across multiple models.

This project documents that entire journey.

---

# 🎯 Project Goal

The objective of this project is to predict the next day's SPY return and evaluate whether machine learning models can generate profitable trading signals.

The final goal is not only prediction accuracy but also:

* Strategy profitability
* Risk-adjusted returns
* Trading performance
* Model interpretability

---

# 📊 Dataset

Historical SPY ETF market data from:

* Open Price
* High Price
* Low Price
* Close Price
* Volume

Period:

* January 2020 – December 2024

Total observations:

* 1,258 trading days

---

# 🔍 Exploratory Data Analysis

The project begins with an extensive exploration of SPY market behavior.

Key analyses include:

* Dataset inspection
* Missing value analysis
* Statistical summaries
* Closing price trends
* Daily return distributions
* Rolling volatility analysis

### Key Finding

The SPY ETF showed strong long-term growth but experienced periods of significant volatility, particularly during market stress events.

---

# ⚙️ Feature Engineering

To capture market behavior, several predictive features were created.

### Return Features

* Return_1D
* Return_5D
* Return_10D

### Volatility Features

* Volatility_5D
* Volatility_20D

### Trend Features

* MA5
* MA20
* MA50
* MA_Signal

### Volume Features

* Volume_Avg_20
* Volume_Ratio

### Relative Price Features

* Price_MA20_Ratio

### Target Variable

* Tomorrow_Return

---

# 📈 Statistical Analysis

A correlation study was performed to understand how features relate to future returns.

### Observation

Most engineered features showed very weak correlation with tomorrow's return.

This highlights an important reality of financial markets:

> Future price movements are extremely difficult to predict.

---

# 🤖 Machine Learning Models

Three machine learning approaches were implemented and evaluated.

## 1. Linear Regression

A baseline predictive model used to estimate future returns.

### Results

* MSE: 0.000068
* R²: -0.066
* Total Return: 2.43%
* Sharpe Ratio: 0.260

---

## 2. Random Forest Regressor

A non-linear ensemble learning model capable of capturing complex market relationships.

### Results

* MSE: 0.000069
* R²: -0.086
* Total Return: 6.44%
* Sharpe Ratio: 0.573

### Key Insight

Although prediction accuracy remained difficult, the trading strategy generated the highest risk-adjusted return.

---

## 3. Random Forest Classifier

A classification model predicting market direction:

* Up Market → 1
* Down Market → 0

### Results

* Accuracy: 52.07%
* Total Return: 1.88%
* Sharpe Ratio: 0.216

### Key Insight

The model slightly outperformed random guessing but produced weaker trading performance than regression-based approaches.

---

# 🏆 Final Model Ranking

## 🥇 Random Forest Regressor

* Highest Total Return (6.44%)
* Highest Sharpe Ratio (0.573)
* Best overall trading performance

## 🥈 Linear Regression

* Total Return: 2.43%
* Sharpe Ratio: 0.260
* Simpler and more interpretable model

## 🥉 Random Forest Classifier

* Accuracy: 52.07%
* Total Return: 1.88%
* Lowest risk-adjusted performance

---

# 📉 Key Lessons Learned

This project reinforced several important lessons about quantitative finance:

### 1. Financial markets are difficult to predict

Even sophisticated features often have weak predictive power.

### 2. Accuracy is not everything

A model with lower prediction accuracy can still generate better trading returns.

### 3. Feature engineering matters

Market returns, volatility, moving averages, and volume signals provide valuable information for machine learning models.

### 4. Backtesting is essential

Evaluating a model through trading performance provides more practical insight than prediction metrics alone.

---

# 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-Learn
* Google Colab

---

# 🚀 Future Improvements

Potential enhancements include:

* XGBoost Regressor
* LightGBM
* LSTM Deep Learning Models
* Hyperparameter Optimization
* Walk-Forward Validation
* Portfolio Optimization
* Multi-Asset Trading Strategies

---

# 👩‍💻 Author

**Pooja Sukhdeve**

Master of Science in Computer Science
Boston University Metropolitan College

Interested in:

* Machine Learning
* Data Science
* Quantitative Finance
* Software Development

---

*"The goal was never to perfectly predict the market. The goal was to understand it better through data, statistics, and machine learning."*

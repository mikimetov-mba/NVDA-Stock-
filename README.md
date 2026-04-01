# 📈 NVDA Stock Trading Signal — ML Classifier

A machine learning project that predicts next-day **BUY / SELL signals** for NVIDIA (NVDA) stock using technical indicators and Logistic Regression.

---

## 🧠 What This Project Does

This project downloads 4 years of NVIDIA historical stock data (2021–2024), engineers technical indicators, labels each day as a BUY (`1`) or SELL (`-1`) signal based on next-day price movement, and trains a Logistic Regression classifier to predict those signals.

---

## 🗂️ Project Structure

```
nvda-trading-signal/
│
├── nvda_trading_signal.ipynb   # Main Jupyter notebook
├── requirements.txt            # Python dependencies
└── README.md                   # Project documentation
```

---

## ⚙️ Features Used (X)

| Feature | Description |
|--------|-------------|
| `mo50` | 50-day Simple Moving Average of Adj Close |
| `mo100` | 100-day Simple Moving Average of Adj Close |
| `std5` | 5-day Rolling Standard Deviation (short-term volatility) |
| `std20` | 10-day Rolling Standard Deviation (medium-term volatility) |

---

## 🎯 Target Variable (y)

```python
signal = 1   # Tomorrow's price > Today's price → BUY
signal = -1  # Tomorrow's price < Today's price → SELL
```

---

## 🔁 Pipeline Overview

```
Download NVDA Data (yfinance)
        ↓
Calculate Technical Indicators (pandas_ta)
        ↓
Create Signal Labels (numpy)
        ↓
Drop NaN rows → Split X and y
        ↓
Train/Test Split (80% / 20%)
        ↓
Train Logistic Regression (sklearn)
        ↓
Evaluate Accuracy
```

---

## 📊 Results

| Metric | Value |
|--------|-------|
| Model | Logistic Regression |
| Test Accuracy | **53.59%** |
| Baseline (random) | 50.00% |
| Test Period | ~April 2024 – Dec 2024 |

> ⚠️ The model shows a slight edge over random guessing. Future improvements can push this higher — see [Improvements](#-future-improvements) below.

---

## 🚀 Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/your-username/nvda-trading-signal.git
cd nvda-trading-signal
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the notebook

```bash
jupyter notebook nvda_trading_signal.ipynb
```

---

## 📦 Requirements

```
numpy
pandas
yfinance
matplotlib
seaborn
pandas_ta
scikit-learn
jupyter
```

Install all at once:

```bash
pip install numpy pandas yfinance matplotlib seaborn pandas_ta scikit-learn jupyter
```

## ⚠️ Disclaimer

> This project is for **educational purposes only**. It is not financial advice. Do not use this model for real trading decisions without proper risk management and further validation.

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 🙋 Author

Built as a learning project exploring the intersection of **quantitative finance** and **machine learning**.

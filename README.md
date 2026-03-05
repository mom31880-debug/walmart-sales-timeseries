# 🛒 Walmart Sales Time Series Analysis

A comprehensive time series analysis of Walmart retail sales data using Python, covering data cleaning, exploratory data analysis, decomposition, and forecasting.

---

## 📊 Dataset

**Source:** [Walmart Store Sales Forecasting - Kaggle](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting)

The dataset consists of 3 files:

| File | Description |
|------|-------------|
| `train.csv` | Weekly sales data for 45 stores and 81 departments (2010–2012) |
| `stores.csv` | Store type (A/B/C) and size |
| `features.csv` | External factors: Temperature, Fuel Price, CPI, Unemployment, Markdowns |

---

## 🎯 Project Goals

- Understand the sales patterns and trends over time
- Identify the impact of holidays on sales
- Decompose the time series into Trend, Seasonality, and Residual
- Build and compare forecasting models to predict future sales

---

## 🔧 Tools & Libraries

- **Python 3**
- **Pandas** — data manipulation
- **NumPy** — numerical operations
- **Matplotlib** — data visualization
- **Seaborn** — statistical plots

---

## 📁 Project Structure

```
walmart-sales-timeseries/
│
├── train.csv
├── stores.csv
├── features.csv
│
└── walmart_analysis.ipynb
```

---

## 🚀 Steps

### 1. Data Loading & Cleaning
- Loaded and merged all 3 CSV files
- Fixed duplicate `IsHoliday` column after merge
- Filled missing MarkDown values with 0 (no promotions)
- Converted `Date` column to datetime format

### 2. Exploratory Data Analysis (EDA)
- Visualized total weekly sales over time
- Compared Holiday vs Non-Holiday average sales
- Analyzed performance by Store and Department
- Explored the effect of Store Type and Size on sales

### 3. Time Series Decomposition
Manually decomposed the time series into 3 components using Rolling Mean:
- **Trend** — overall direction of sales
- **Seasonality** — repeating patterns (holiday spikes)
- **Residual** — unexplained noise

### 4. Forecasting
Split data into **80% Train / 20% Test** and built 3 models:

| Model | Description |
|-------|-------------|
| **SMA** | Simple Moving Average — equal weights for all weeks |
| **WMA** | Weighted Moving Average — recent weeks have higher weight |
| **EMA** | Exponential Moving Average — weights decay exponentially |

---

## 📈 Results

| Model | MAE | MAPE | Accuracy |
|-------|-----|------|----------|
| SMA | $1,591,869 | 3.44% | 96.56% |
| WMA | $1,654,907 | 3.57% | 96.43% |
| **EMA** | **$1,541,240** | **3.32%** | **96.68%** ✅ |

**EMA achieved the best performance** with only 3.32% average error.

---

## 💡 Key Insights

- **Holiday weeks** generate ~7% higher sales than non-holiday weeks
- **Black Friday (November)** is the highest sales week of the year
- **4th of July** causes a notable spike in summer sales
- **Store Type A** outperforms Type B and C by up to 2x
- **Larger stores** consistently generate higher weekly sales
- **Department 92** is the top-performing department overall
- Sales show a clear **upward trend** from 2010 to 2012


---

## 👤 Mohamed ashraf

Feel free to reach out or contribute to this project!

# 📈 IHSG Weekly Forecasting with GRU & BiGRU (2004–2023)

Forecasting the **Indonesia Stock Exchange Composite Index (IHSG)** weekly closing prices using deep learning models — **GRU** and **Bidirectional GRU (BiGRU)**. The project evaluates both models and visualizes their predictive performance over nearly two decades of financial data.

---

## 📚 Table of Contents

- [Dataset](#dataset)
- [Models Used](#models-used)
- [Preprocessing Steps](#preprocessing-steps)
- [Results & Evaluation](#results--evaluation)
- [Key Takeaways](#key-takeaways)

---

## 📂 Dataset

- **Data**: Weekly IHSG closing prices from **2004 to 2023**
- **Features**:
  - `Date`: Weekly timestamps
  - `Harga`: IHSG closing price (target variable)
- **Source**: [Yahoo Finance](https://finance.yahoo.com/)
- **Frequency**: Weekly
- **Size**: ~1,000+ time points

---

## 🧠 Models Used

### GRU
- Gated Recurrent Unit: Efficient RNN variant for time series modeling

### BiGRU
- Bidirectional GRU: Captures forward and backward temporal relationships

**Model settings**:
- Lookback window: 5 weeks
- Optimizer: Adam (`lr=0.00005`)
- Loss: Huber loss
- Regularization: L1L2
- Callbacks: EarlyStopping & ModelCheckpoint

---

## 🔧 Preprocessing Steps

- Convert `Date` to datetime format
- Linear interpolation for missing price values
- Normalize using custom z-score method
- Create training & validation sets (70:30 split)
- Sequence generation using sliding window

---

## 📊 Results & Evaluation

- Metrics used:
  - **MAE**: Mean Absolute Error
  - **RMSE**: Root Mean Squared Error
  - **MAPE**: Mean Absolute Percentage Error
- Visualized prediction vs actual values on both train and validation data

---

## 📌 Key Takeaways

- **BiGRU** slightly outperforms **GRU** in terms of capturing trends and reducing prediction error
- GRU remains a faster, lighter model suitable for smaller devices
- Temporal modeling of IHSG with deep learning is feasible with weekly resolution data


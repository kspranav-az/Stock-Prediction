# 📈 Apple Stock Price Prediction using ARIMA and LSTM

This project focuses on **predicting Apple Inc. (AAPL) stock prices** using both traditional statistical methods (ARIMA) and deep learning (LSTM). It provides a comprehensive analysis of stock data from 2010 to 2020, covering data preprocessing, exploratory data analysis, stationarity testing, model training, evaluation, and forecasting.

---

## 🗂️ Project Structure

1. **Data Collection**
2. **Data Preprocessing**
3. **Exploratory Data Analysis**
4. **Stationarity Testing**
5. **ARIMA Modeling**
6. **LSTM Neural Network Modeling**
7. **Model Evaluation**
8. **Visualization of Results**

---

## 🛠️ 1. Data Collection

The project uses the `yfinance` API to fetch historical stock price data for Apple Inc. from **2010-01-01 to 2020-01-01**. The relevant columns (`Open`, `Close`, `High`, `Low`, `Volume`, and `Adj Close`) are selected for further analysis.

---

## 🧹 2. Data Preprocessing

- Missing values are interpolated linearly to ensure continuous time series.
- The data is saved to CSV files for consistency and reusability.
- The index is set to `Date` to ensure time-series compatibility.

---

## 📊 3. Exploratory Data Analysis (EDA)

- **Line Plot** of closing prices over time gives a sense of trends and volatility.
- **Correlation Heatmap** helps understand inter-feature relationships.

---

## 📉 4. Stationarity Testing

Using:
- **Rolling Mean and Standard Deviation**
- **Augmented Dickey-Fuller Test (ADF)**

Stationarity is crucial for time series modeling; the series was tested and found to be **non-stationary**, so differencing was applied to make it stationary.

---

## 📈 5. ARIMA Modeling

- **ACF and PACF plots** are used to determine p, d, and q parameters.
- **ndiffs** function confirms the differencing order `d=1`.
- Optimal parameters found:
  - `p = 10`, `d = 1`, `q = 3`
- The ARIMA model is trained iteratively to forecast future closing prices.
- **Forecasted values** are compared against actual test data using metrics:
  - **RMSE**
  - **MAE**
  - **R² Score**

---

## 🤖 6. LSTM Neural Network Modeling

- Data is scaled using **MinMaxScaler**.
- Time-series windowing is applied with 30-day lookback periods.
- An LSTM architecture with multiple layers and dropout regularization is used:
  - LSTM → Dropout → LSTM → ... → Dense
- The model predicts the next closing price from past values.
- Hyperparameters such as `units`, `dropout_rate`, and `optimizer` are set for flexibility.

---

## 📏 7. Model Evaluation

Both ARIMA and LSTM models are evaluated on unseen test data using:
- **Root Mean Squared Error (RMSE)**
- **Mean Absolute Error (MAE)**
- **R² Score**

These metrics help quantify how well the models predict the actual prices.

---

## 📉 8. Results Visualization

- Comparison plots between **actual vs predicted values** are generated for both ARIMA and LSTM models.
- Visualizations show the predictive power and limitations of each method.

---

## 🔚 Conclusion

This project demonstrates:
- The importance of preprocessing and stationarity in time series analysis.
- How ARIMA, a classical statistical method, can be applied for stock price forecasting.
- How LSTM, a deep learning model, can capture temporal dependencies in financial time series.
- The power of combining both approaches to gain insights and improve prediction performance.

---

## 📦 Dependencies

- `yfinance`
- `pandas`, `numpy`
- `matplotlib`, `seaborn`
- `statsmodels`
- `pmdarima`
- `tensorflow`, `keras`
- `scikit-learn`

---

## 📁 Files

- `apple_stock_data.csv` — Raw stock data
- `apple_stock_data_filled.csv` — Preprocessed data
- `ARIMA_forecast.png` — ARIMA prediction plot
- `LSTM_forecast.png` — LSTM prediction plot

---

## 📌 Note

This project is intended for **educational and research purposes only**. Financial predictions from this model should not be used for trading or investment decisions without further robust validation.


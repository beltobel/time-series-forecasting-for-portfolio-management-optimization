# time-series-forecasting-for-portfolio-management-optimization

## Project Overview

This project performs preprocessing and exploratory data analysis (EDA) on historical financial data for three assets: Tesla (TSLA), Vanguard Total Bond Market ETF (BND), and SPDR S&P 500 ETF (SPY). The data spans from July 1, 2015, to July 31, 2025, sourced from Yahoo Finance using the yfinance library. The goal is to clean, analyze, and derive insights to prepare the data for time series modeling, such as ARIMA, by examining trends, volatility, stationarity, and risk metrics. A comprehensive report (Financial Data Analysis Report.md) summarizes the findings, including a brief background on each asset.

## Repository Structure

├── data/ <br>
│ ├── adj_close_prices.csv # Cleaned adjusted closing prices <br>
│ └── volume_data.csv # Cleaned volume data <br>
├──notebooks <br>
  |
  |--preprocess_explore_data.ipynb # Jupyter notebook with preprocessing and EDA code <br>
  ├── rolling_volatility_plot.png # Plot of 21-day rolling annualized volatility <br>
  ├── Financial Data Analysis Report.md # Detailed analysis report <br>
  └── README.md # Project overview (this file) <br>

# Prerequisites

To run the code in this repository, ensure you have the following installed:

Python 3.13.1<br>
Required Python packages (listed in requirements.txt):<br>
yfinance<br>
pandas<br>
numpy<br>
matplotlib<br>
seaborn<br>
statsmodels<br>
scikit-learn<br>

**Install dependencies using:**
pip install -r requirements.txt

## Usage

**Clone the Repository:**
git clone time-series-forecasting-for-portfolio-management-optimization.git
cd financial-data-analysis

**Run the Jupyter Notebook**:Launch Jupyter Notebook and open preprocess_explore_data.ipynb:
jupyter notebook

Execute the cells sequentially to perform data preprocessing, EDA, and generate visualizations.

## Outputs:

**Data Files**: Cleaned data is saved in data/adj_close_prices.csv and data/volume_data.csv.
**Visualization**: The 21-day rolling annualized volatility plot is saved as rolling_volatility_plot.png.

## Methodology

### The analysis follows these steps:

**Data Acquisition:** Fetched historical data for TSLA, BND, and SPY using yfinance.
**Data Cleaning**: Checked for missing values, applied forward-fill, verified data types, and saved cleaned data.
**Normalization**: Scaled adjusted closing prices using MinMaxScaler for potential machine learning applications.
**EDA**:
Computed basic statistics to understand data distribution.<br>
Visualized closing prices and daily returns to identify trends and volatility.<br>
Analyzed 21-day rolling volatility and means.<br>
Detected outliers in daily returns (beyond 3 standard deviations).<br>
Performed Augmented Dickey-Fuller (ADF) tests to assess stationarity.<br>

**Risk Metrics**: Calculated Value at Risk (VaR) at 95% confidence and Sharpe Ratio (2% risk-free rate).
**Insights**: Summarized key findings, including TSLA’s high volatility, BND’s stability, and SPY’s balanced profile.

## Key Findings

**TSLA**: High volatility and strong risk-adjusted returns (Sharpe Ratio: 0.7446), with non-stationary <br>closing prices requiring differencing for ARIMA modeling.<br>
**BND**: Low volatility and stable returns (Sharpe Ratio: -0.0073), suitable for risk-averse strategies.<br>
**SPY**: Moderate volatility and balanced returns (Sharpe Ratio: 0.6844), reflecting diversified market exposure.<br>
**Stationarity**: Closing prices are non-stationary; daily returns are stationary, suitable for time series modeling.<br>
**Risk Metrics**: VaR highlights TSLA’s high risk (-5.47%), SPY’s moderate risk (-1.72%), and BND’s low risk (-0.49%).<br>

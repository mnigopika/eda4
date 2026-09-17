#  Shopify Stock Market Analysis

## 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)** on historical Shopify stock-market data.

The analysis uses Python with **Pandas** for data handling and **Matplotlib** for visualization. The notebook examines stock prices, trading volume, daily returns, price range, and moving averages.

## 🎯 Objectives

* Load and inspect Shopify historical stock data.
* Understand the structure and quality of the dataset.
* Check for missing values.
* Convert and prepare the date column for time-series analysis.
* Calculate daily price change, daily return percentage, and price range.
* Generate descriptive statistics.
* Measure mean return, return variance, and standard deviation.
* Visualize trading volume and price-related trends.
* Analyze daily-return distributions using histogram and KDE plots.
* Compare closing prices with 20-day and 50-day moving averages.

## 🛠️ Technologies Used

* **Python 3**
* **Pandas**
* **Matplotlib**
* **Google Colab / Jupyter Notebook**

## 📂 Dataset

The notebook reads a CSV file containing Shopify (`SHOP`) historical market data.

The dataset contains **2,469 rows and 7 columns** before feature engineering.

### Original Columns

|Column|Description|
|-|-|
|`date`|Trading date|
|`open`|Opening price|
|`high`|Highest price during the trading day|
|`low`|Lowest price during the trading day|
|`close`|Closing price|
|`adj\_close`|Adjusted closing price|
|`volume`|Trading volume|

According to the notebook, the original dataset has no missing values.

## 🔄 Data Preparation

The notebook performs the following preparation steps:

1. Loads the CSV using `pd.read\_csv()`.
2. Inspects the first few rows using `df.head()`.
3. Checks the dataset shape using `df.shape`.
4. Checks column types and non-null values using `df.info()`.
5. Checks missing values using `df.isnull().sum()`.
6. Converts the `date` column using `pd.to\_datetime()`.
7. Sorts the data by date.
8. Sets `date` as the DataFrame index.
9. Removes missing rows using `dropna()`.

After preparation, the notebook contains six main market-data columns plus calculated analytical features.

## 📊 Feature Engineering

Three additional features are calculated:

### 1\. Daily Price Change

```python
df\["Daily\_Price\_Change"] = df\["close"] - df\["open"]
```

This represents the difference between the closing and opening prices for a trading day.

### 2\. Daily Return (%)

```python
df\["Daily\_Return\_%"] = ((df\["close"] - df\["open"]) / df\["open"]) \* 100
```

This calculates the percentage change from the opening price to the closing price.

### 3\. Price Range

```python
df\["Price\_Range"] = df\["high"] - df\["low"]
```

This represents the difference between the day's highest and lowest prices.

## 📈 Descriptive Statistics

The notebook uses:

```python
df.describe()
```

The recorded statistics include:

* Mean
* Standard deviation
* Minimum
* 25th percentile
* Median
* 75th percentile
* Maximum

For the calculated daily return:

* **Mean Return:** approximately `0.0864%`
* **Return Variance:** approximately `9.7331`
* **Return Standard Deviation:** approximately `3.1198`

These values describe the distribution and variability of the daily opening-to-closing returns in the dataset.

## 📉 Visualizations

### Shopify Trading Volume Trend

The notebook plots trading volume over time to observe changes in market activity.

!\[Shopify Trading Volume Trend](readme\_assets/plot\_1.png)

### Daily Return Distribution

A histogram with 30 bins is used to visualize the distribution of daily returns.

!\[Shopify Daily Return Distribution](readme\_assets/plot\_2.png)

### Price Range Trend

The notebook visualizes the daily difference between the high and low prices.

!\[Shopify Price Range Trend](readme\_assets/plot\_3.png)

### Shopify OHLC Prices

The notebook compares the **Open, High, Low, and Close** prices over time.
<img width="985" height="465" alt="Screenshot 2026-09-17 201259" src="https://github.com/user-attachments/assets/938ee1ab-ea8e-4d41-9144-69ab455bb678" />


### Closing Price and Moving Averages

The notebook compares the daily closing price with **20-day and 50-day moving averages**.
<img width="995" height="481" alt="Screenshot 2026-09-17 201407" src="https://github.com/user-attachments/assets/7e52dc26-76da-4991-ab60-280716619b17" />



### KDE of Daily Returns

A Kernel Density Estimate (KDE) is used to show the smoothed distribution of daily returns.
<img width="844" height="462" alt="Screenshot 2026-09-17 201425" src="https://github.com/user-attachments/assets/3b819b4e-ba12-4178-bcf7-0c4e1b640776" />


## 🔍 Key Observations from the Notebook

* The dataset contains **2,469 trading records**.
* The original dataset has **7 columns**.
* No null values were reported in the original dataset.
* Shopify's stock prices show substantial variation across the analyzed period.
* Daily returns fluctuate around a small positive mean, with noticeable variability.
* Trading volume changes significantly over time.
* The notebook uses moving averages to provide a smoother view of closing-price trends.

## ▶️ How to Run

### Option 1 – Google Colab

1. Open `EDA\_Task\_3.ipynb` in Google Colab.
2. Upload the required Shopify CSV dataset.
3. Make sure the CSV filename/path matches the path used in the notebook.
4. Run the cells from top to bottom.

### Option 2 – Jupyter Notebook

Install the required libraries:

```bash
pip install pandas matplotlib
```

Then open the notebook:

```bash
jupyter notebook EDA\_Task\_3.ipynb
```

Run all cells in order.

## 📁 Project Structure

```text
EDA-Task-3/
│
├── EDA\_Task\_3.ipynb
├── README.md
└── readme\_assets/
    ├── plot\_1.png
    ├── plot\_2.png
    ├── plot\_3.png
    ├── plot\_4.png
    ├── plot\_5.png
    └── plot\_6.png
```

## 📌 Conclusion

This EDA project provides a basic statistical and visual analysis of Shopify historical stock data. It covers data inspection, cleaning, feature engineering, descriptive statistics, return analysis, trading-volume analysis, price-range analysis, and moving-average visualization.

The notebook can be used as a foundation for further financial-data analysis and visualization.


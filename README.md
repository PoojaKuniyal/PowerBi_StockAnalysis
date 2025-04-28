# 📊 Power BI Stock Market Dashboard

This project is a professional Power BI dashboard built using **real-time stock data** from **Alpha Vantage API**. It visualizes key stock market trends and performance indicators across multiple stocks.

---

## 🚀 How I Collected the Data

- **Source**: [Alpha Vantage API](https://www.alphavantage.co/)
- **Method**:  
  - Used API links for each stock (e.g., GOOGL, AAPL) with `TIME_SERIES_DAILY` function and `datatype=csv`.
  - Example URL format:  
    ```
    https://www.alphavantage.co/query?function=TIME_SERIES_DAILY&symbol=GOOGL&apikey=YOUR_API_KEY&datatype=csv
    ```
  - Connected the URLs into **Power BI** using **Web Connector** (Anonymous access).
- **Multi-Stock Setup**:
  - Imported **Google (GOOGL)** and **Apple (AAPL)** data separately.
  - **Appended queries** to create a combined table (**MultiStockData**) for multi-stock analysis.

---

## 🛠 Transformations and Calculations

- **Created Calculated Columns**:
  - **% Change**: Daily percent change to measure stock performance day-by-day.
  - **7-Day Moving Average**: Smooths daily fluctuations to show **weekly price trends**.
    - 🔎 Helps **spot trends** over a week instead of noisy daily changes.

- **Other Transformations**:
  - Renamed columns (e.g., 'timestamp' to 'date') and set correct data types.
  - Added **Stock Name** column manually to identify the stock in combined datasets.

---

## 📈 Visuals Used

| Visual | Purpose |
|:---|:---|
| **Slicer: Stock Name** | Filter dashboard by stock (AAPL/GOOGL). |
| **Slicer: Year** | Analyze data year-wise. |
| **Area Chart**: 7-Day Moving Average | See smoothed price trends over time. |
| **Line Chart**: Percent Change by Close and Stock Name | Compare stock performances fairly (% basis). |
| **Scatter Plot**: Sum of Close vs Sum of Volume by Date | Visualize trading activity in relation to stock prices. |
| **KPIs**: | Show important metrics like Minimum Closing Price, Maximum Closing Price, and Average Opening Price. |

---

## 📋 Features Highlight

- 📊 **Multi-Stock Comparison**: Quickly switch between different stocks using slicers.
- 🔎 **Trend Spotting**: Understand weekly behavior through 7-day moving averages.
- 🚀 **Performance Normalization**: See % growth/fall to compare high and low-priced stocks easily.
- 📅 **Time Filtering**: Slice data by year for historical performance analysis.

---

## ⚙️ How to Refresh the Data

1. Open the Power BI Dashboard.
2. Click **Home → Refresh** to pull the latest data from Alpha Vantage.
3. ⚡ Note: **Alpha Vantage free tier has API call limits** (5 API calls/minute, 500 calls/day).  
   Avoid refreshing too frequently.

---

## Important Notes

- You will need your **own Alpha Vantage API Key**. (It’s free to get.)
- Free tier API limits may restrict the number of refreshes per day.

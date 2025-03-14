# stock_market_powerbi_project


## 📊 Overview
This Power BI project provides insightful stock market analysis using interactive dashboards and visualizations. The dataset includes stock prices, volume, and key financial indicators to help users make informed investment decisions.

## 🚀 Features
- **Dynamic Visualizations**: Interactive charts and graphs for better understanding.
- **Real-time Data Refresh**: Keep stock prices up to date.
- **Key Performance Indicators (KPIs)**: Track stock trends with custom metrics.
- **Filtering & Slicing**: Customize data views based on company, time frame, and more.

## 📂 File Structure
```plaintext
📁 PowerBI-Stock-Analysis/
 ├── 📄 README.md
 ├── 📄 Stock Power BI.pbix
 ├── 📄 Data/ (Contains stock datasets)
 ├── 📄 Reports/ (Pre-generated Power BI reports)
 └── 📄 SQLQueries/ (Database queries for data processing)
```

## 🔍 Data Sources
The dataset is sourced from multiple APIs and CSV files containing:
- **Stock Prices** (Open, High, Low, Close, Adjusted Close, Volume)
- **Company Financials** (Revenue, Net Profit, Market Cap, P/E Ratio)
- **Historical Trends** (5-year, 10-year trends)

## 🛠️ Power BI Queries (M Code)
Below are some key M queries used in Power BI:

```PowerQuery
let
    Source = Csv.Document(File.Contents("C:\StockData\stocks.csv"), [Delimiter=",", Columns=6, Encoding=65001, QuoteStyle=QuoteStyle.None]),
    PromotedHeaders = Table.PromoteHeaders(Source, [PromoteAllScalars=true]),
    ChangedTypes = Table.TransformColumnTypes(PromotedHeaders,{{"Date", type date}, {"Open", type number}, {"Close", type number}, {"High", type number}, {"Low", type number}, {"Volume", type number}})
    in
    ChangedTypes
```

## 📊 SQL Queries for Data Processing
Below is an example SQL query used to fetch historical stock prices:

```sql
SELECT stock_symbol, trade_date, open_price, close_price, volume
FROM stock_market_data
WHERE trade_date BETWEEN '2022-01-01' AND '2023-12-31';
```

## 📌 How to Use
1. **Clone the Repository**:
   ```sh
   git clone https://github.com/yourusername/PowerBI-Stock-Analysis.git
   ```
2. **Open the .pbix file in Power BI Desktop**.
3. **Refresh the data sources** to get updated stock information.
4. **Explore the dashboards** and gain insights.




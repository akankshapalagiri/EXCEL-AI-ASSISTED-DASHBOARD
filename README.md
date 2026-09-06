# Sales Performance Dashboard

An interactive Excel analytics workbook designed to track, analyze, and visualize global sales, profitability, regional trends, and product category performance across multi-year transactional data.

## 📌 Features & KPIs

The workbook aggregates key operational metrics dynamically using Excel Pivot Tables and `GETPIVOTDATA` functions:

* **Total Sales:** Revenue generated across all product categories and regions ($5,297,958.31).
* **Total Profit:** Net earnings realized from sales transactions ($655,633.81).
* **Total Quantity Sold:** Cumulative volume of units distributed (5,954 units).
* **Average Discount:** Mean discount rate applied across orders (~14.68%).
* **Regional & Geographic Breakdown:** Regional and country-level sales distribution across Africa, Asia, Europe, North America, and South America.
* **Product Analytics:** Revenue and profitability performance parsed by top-level Product Categories (Clothing, Electronics, Furniture, Home Decor, Office Supplies) and individual Product Names.
* **Temporal Trends:** Monthly and yearly aggregated performance tracking from early 2023 through mid-2024.

## 📁 Workbook Architecture

The Excel file consists of three dedicated worksheets:

| Sheet Name | Description |
| :--- | :--- |
| **Dashboard** | The front-facing executive interface displaying top-level KPI cards and linked visual charts for reporting. |
| **Sales Data** | The underlying relational dataset containing individual transaction records and calculated date fields. |
| **Pivot_Data** | Back-end data modeling sheet containing Pivot Tables used to drive dashboard KPIs and chart visualizations. |

## 📊 Data Schema (Sales Data Sheet)

Each entry in the raw dataset represents a discrete customer order recorded with the following attributes:

* **Order ID:** Unique numeric identifier for the order (e.g., 10001).
* **Date:** Transaction date formatted as YYYY-MM-DD.
* **Region:** Target geographic region (Africa, Asia, Europe, North America, South America).
* **Country:** Specific market destination (e.g., India, Argentina, Germany, USA).
* **Product Category:** High-level classification (Clothing, Electronics, Furniture, Home Decor, Office Supplies).
* **Product Name:** Specific item sold (Wall Art, Jeans, Bookshelf, Pen Set, Smartphone, etc.).
* **Sales:** Total gross revenue for the item line (USD).
* **Quantity:** Number of units purchased.
* **Discount:** Fractional discount rate applied (e.g., 0.19 = 19%).
* **Profit:** Net profit generated from the line item (USD).
* **Month-Year:** Calculated date dimension generated via `=TEXT(B2, "yyyy-mmm")`.

## 🛠️ Data Refresh & Maintenance

1. **Adding New Transactions:** Append new rows to the bottom of the **Sales Data** sheet. Ensure the Month-Year formula in Column J is extended to cover new rows.
2. **Refreshing Dashboard KPIs:**
   * Navigate to the Excel ribbon.
   * Click **Data > Refresh All** (or press `Ctrl` + `Alt` + `F5`).
   * Verify that all Pivot Tables on the `Pivot_Data` sheet update automatically to include new transaction ranges.

# SALES DASHBOARD(POWER BI)
A POWER BI dashboard to analyze Sales performance across different regions, product categories and customer segments. It provides insights into revenue trends, profit margins and top-performing product to support data-driven decision making. 

---

# 📑 Table of Contents

* 🚀 Features
* 📁 Repository Structure
* ⚙️ Prerequisites
* 🗂 Data Schema & Preparation
* 📊 Sample DAX Measures
* 📈 Visuals Included
* 🎨 Dashboard Designing
* 📊 Project Outcome
* 📂 Dataset
* 🧠 Skills Demonstrated

---

# 🚀 Features

* Year-based filtering (2022–2025)
* Region, Segment, and Category slicers
* **Open Filters / Close Filters functionality** for better dashboard space management
* Reset Filters button to quickly clear all selections
* Monthly sales trend analysis
* Category-wise sales distribution
* Profit comparison across regions
* Top 10 performing products analysis
* Drill-through navigation to **Product Performance Overview**
* Product-wise sales analysis

---

# ⚙️ Prerequisites

* Microsoft Power BI Desktop(latest version recommended)
* (optional) Power Bi Pro / Service for publishing & sharing
* Basic familarity with Power Query and DAX formulas
* CSV or Excel file of Sales data with at least: Order details, product details & customer details.

---

# 🗂 Data Schema & Preparation

###  Data Schema

| Column Name  | Description                                                                            |
| ------------ | -------------------------------------------------------------------------------------- |
| Order Date   | Date when the order was placed. Used for time-based analysis and monthly sales trends. |
| Region       | Geographic sales region such as East, West, Central, or South.                         |
| Segment      | Customer segment category (Consumer, Corporate, Home Office).                          |
| Category     | High-level grouping of products such as Technology, Furniture, or Office Supplies.     |
| Sub-Category | Detailed product classification within a category.                                     |
| Product Name | Name of the individual product sold.                                                   |
| Sales        | Total revenue generated from the product sale.                                         |
| Quantity     | Number of units sold in the transaction.                                               |
| Profit       | Profit earned from the sale after costs and discounts.                                 |


### Data Preparation Steps

* Imported dataset into Power BI
* Cleaned and transformed data using **Power Query**
* Created **Date Table** for time-based analysis
* Established relationships between tables
* Created calculated columns and measures

---

# 📊 Sample DAX Measures

Total Sales Total Sales = SUM(Sales[Sales])

Total Profit Total Profit = SUM(Sales[Profit])

Total Orders Total Orders = DISTINCTCOUNT(Sales[Order ID]) 

Total Quantity Total Quantity = SUM(Sales[Quantity]) 

Profit Margin Profit Margin % = DIVIDE([Total Profit],[Total Sales])

Avg Order Value Avg Order Value = DIVIDE([Total Sales],[Total Orders]) 

Product Contribution  Product Contribution % =
DIVIDE(
[Total Sales],
CALCULATE([Total Sales], ALL(Sales))
)

Product Rank Product Rank =
RANKX(
ALL(Sales[Product Name]),
[Total Sales],
,
DESC
)

Product Title = 
"PRODUCT PERFORMANCE OVERVIEW - " &
SELECTEDVALUE(Sales[Product Name], "ALL Products") 

---

# 📈 Visuals Included

* KPI Cards:Display key Sales metrics such as:
  * Total Sales
  * Profit
  * Orders
  * Quantity
* Line Chart: Shows Monthly Sales Trend
* Donut Chart: Shows Sales by Category
* Bar Chart: Displays Profit by Region
* Bar Chart: Provides Top 10 Products by Sales
* Drill-through Page: Navigate to Product Performance Overview
  
---

# Dashboard Designing

Based on the defined dashboard requirements, appropriate visuals were designed to effectively represent sales performance and business insights. Relevant charts and KPI indicators were created to analyze trends, regional profitability, and product performance.


---

# 📊 Project Outcome

This project helps businesses understand sales performance by providing insights into:

* Sales growth trends
* Regional profitability
* Category performance
* Top performing products
* Customer purchasing behavior

The dashboard enables stakeholders to **identify opportunities and make data-driven decisions**.

---

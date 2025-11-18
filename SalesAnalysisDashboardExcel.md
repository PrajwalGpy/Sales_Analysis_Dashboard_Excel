# Ferns and Petals (FNP) Sales Analysis Dashboard

## Project Overview

[cite_start]This project involves analyzing a sales dataset from Ferns and Petals (FNP), a company specializing in gifts for various occasions like Diwali, Raksha Bandhan, Holi, Valentine's Day, Birthdays, and Anniversaries[cite: 2].

[cite_start]The goal is to analyze sales trends, customer behavior, and product performance by creating a comprehensive Excel dashboard[cite: 4, 5]. [cite_start]The insights from this analysis are intended to help the company improve its sales strategy and optimize customer satisfaction[cite: 4, 5].

## Key Business Questions (KQs)

[cite_start]This dashboard was built to answer the following 10 key business questions[cite: 5]:

1.  [cite_start]What is the **Total Revenue**? [cite: 6]
2.  [cite_start]What is the **Average Order and Delivery Time**? [cite: 7]
3.  [cite_start]What is the **Monthly Sales Performance** for 2023? [cite: 8]
4.  [cite_start]What are the **Top Products by Revenue**? [cite: 8]
5.  [cite_start]What is the **Average Customer Spend**? [cite: 9, 10]
6.  [cite_start]What is the sales performance of the **Top 5 Products**? [cite: 11]
7.  [cite_start]What are the **Top 10 Cities** by Number of Orders? [cite: 12]
8.  [cite_start]Does **Order Quantity impact Delivery Time**? [cite: 14]
9.  [cite_start]What is the **Revenue Comparison Between Occasions**? [cite: 15]
10. [cite_start]What is the **Product Popularity by Occasion**? [cite: 16]

## Data Sources

The analysis is based on three primary data files:

- [cite_start]**`products.csv`**: Contains detailed product information, including Product ID, Name, Category, Price, and intended Occasion[cite: 17].
- **`orders.csv`**: The main transaction table. [cite_start]It includes Order ID, Customer ID, Product ID, Quantity, all relevant dates (order and delivery), and customer Location[cite: 49].
- [cite_start]**`customers.csv`**: Contains customer demographic data, such as Customer ID, Name, and City[cite: 54].

## Tools & Methodology

This dashboard was created entirely within **Microsoft Excel**.

- **Data Modeling (Power Pivot):** The three CSV files were loaded into the Excel Data Model. Relationships were established between the tables (e.g., `orders[Product_ID]` to `products[Product_ID]`) to create a relational database for analysis.
- **DAX (Data Analysis Expressions):** DAX measures were written to calculate key metrics, including:
  - `Total Revenue = SUMX(orders, orders[Quantity] * RELATED(products[Price (INR)]))`
  - `Avg. Delivery Time = AVERAGE(orders[Delivery_Date] - orders[Order_Date])`
  - `Total Orders = DISTINCTCOUNT(orders[Order_ID])`
- **Visualizations (PivotTables & PivotCharts):**
  - **KPI Cards:** To display Total Revenue, Avg. Delivery Time, and Avg. Customer Spend.
  - **Line Chart:** To track Monthly Sales Performance.
  - **Bar Charts:** To visualize Top Products by Revenue and Top 10 Cities by Orders.
  - **Tree Map:** To compare Revenue by Occasion.
  - **Scatter Plot:** To analyze the relationship between Order Quantity and Delivery Time.
- **Interactivity:**
  - **Slicers** were added for **Occasion**, **Product Category**, and **City**, allowing users to filter the entire dashboard dynamically.
  - A **Timeline** slicer was added for the `Order_Date` to filter by specific time periods.

## Dashboard Features & Key Insights

The final dashboard is a single, interactive sheet that provides at-a-glance answers to all key business questions.

- **Main KPIs:** The top of the dashboard prominently displays the most critical metrics: Total Revenue, Average Delivery Time, and Average Customer Spend.
- **Sales Trends:** The "Monthly Sales Performance" chart shows the fluctuation of sales throughout 2023, helping to identify seasonal peaks.
- **Product Performance:** A horizontal bar chart identifies the top revenue-generating products, while a separate chart shows the sales trends for just the top 5, allowing for focused analysis.
- **Geographic Analysis:** The "Top 10 Cities" chart highlights key markets by order volume.
- **Occasion-Based Insights:** The dashboard features a "Revenue by Occasion" chart and a "Product Popularity by Occasion" matrix, which are crucial for FNP's business model. These can be filtered using the "Occasion" slicer for deeper insights into holiday-specific performance.

## How to Use

1.  Open the `Ferns and Petals Sales Analysis.xlsx` file.
2.  Navigate to the "Dashboard" worksheet.
3.  Use the slicers at the top of the page (e.g., Occasion, Category) to filter the data.
4.  Click on any element within a chart (e.g., a specific month on the line chart) to cross-filter the entire dashboard.
5.  Hover over chart elements to see detailed tooltips with specific values.

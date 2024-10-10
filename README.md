# Sales Insights Dashboard using PowerBI and MySQL

This repository contains a **Sales Insights Dashboard** project, which integrates **PowerBI** with a **MySQL** database. The dashboard provides a comprehensive overview of sales performance, allowing users to explore key sales metrics and trends interactively.

## Project Overview

The **Sales Insights Dashboard** aims to help businesses analyze and visualize their sales data. By connecting to a MySQL database, this PowerBI dashboard offers real-time insights into sales figures, performance trends, and customer behavior. The dashboard presents key performance indicators (KPIs), comparisons, and detailed sales breakdowns across various dimensions.

### Key Features
- **Sales Metrics:** Analyze total revenue, profit margins, and average order values.
- **Time-Based Analysis:** View sales performance over time (daily, monthly, yearly).
- **Regional Insights:** Explore sales across different regions or countries.
- **Product Performance:** Identify top-selling products and product categories.
- **Customer Insights:** Analyze customer segmentation, purchase behavior, and customer lifetime value.
- **Dynamic Filtering:** Apply filters and slicers to explore data by time, product, region, and customer demographics.

## Technology Stack
- **PowerBI:** For interactive data visualizations and reporting.
- **MySQL:** Used as the data source for storing sales data.
- **Power Query:** To perform data extraction, transformation, and loading (ETL) from the MySQL database into PowerBI.
- 
## Setup & Installation

1. **MySQL Database**  
   Ensure your MySQL database contains the relevant sales data (e.g., sales orders, customer details, product data).  
   - You can install MySQL from [here](https://dev.mysql.com/downloads/installer/).

2. **PowerBI Desktop**  
   Download PowerBI Desktop from [here](https://powerbi.microsoft.com/desktop/).

3. **Connecting PowerBI to MySQL**  
   - Open PowerBI Desktop.
   - In the **Home** tab, click **Get Data**, then select **MySQL database**.
   - Input your server, database, and login credentials to connect PowerBI to the sales data.

4. **Import the PowerBI File**  
   Open the `.pbix` file from this repository in PowerBI Desktop and connect it to your MySQL database.

5. **Data Refresh**  
   After connecting to your database, refresh the data within PowerBI to visualize your up-to-date sales insights.

## Dashboard Features

- **Sales Overview:** A high-level view of total sales, revenue, and profits.
- **Top Products & Categories:** Lists top-performing products and product categories.
- **Sales by Region:** A breakdown of sales performance across various regions and markets.
- **Customer Analysis:** Insights into customer demographics, behavior, and loyalty.
- **Sales Trends:** Interactive visualizations showing monthly and yearly sales trends.

## Screenshots



---![Screenshot 2024-10-10 104422](https://github.com/user-attachments/assets/4a670a07-59a2-4c7b-a8cb-4134130f4911)

## Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`

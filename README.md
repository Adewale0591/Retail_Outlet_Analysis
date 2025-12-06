# Retail_Outlet_Analysis
### Table of Contents
- [Project Overview](#project-overview)
- [Objectives](#objectives)
- [Dataset Description](#dataset-description)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Visualizations](#visualizations)
- [Insights](#insights)
- [Recommendations](#recommendations)

## Project Overview
This project analyzes retail sales and supply chain performance using transactional data. The objective is to uncover patterns in customer behavior, product profitability, shipping efficiency, and discount impact to help businesses optimize revenue, reduce losses, and improve decision-making across operations.

## Objectives
- Identify the highest revenue and most profitable products.
- Track revenue and profit over time (daily, monthly, yearly).
- Identify most profitable customer segments & regions.
- Determine best and worst selling product categories/sub-categories.
- Identify products/customers with high return rates.

## Dataset Description
- Order details (Order ID, Order Date, Ship Date, Shipping Mode).
- Customer information (Customer ID, Segment, Region, Country, City).
- Product hierarchy (Category, Sub-Category, Product Name).
- Financials (Sales, Profit, Discount, Quantity).
- Logistics (Shipping Mode, Returned Status).
- Date lookup table for time-based analysis.

## Data Cleaning and Preparation
- Removed columns.
- Table duplication for data normalization and creating relationships.
- Merging queries.
- Creating date table for time intelligence functions.

## Exploratory Data Analysis
- Tools (Power Query, DAX functions, Power BI Data Modeling).
- Created measures and columns for visualization.
  - Total Sales = SUM(Sales[Sales])
  - Total Profit = SUM('Sales'[Profit])
  - Total Quantity = SUM(Sales[Quantity])
  - Return Rate% = DIVIDE(COUNTROWS(FILTER(Sales, Sales[Returned] = "Yes")), COUNTROWS(Sales))
  - Total Customers = DISTINCTCOUNT(Sales[Customer ID])
  - YTD Sales = TOTALYTD([Total Sales], 'Date'[Date])
  - MTD Sales = TOTALMTD([Total Sales], 'Date'[Date])
  - YoY Growth = [Total Sales] - [Previous Year Sales]
  - YoY Growth% = DIVIDE([Total Sales] - [Previous Year Sales], [Previous Year Sales])
  - Customer Rank = RANKX(ALL(Customer[Customer Name]),[Total Sales],,DESC)

  ![Retail Outlet 7](https://github.com/user-attachments/assets/ff40fc60-b892-442a-8d41-e4894c6472d2)

  ## Visualizations
![Retail Supply Chain Report 1](https://github.com/user-attachments/assets/2fadc956-2cd8-4923-b1ef-523c989dac68)

![Retail Supply Chain Report 2](https://github.com/user-attachments/assets/45dbee11-1491-4406-9d49-6b1fffc7cb00)

![Retail Supply Chain Report 3](https://github.com/user-attachments/assets/57d063d6-96cd-4563-b7f1-2817f60113fa)

## Insights
- Technology drive the highest sales with profit. Although Office Supplies has the lowest sales, the profit is greater than that of Furniture category.
- There was a bit of decline in sales from 2014 to 2015, which then increased after without a decline in profit making 2017 the year of highest sales and profit.
- West & East regions generate most sales.
- Corporate and Consumer segments dominate sales.
- Machines, Tables and Binders have the highest return rates.

## Recommendations
- Review pricing strategy for high-return items.
- Increase marketing efforts in high-performing regions like Central & South.
- Reduce discounts on low-margin products.
- Improve delivery times and customer service for high-value customers.
- Create loyalty programs for top 10% customers by sales volume.


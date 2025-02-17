
# New-Superstore-Sales-Dashboard-Power-BI-Project
This project analyzed the new superstore dataset to uncover trends, customer behavior, and profitability insights thereby providing a data-driven approach to decision-making in retail operations. 

**Data Overview**
The dataset was originally made up of one CSV file with 19 columns. However, after extraction, transformation, and loading with Power Query, it became a model with six tables and a measures table with the following column details expounded below:

**Customer:** customer name, order_id, zip
**Date:** date, year, quarter, month, day, MonthNumber, date hierarchy, YearMonth
**FactSales:** discount, order_date, order_id, profit, profit_margin, quantity, sales, shipping_id, zip
**Location:** country, region, state, city, zip, order_id, country hierarchy
**Orders:** order_date, order_id, ship_date, shipping_id, zip
**Product:** manufactory, section, category, subcategory, product_id, product_name, order_id, product hierarchy


**Key Business Questions Answered**

* How are sales and profits trending over time?
* Which regions drive the most sales and how have the regions ranked in performance over time?
* What percentage of total sales represents profit or loss?
* How have discounts impacted profitability?
* What is the average order value?
* Who are the most valuable customers based on purchase behavior?
* Which states are the top 5 performing states in terms of sales, and how do their sales figures compare to their profit or loss?

**Data Visualization Highlights & Insights**

1. Total Sales & Profit By Region: Line & Column Chart.
   The West region recorded the most sales and profit almost doubling the South region in sales and more than doubling it in profits.
   
2. Total Sales, Total Profits, and Total Losses By Product Category: 100% Stacked Column Chart.
   The technology product category recorded the most sales, profit, and the least losses of the three product categories.
   
3. Discount Usage % By Total Profit By Product Segment: Scatter Chart
   Discount usage % increased with profit across product segments showing a positive correlation between the use of discounts and profits.
   
4. Regional ranking By Total Sales per year: Ribbon Chart.
   The West region ranked 1st in total sales in all four years except one (2020) while the South region ranked last in total sales in all years except in 2019.
   
5. Top five states by total sales with Total profits as a tooltip: Map Visual
   California, New York, Texas, Washington, and Pennsylvania topped the charts respectively. However, Texas and Pennsylvania's top sales performances were detracted or diminished by 
   their subsequent losses.
   
6. Total Sales & Profits By Year: Line Chart
   Generally, the total sales and profits showed an upward trajectory over the years under observation.
   
 
**Dashboard Features & Visuals**

Sales & Profit Trends
* Line Chart: sales and profit trends over the years. The report allows a drill down to quarters, months, and days.
* Ribbon Chart: regional ranking based on sales performance over the years.
* Line and Clustered Column Chart: sales and profit comparison for each region.
* Map: top 5 states with the most sales while showcasing profit/loss details to uncover how sales figures compare to their profits or losses.
* 100% Stacked Column Chart: how each product category's sales, profits, and losses compare.

Discount Impact on Profitability
* Scatter Chart: compares discount usage percentage to profits for each product segment.
* Card Visual: displays the discount usage percentage.

**Key Metrics (DAX Measures Used)**
* Total Sales: SUM (factsales[Sales])
* Total Profit: SUM (factsales[profit])
* Average Order Value (AOV): DIVIDE( [Total Sales] , DISTINCTCOUNT (orders[order.id]), 0)
* Discount Usage %: DIVIDE(
                  SUM(factSales[discount]), SUM(factSales[sales]), 0
                  ) * 100
* Total Loss: CALCULATE([Total profit], factSales[profit] < 0)
* Total Profit Margin: SUM(factsales[profit_margin])


**Conclusion**
The new Superstore dataset analysis uncovered various insights regarding geographical and product sales performance, the correlation between key metrics, and the underlying story in the sales figures that call for further exploration, root cause analysis, and decision-making.



**How to Access the Dataset**
https://www.kaggle.com/datasets/timchant/supstore-dataset-2019-2022/data

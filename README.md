# Lita_Capstone_Project
This is where I document my capstone project for the Incubator Hub
### Project Title: Sales Analysis
### Project Overview

### DATA DESCRIPTION
Column Names and Descriptions

1. OrderID (Unique Identifier): A unique number assigned to each order.

2. CustomerID (Foreign Key): The ID of the customer who placed the order.

3. Product (String): The name or description of the product purchased.

4. Region (String): The geographical region where the order was shipped.

5. OrderDate (Date): The date when the order was placed.

6. Quantity (Integer): The number of units of the product purchased.

7. UnitPrice (Decimal): The price of a single unit of the product.

### Tools Used
- Microsoft Excel for data cleaning,Analysis and Visualisation 
- SQL - Structured query Language for querying data for building of Portfolio in Github
- Power Bi - For Dashboard and Visualization 


### STATISTICAL ANALYSIS ON THE DATA
- Total sales for each prroduct category
- Number of sales category in each region
  
  select region, count(orderid) as Num_sales_transaction
from LITAcustomers group by region order by
Num_sales_transaction desc


![image](https://github.com/user-attachments/assets/9c535931-ef4e-4f1d-917e-2ccc8b9b7f00)


- Highest-selling product by total sales value

  SELECT top 1 product,
SUM(cast(quantity as int) * cast(unitprice as decimal)) AS total_sales
FROM 
LITAcustomers
GROUP BY 
product
ORDER BY 
total_sales DESC

![image](https://github.com/user-attachments/assets/d6f01bf0-0995-4a98-ad09-ce8a0dae60a9)

- Total revenue per product
- Monthly sales totals for the current year
- Top 5 customers by total purchase amount
- Percentage of total sales contributed by each region
- Products with no sales in the last quarter

### METHODOLOGY
### DATA MANIPULATION 
### INSIGHTS
### CONCLUSION

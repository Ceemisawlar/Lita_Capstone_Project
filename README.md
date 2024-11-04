# Lita_Capstone_Project
This is where I document my capstone project for the Incubator Hub
### Project Title: Sales Analysis
### Project Overview

### DATA DESCRIPTION FOR SALES DATA
Column Names and Descriptions

1. OrderID (Unique Identifier): A unique number assigned to each order.

2. CustomerID (Foreign Key): The ID of the customer who placed the order.

3. Product (String): The name or description of the product purchased.

4. Region (String): The geographical region where the order was shipped.

5. OrderDate (Date): The date when the order was placed.

6. Quantity (Integer): The number of units of the product purchased.

7. UnitPrice (Decimal): The price of a single unit of the product.

### DATA DESCRIPTION FOR CUSTOMERS DATA

1) CustomerID (Unique Identifier): A unique number assigned to each customer.

2) CustomerName (String): The name of the customer.

3) Region (String): The geographical region where the customer is located e.g west, east, north,south

4) SubscriptionType (String): The type of subscription plan of the customers(e.g., Basic, Premium, etc).

5) SubscriptionStart (Date): The start date of the subscription.

6) SubscriptionEnd (Date): The end date of the subscription.

7) Canceled (Boolean): Indicates whether the subscription has been canceled (True or false).

8) Revenue (Decimal): The total revenue generated by the subscription.

### Tools Used
- Microsoft Excel for data cleaning,Analysis and Visualisation 
- SQL - Structured query Language for querying data for building of Portfolio in Github
- Power Bi - For Data cleaning and Visualization

### Data Cleaning
This is the first stage for any data analysis project which includes 

* Uploading the data

* Checking for null variables and missing data
  
* Data cleaning which includes removing duplicates


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

  SELECT product,
SUM(Cast(quantity as int) * cast(unitprice as decimal)) AS total_revenue
FROM 
LITAcustomers
GROUP BY 
product
ORDER BY 
total_revenue DESC;

![image](https://github.com/user-attachments/assets/3325885b-53a1-4c2a-98b6-d5f6712ae011)

- Monthly sales totals for the current year

  SELECT DATENAME(month, orderdate) AS month_name,
SUM(cast(quantity as int) * cast(unitprice as decimal(10,0))) AS monthly_sales
FROM 
LITAcustomers
WHERE 
YEAR(orderdate) = YEAR(GETDATE())
GROUP BY 
DATENAME(month, orderdate)
ORDER BY 
month_name DESC

![image](https://github.com/user-attachments/assets/29a2fb88-5d6f-4a40-8c72-710bbea6d5a6)

- Top 5 customers by total purchase amount

  SELECT top 5 Customer_Id,
SUM(cast(quantity as int) * cast(unitprice as decimal(10,0))) AS total_purchase_amount
FROM 
    LITAcustomers
GROUP BY 
    Customer_Id
ORDER BY 
    total_purchase_amount DESC

![image](https://github.com/user-attachments/assets/11974d0f-68dc-4a2e-8164-d222d2ca6edc)

- Percentage of total sales contributed by each region

  SELECT region,
SUM(cast(quantity as int) * cast(unitprice as decimal(10,0))) AS regional_sales,
SUM(cast(quantity as int) * cast(unitprice as decimal(10,0))) / (SELECT SUM(cast(quantity as int) * cast(unitprice as decimal(10,0))) FROM LITAcustomers) * 100 AS percentage_of_total_sales
FROM 
Litacustomers
GROUP BY 
region
ORDER BY 
regional_sales DESC;

![image](https://github.com/user-attachments/assets/9ecc70c7-96e9-4343-ae67-124dd9e9bd1e)

- Products with no sales in the last quarter

  SELECT 
DISTINCT o.product
FROM 
LITAcustomers o
WHERE 
o.product NOT IN (
SELECT 
o2.product
FROM 
LITAcustomers o2
 WHERE 
o2.orderdate >= DATEADD(quarter, -1, GETDATE())
    )

  ![image](https://github.com/user-attachments/assets/48d7f916-febe-44df-886b-93015eb1c0d6)



### Exploratory Data Analysis
Exploratory Data Analysis (EDA) examines and visualizes data to understand its main characteristics and answer meaniful questions

### For sales Data using Excel the following insights where gotten

1)Average sales was retrieved using the in built formula in excel 

2)Total sales

3)Sum of quantity of product

4)Month by sum of sales

5)Total sales by region

6)Sum of sales by each quarter

### Customer Data


### DATA Visualisation



### INSIGHTS
### CONCLUSION

# NCC-Analysis-Report

A Udacity Power BI project for an online clothing store, View Power Bi Report [Here](https://app.powerbi.com/view?r=eyJrIjoiMjZkMjYzYmMtYzBmYy00ZWU5LWI1NjctYjY2NDEzZGE1Y2VhIiwidCI6ImE0YmE3MmNhLWFjNjMtNGRlNS04OTA2LThjNjY5OTg2N2UzYyJ9)

# Overview

An online national clothing chain needs your help creating a targeted marketing campaign. Sales have been flat and they want to lure lost customers back. They want to advertise specific products to specific customers in specific locations, but they don’t know who to target. They have three products in mind:

Shirt: $25
Sweater: $100
Leather Bag: $1,000
They need you to conduct an analysis to determine the best product to advertise to each customer.

# Analysis Questions:

- What is the correlation (R2 value) between sales and income?
- What is the correlation (R2 value) between customer ratings and product return rate?
- What are the linear regression formulas to predict customer income from customer sales?
- Which customer do you predict has the highest income?
- Which product will be advertised the most?

# Data Files
## US Census Bureau
Average income | location | population | industry
## Business Data
Product inventory | Product prices | Customer rating | Product return rate
## Customer Data
Customer ID | Names | Location | Date of birth | Purchase history

# Data Cleanup
- Used Power Query to Split cloumns, Replace Values, Unpivot.
- Created a date table in Power Query using {Number.From(List.Min(TableName[ColumnName]))..Number.From(List.Max(TableName[ColumnName]))}

| Purchase List  | Product Inventory |
| ------------- | ------------- |
| ![Purchase list](https://github.com/DianaTaha/NCC-Analysis-Report/assets/157681412/9227ad20-7702-486e-90f4-109a429fa370)  | ![product inventory](https://github.com/DianaTaha/NCC-Analysis-Report/assets/157681412/aa63e618-83c1-4add-9bbb-168f8371b8e9)  |

# Data Modelling
A star schema was relationship between the necessary tables
![Star_Schema](https://github.com/DianaTaha/NCC-Analysis-Report/assets/157681412/510fec9c-dd82-49ca-b73c-66f1105f6452)

# Dax Formulas
- Linear Regression Formula: X=(-722.14-Y)/0.01
- Created Regretion table
- Created Income Buckets "Image Below"
- 
| Income Range  | Regression table content |
| ------------- | ------------- |
  ![income range dax formula](https://github.com/DianaTaha/NCC-Analysis-Report/assets/157681412/29266bc9-9f28-47bb-9b2a-2614a79ec225) | <img width="213" alt="Screenshot 2024-01-25 at 2 19 20 PM" src="https://github.com/DianaTaha/NCC-Analysis-Report/assets/157681412/d3afa6ed-5f99-41d4-83d8-ac897b343c01">

# Analysis & Visualization
The report can be accessed [Here](https://app.powerbi.com/view?r=eyJrIjoiMjZkMjYzYmMtYzBmYy00ZWU5LWI1NjctYjY2NDEzZGE1Y2VhIiwidCI6ImE0YmE3MmNhLWFjNjMtNGRlNS04OTA2LThjNjY5OTg2N2UzYyJ9)

<img width="1685" alt="Screenshot 2024-01-25 at 11 46 56 AM" src="https://github.com/DianaTaha/NCC-Analysis-Report/assets/157681412/88359eda-fc85-4200-96a0-8cb04efa45a3">
<img width="1685" alt="Screenshot 2024-01-25 at 11 47 29 AM" src="https://github.com/DianaTaha/NCC-Analysis-Report/assets/157681412/f702e3c3-9248-41c5-a5c6-a3b1a8acd68e">
<img width="1685" alt="Screenshot 2024-01-25 at 11 47 42 AM" src="https://github.com/DianaTaha/NCC-Analysis-Report/assets/157681412/1300cb3e-67b5-4661-88e7-167ee28680fd">

# Findings

### What is the correlation (R2 value) between sales and income?
	There is a positive Correlation value between Sales is 0.78 as per “Average income VS average sales scatter plot”.
 
### What is the correlation (R2 value) between customer ratings and product return rate?
	There is a strong Negative Correlation with a value of 0.69 between customer ratings and product returns as per “the relationship between return rate and rating” scatter plot. 

### What are the linear regression formulas to predict customer sales and customer incomes?
Linear Regression Formula: X=(-722.14-Y)/0.01

### Which customer do you predict has the highest income?
The predicted Customer with highest income is “Jon Little” As per the Card visual representing the below formula:
Highest Cx income = LOOKUPVALUE('Customer List'[Full name],'Customer List'[Predict Cx income],MAX('Customer List'[Predict Cx income]))

### Which product will be advertised the most?
- As per the analysis an average of 81% of the client’s income range is low and average as per “Predicted income range column chart”
- I recommend advertising the most: $25 spring tshirt &  $100 Cotton sweater according to the season of the year.
- For the $1,000 leather bag it can be advertised in highest income state as it falls in the luxury category.
- There are low sales in some of the high income states ex: District of Columbia, New Jersey, Maryland, Massachusetts and Hawaii in comparison with California, as per the “state,last 6 months purchase,  income” table.
- There is an opportunity to market these products in those states.
- Majority of clients based on the last 6 month purchase are born between 1960-2000 as per “Last 6 month purchase by age group” donut chart

 


# NCC-Analysis-Report

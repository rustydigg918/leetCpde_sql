# leetCpde_sql

### 1. Write a SQL query to get the second highest salary from the Employee table.
```
+----+--------+
| Id | Salary |
+----+--------+
| 1  | 100    |
| 2  | 200    |
| 3  | 300    |
+----+--------+
```
For example, given the above Employee table, the query should return 200 as the second highest salary. If there is no second highest salary, then the query should return null.

```
+---------------------+
| SecondHighestSalary |
+---------------------+
| 200                 |
+---------------------+
```

#### ANSWER >>>
```
SELECT MAX(Salary) as SecondHighestSalary FROM Employee
WHERE Salary <(SELECT MAX(Salary) FROM Employee)
```
### 2. Technical Assessment 



```**Table schema**

ORDERS
order_id varchar(30) composite primary key
customer_id numeric(38,0)
order_datetime timestamp
item_id varchar(10) composite primary key
order_quantity numeric(38,0)
Sample extract from ORDERS
order_id | customer_id | order_datetime | item_id | order_quantity

A-001 | 32483 | 2018-12-15 09:15:22 | B000 | 3
A-005 | 21456 | 2019-01-12 09:28:35 | B001 | 1
A-005 | 21456 | 2019-01-12 09:28:35 | B005 | 1
A-006 | 42491 | 2019-01-16 02:52:07 | B008 | 2

ITEMS
item_id varchar(10) primary key
item_category varchar(20)
Sample extract from ITEMS
item_id | item_category

B000 | Outdoors
B001 | Outdoors
B002 | Outdoors
B003 | Kitchen
B004 | Kitchen

/* Questions */
-- Q1: How many UNITS have been ordered yesterday? UNITS is the total quantity ordered.
-- Output as: Units

-- Q2: How many UNITS have been ordered in the last 7 days (including today) in EACH and EVERY category? Please consider SEVEN calendar days in total, including today.
-- Please consider ALL categories, even those which have zero orders.
-- Output as: Category | Units

-- Q3: How many UNITS in EACH and EVERY category have been ordered on each day of the week in the last 7 days (including today)?
-- Output as: Category | Sunday_units | Monday_units | Tuesday_units | Wednesday_units | Thursday_units | Friday_units | Saturday_units

-- Q4: It is possible for customers to place multiple orders on a single date.
-- For ALL customers, write a query to get the earliest ORDER_ID for each customer for each date they placed an order.
-- Output as: Customer_id | Order_date | First_order_id

-- Q5: Write a query to get the second earliest ORDER_ID for each customer for each date they placed AT LEAST two orders.
-- Output as: Customer_id | Order_date | Second_order_id



```
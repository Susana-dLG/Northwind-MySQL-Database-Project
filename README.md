# 🛒 Northwind MySQL Project

This project involves creating and analyzing the classic **Northwind database** using **MySQL**. The Northwind dataset represents a fictional trading company that imports and exports specialty foods worldwide. It includes details about customers, employees, orders, products, suppliers, and more—making it ideal for practicing relational database design and SQL queries.

---

## 📌 1. Project Overview

This repository demonstrates how to:
- Rebuild the **Northwind schema** using SQL DDL (Data Definition Language).
- Populate tables with sample business data.
- Query the dataset to extract insights on customer behavior, product performance, and supply chain activity.

---

## 🎯 2. Project Objectives

- Build a relational database using structured SQL commands.
- ER diagrams
- Explore multi-table relationships using **JOINs**, **aggregations**, and **filters**.
- Generate business insights through analytical SQL queries.
- Simulate real-world database interactions in a retail context.

---

## 🗂 3. Schema Overview

The database contains the following key tables:

| Table                | Description                                             |
|---------------------|---------------------------------------------------------|
| `customers`          | Customer info, contact, and location details           |
| `orders`             | Sales order data, linked to customers and employees    |
| `order_details`      | Products, prices, and quantities per order             |
| `products`           | Product names, categories, pricing, and stock info     |
| `suppliers`          | Supplier companies and their contact information       |
| `employees`          | Employee data including roles and managers             |
| `categories`         | Product categories (e.g., Beverages, Produce)          |
| `shippers`           | Companies responsible for shipping orders              |
| `regions`, `territories`, `employee_territories` | Employee and regional mapping |

📄 *All tables, keys, constraints, and indexes were created using the SQL script: `Northwind Database create.sql`.*

---

## 📊 4. Dataset Overview

The Northwind dataset includes:

- ✔️ Dozens of products from 8 categories
- ✔️ 29 suppliers and 91 customers across different countries
- ✔️ 830+ customer orders
- ✔️ 9 employees and a hierarchy of reporting territories
- ✔️ Realistic sales transactions and shipping records

This sample dataset allows you to simulate queries found in retail, sales, logistics, and CRM systems.

---

## 💡 5. Sample SQL Queries

```sql
-- 1.-- write sql query to return customers from USA
select count(*)
from customers
where country = "USA";
-- 2.# Write an SQL query to get the top 10 products from the Products table with a Price greater than 20, limiting the result to 10 rows.
select *
from products where Price> 20
order by Price  
limit 10
-- 3.-- SUBQUERY
-- find out the name of the products same as product category
select*
from products
where ProductName in (select categoryname from categories);
-- 4.-- ALIASES
select CustomerID 
as ID, CustomerName AS CUstomer
from Customers;
-- 5.-- Retrieve all columns from the "Customers" table where the "Country" is 'USA' and "City" is either 'Portland' or 'Kirkland', ordered by ascending "CustomerName".
select *
from customers
where Country = "USA" and City IN ("PORtland"," KIRKLABN") 
order by CustomerName asc;
-- 6.-- Retrieve all columns from the Orders table for orders made by customers whose name starts with "A".
select *
from orders
where CustomerID 
in (select CustomerID from customers where CustomerName like "a%");
-- 7.-- Inner join Supplier of each product
select products.productname as product, suppliers.suppliername as supplier
from products
inner join suppliers
on products.supplierid = suppliers.supplierid;
-- 8.-- Supplier Tokyo Traders only
select products.productname as product, suppliers.suppliername as supplier
from products
inner join suppliers
on products.supplierid = suppliers.supplierid
where suppliername = "Tokyo Traders";
-- 9.-- write sql query to find name of the products whivch has never been ordered
-- if product never been ordered , it will not have an orderid
SELECT *
FROM products as p
LEFT JOIN Order_details as od 
ON p.productid = od.productid
where od.orderid is null;
-- 10.-- calculate the price*qty, and name it as Sales
select p.productname, p.price, od.quantity, od.quantity*P.price as sales
from products as p
inner join order_details as od
on p.ProductID = od.ProductID;
-- 11.-- adding order by sales descendant
select  p.productname, sum(od.quantity * p.price) as sales
from products as p
inner join order_details as od
on p.productid = od.productid
group by p.productname
order by sales desc;
-- 12.-- Write a query to list each employee and the number of orders they have handled.
select e.employeeid, e.firstname,e.lastname, count(o.orderid) as ordercount 
from employees as e
inner join orders as o
on e.employeeid = o.employeeid
group by e.employeeid, e.firstname, e.lastname
order by ordercount ; 

## Tools used 


| **MySQL**                         | Main database engine for creating and querying the Northwind schema |
| **MySQL Workbench**               | GUI used for writing, testing, and visualizing SQL scripts          |
| **Northwind `create.sql`**        | SQL script used to build the full relational schema from scratch    |
| **Output CSV files***             | For previewing data exports and light preprocessing if needed       |
| **ER Diagram Tools** *(optional)* | For mapping relationships and understanding foreign key structures  |


## 🧠 7. Key Learning Outcomes
Designed and implemented a normalized relational schema

Queried interconnected data using JOINs, aggregates, and GROUP BY

Applied date functions, sorting, and limiting to get business insights

Practiced query optimization with indexes and keys

Simulated real-world database tasks relevant to retail and supply chain domains

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
-- 2.
-- 1.
-- 2.
-- 1.
-- 2.
-- 1.
-- 2.
-- 1.
-- 2.
-- 1.
-- 2.

## 🛠 6. Tools Used


| Tool                     | Purpose                                 |
| ------------------------ | --------------------------------------- |
| **MySQL**                | Database engine used to execute queries |
| **SQL Workbench**        | Writing and managing SQL scripts        |
| **Northwind SQL Script** | To generate schema and sample data      |
| **Output CSV files**     | Used for data preview or export         |

## 🧠 7. Key Learning Outcomes
Designed and implemented a normalized relational schema

Queried interconnected data using JOINs, aggregates, and GROUP BY

Applied date functions, sorting, and limiting to get business insights

Practiced query optimization with indexes and keys

Simulated real-world database tasks relevant to retail and supply chain domains

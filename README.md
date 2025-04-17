# 📊 Superstore Sales Analysis (SQL Portfolio Project)

A complete sales analysis project using **Microsoft SQL Server** built on a dummy Superstore dataset. This project demonstrates core SQL skills in database design, data exploration, aggregation, and business insights generation.

---

## 📌 Project Objectives

- Design and populate relational tables for Customers, Products, and Orders
- Perform exploratory data analysis (EDA) using SQL queries
- Derive key business metrics and insights
- Identify trends and performance across categories, regions, and customers

---

## 🧱 Database Structure

- **Customers**
  - CustomerID (Primary Key)
  - CustomerName
  - Segment (Consumer, Corporate, Home Office)
  - Region (East, West, Central, South)

- **Products**
  - ProductID (Primary Key)
  - ProductName
  - Category
  - SubCategory
  - UnitPrice

- **Orders**
  - OrderID (Primary Key)
  - OrderDate
  - CustomerID (Foreign Key)
  - ProductID (Foreign Key)
  - Quantity
  - Discount

---

## 📈 Insights Generated

- 📌 **Total Sales & Profit** per order
- 🏆 **Top-selling products** and categories
- 💸 **Monthly revenue trends** and average order value
- 👥 **Top customers** by spending
- 📍 **Best performing regions**
- 🔄 **Average purchase frequency**
- 🧾 **Category profitability**

---

## 📂 Files Included

| File / Folder           | Description |
|-------------------------|-------------|
| `sql_scripts/` https://1drv.ms/u/c/44ee9b98ba9a1f65/Ef37q3DuLA9AmaGiK8B8ChgBEtP-Y3kZ7rlj0L-Hj9rOJA?e=7kdrzV         | Contains the full SQL code: table creation, data inserts, and all queries |
| `README.md`             | Documentation of the project |

---

## 🛠 Tools Used

- **SQL Server Management Studio (SSMS)**
- T-SQL

---

## 🔍 Sample Queries

```sql
-- Total Sales and Profit per Order
SELECT 
    o.OrderID,
    c.CustomerName,
    p.ProductName,
    o.Quantity,
    o.Discount,
    ROUND(o.Quantity * p.UnitPrice * (1 - o.Discount), 2) AS Sales,
    ROUND(o.Quantity * p.UnitPrice * (1 - o.Discount) * 0.2, 2) AS Profit
FROM Orders o
JOIN Customers c ON o.CustomerID = c.CustomerID
JOIN Products p ON o.ProductID = p.ProductID;

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
 <img width="421" alt="image" src="https://github.com/user-attachments/assets/af1a8c49-b483-4bf0-b83d-82b9072de62f" />

- 🏆 **Top-selling products** and categories
<img width="347" alt="image" src="https://github.com/user-attachments/assets/a7973e02-4483-4aba-b323-59348f174760" />
<img width="341" alt="image" src="https://github.com/user-attachments/assets/cf2c5988-b6ad-4a8b-aaf0-da8e64b5ee63" />
 
   - *Top selling products are Monitor & Notebook*
   - *Top Categories are Technology & Office Supplies*

- 💸 **Monthly revenue trends** and average order value
<img width="182" alt="image" src="https://github.com/user-attachments/assets/81b153fa-2ff7-46c0-a25d-182589831b77" />
<img width="203" alt="image" src="https://github.com/user-attachments/assets/27d0e0f3-2583-4463-9e8f-bc977816dc5f" />
<img width="218" alt="image" src="https://github.com/user-attachments/assets/a2dbddcc-7bb6-46bd-a42d-0ea66900e9a1" />

  - *March 2024 recorded the highest sales while January 2024 Lowest holds sales*
  - *Average order value is $127.44*
  
- 👥 **Top customers** by spending
<img width="226" alt="image" src="https://github.com/user-attachments/assets/de62f4d2-d127-440d-9261-7ffc84f415ed" />

  - *Bob Johnson & Alice Smith are the top customers*

- 📍 **Best performing regions**
<img width="197" alt="image" src="https://github.com/user-attachments/assets/03062a7a-d699-451f-93f0-f258ea4137d2" />

  - *Best performing regions are, West & East respectively*
 
- 🔄 **Average purchase frequency**
<img width="198" alt="image" src="https://github.com/user-attachments/assets/f2d02038-f4de-4909-80c7-eacb4843ee6c" />

  - *Average purchase frequency is 1*
  
- 🧾 **Category profitability**
<img width="244" alt="image" src="https://github.com/user-attachments/assets/8759aee2-d08f-4f4e-8d5e-4cb894bcaad9" />

  - *Technology Category generated Most Profit($95.49)*

---

## 📂 Files Included

| File / Folder           | Description |
|-------------------------|-------------|
| [`sql_scripts/`](https://1drv.ms/u/c/44ee9b98ba9a1f65/Ef37q3DuLA9AmaGiK8B8ChgBEtP-Y3kZ7rlj0L-Hj9rOJA?e=7kdrzV)        | Contains the full SQL code: table creation, data inserts, and all queries |
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

---


📌 Key Metrics

Metric | Value 
Total Sales | $892.14
Highest Revenue Month | March 2024
Most Profitable Category | Technology
Top Regions | West & East
Average Order Value | $127.44

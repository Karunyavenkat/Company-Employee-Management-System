# 🏢 Company Employee Management System (SQL Project)

A simple and beginner-friendly **Employee Management System** built using MySQL. This project demonstrates how to design a relational database, apply constraints, and perform real-world data operations using SQL.

---

## 📌 Project Overview

This project focuses on managing employee and department data efficiently using structured queries. It includes database creation, table relationships, and various SQL operations to simulate a real-world company system.

---

## 🎯 Objectives

- Understand relational database design  
- Apply primary and foreign key constraints  
- Perform CRUD (Create, Read, Update, Delete) operations  
- Use aggregate functions for data analysis  
- Implement JOIN queries to combine multiple tables  

---

## 🛠️ Technologies Used

- **Database:** MySQL  
- **Language:** SQL  
- **Tools:** MySQL Workbench / CLI / phpMyAdmin  

---

## 🧱 Database Structure

### 📂 Department Table

| Column     | Type         | Constraints       |
|------------|-------------|------------------|
| dept_id    | INT          | PRIMARY KEY       |
| dept_name  | VARCHAR(50)  | NOT NULL, UNIQUE  |

---

### 👨‍💼 Employee Table

| Column   | Type           | Constraints                        |
|----------|---------------|----------------------------------|
| emp_id   | INT            | PRIMARY KEY                      |
| name     | VARCHAR(100)   | NOT NULL                         |
| salary   | DECIMAL(10,2)  | CHECK (salary > 0)               |
| doj      | DATE           |                                  |
| dept_id  | INT            | FOREIGN KEY → Department(dept_id)|

---

## ⚙️ Features

- Create and manage company database  
- Establish relationships between tables  
- Perform CRUD operations on employee data  
- Use aggregate functions like `SUM()` and `AVG()`  
- Apply `GROUP BY` and `HAVING` clauses  
- Retrieve combined data using JOIN queries  

---

## 📊 Sample Queries

### 🔍 View Data
```sql
SELECT * FROM Department;


### 🔎 Filter & Sort

```sql
SELECT name, salary
FROM Employee
WHERE salary > 50000
ORDER BY salary DESC;
```

### ✏️ UPDATE

```sql
UPDATE Employee
SET salary = 65000
WHERE emp_id = 104;
```

### 🗑️ DELETE

```sql
DELETE FROM Employee
WHERE emp_id = 107;
```

### 📈 Aggregate

```sql
SELECT dept_id, SUM(salary) AS total_salary
FROM Employee
GROUP BY dept_id;
```

### 🤝 JOIN

```sql
SELECT e.emp_id, e.name AS employee_name, e.salary, d.dept_name AS department_name
FROM Employee e
JOIN Department d ON e.dept_id = d.dept_id;
```

---

## 📂 How to Run

1. Install MySQL and open any MySQL client (Workbench / CLI / phpMyAdmin)
2. Run the provided SQL script step by step
3. Query the tables to test

---

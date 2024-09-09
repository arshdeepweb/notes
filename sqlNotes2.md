# SQL Guide from Beginner to Advanced

This guide covers SQL concepts from beginner to advanced levels, combining insights from multiple resources including *Complete SQL Tutorial in Hindi by Rishabh Mishra*.

## Table of Contents

- [Introduction to SQL](#introduction-to-sql)
- [Data Types, Keys, and Constraints](#data-types-keys-and-constraints)
- [Creating Tables and Databases](#creating-tables-and-databases)
- [Inserting, Updating, and Deleting Data](#inserting-updating-and-deleting-data)
- [Querying Data with SELECT & WHERE](#querying-data-with-select-and-where)
- [Functions in SQL](#functions-in-sql)
- [Joins in SQL](#joins-in-sql)
- [Subqueries](#subqueries)
- [Advanced Concepts](#advanced-concepts)
- [Best Practices and Next Steps](#best-practices-and-next-steps)

---

## 1. Introduction to SQL

**SQL (Structured Query Language)** is a programming language designed for managing and manipulating databases.

- **Applications:** CRUD operations (Create, Read, Update, Delete) on databases.
- **SQL vs NoSQL:** SQL databases have structured schemas; NoSQL provides flexibility with dynamic schemas.
- **Basic SQL Commands:**
  - **DDL (Data Definition Language):** `CREATE`, `ALTER`, `DROP`
  - **DML (Data Manipulation Language):** `SELECT`, `INSERT`, `UPDATE`, `DELETE`
  - **DCL (Data Control Language):** `GRANT`, `REVOKE`

---

## 2. Data Types, Keys, and Constraints

### Data Types:
- **String:** `char`, `varchar`
- **Numeric:** `int`, `float`
- **Date and Time:** `date`, `datetime`

### Keys:
- **Primary Key:** A unique identifier for table records (cannot be `NULL`).
- **Foreign Key:** Links two tables and establishes relationships between them.

### Constraints:
- **NOT NULL, UNIQUE, PRIMARY KEY, FOREIGN KEY**
- **CHECK, DEFAULT, CREATE INDEX**

---

## 3. Creating Tables and Databases

### Create Database:
```sql
CREATE DATABASE db_name;
Create Table:
sql
Copy code
CREATE TABLE table_name (
    column1 datatype constraint,
    column2 datatype constraint,
    ...
);
Example:

sql
Copy code
CREATE TABLE customer (
    CustID int PRIMARY KEY,
    CustName varchar(50) NOT NULL,
    Age int,
    City varchar(50),
    Salary float
);

```
## 4. Inserting, Updating, and Deleting Data

### Insert :
```
INSERT INTO customer (CustID, CustName, Age, City, Salary)
VALUES (1, 'Sam', 26, 'Delhi', 5000);
```
### Update:
```
UPDATE customer SET Salary = 6000 WHERE CustID = 1;
```
### Delete:
```
DELETE FROM customer WHERE CustID = 1;
```

## 5. Querying Data with SELECT & WHERE
### Select:
```
SELECT * FROM customer;
```

### Select Specific Columns:
```
SELECT CustID, CustName FROM customer;
```

### Where Clause:
## Filters records based on conditions.
```
SELECT * FROM customer
WHERE Age > 25;
```


### Where Clause with Multiple Conditions:
```
SELECT * FROM customer
WHERE Age > 25 AND City = 'Delhi';
```

## Operators:
```
Arithmetic: +, -, *, /
Comparison: =, !=, >, <
Logical: AND, OR, NOT
```

## 6. Functions in SQL
### String Functions:
- **UPPER() :** Convert text to uppercase.

```bash
SELECT UPPER(CustName) FROM customer;
```

- **LOWER()**: Convert text to lowercase.
```
SELECT LOWER(CustName) FROM customer;
```
### Aggregate Functions:
- **COUNT()**: Count the number of rows.

```
SELECT COUNT(*) FROM customer;
```
- **SUM() :** Calculate the sum of a numeric column.

```
SELECT SUM(Salary) FROM customer;
```
- **AVG() :** Calculate the average value.

```
SELECT AVG(Salary) FROM customer;
```
- **MIN() :** Find the minimum value.

```
SELECT MIN(Salary) FROM customer;
```
- **MAX() :** Find the maximum value.

```
SELECT MAX(Salary) FROM customer;
```
### Group By & Having:

```
SELECT City, SUM(Salary) FROM customer
```

### GROUP BY City;
## 7. Joins in SQL
Joins combine rows from two or more tables based on related columns.


### Inner Join:
```
SELECT a.*, b.* FROM tableA a INNER JOIN tableB b ON a.id = b.id;
```

### Left Join:
Returns all records from the left table, and matched records from the right table.

```
SELECT a.*, b.* FROM tableA a LEFT JOIN tableB b ON a.id = b.id;
```

### Right Join:
Returns all records from the right table, and matched records from the left table.

```
SELECT a.*, b.* FROM tableA a RIGHT JOIN tableB b ON a.id = b.id;
```

### Full Join:
Returns all records when there is a match in either table.


```
SELECT a.*, b.* FROM tableA a FULL OUTER JOIN tableB b ON a.id = b.id;
```

## 8. Subqueries
A subquery is a query inside another query.

### Example:
```
SELECT * FROM customer WHERE Salary > (SELECT AVG(Salary) FROM customer);
```
## 9. Advanced Concepts
### Window Functions:
Perform calculations across a set of rows related to the current row.

```
SELECT CustID, Salary, AVG(Salary) OVER(PARTITION BY City)
FROM customer;
```
### Common Table Expressions (CTE):
Temporary result sets you can reference in queries.

```
WITH my_cte AS (SELECT CustID, Salary FROM customer)
```
```
SELECT * FROM my_cte;
```
## 10. Best Practices and Next Steps
Practice SQL Joins, Window Functions, and CTEs for advanced database manipulation.

Review SQL Interview Questions for practical applications.
Example Practice Queries:

**Get all customers from 'Delhi' and their respective salaries:**

```
SELECT CustName, Salary FROM customer WHERE City = 'Delhi';
```

**List all customers with a salary greater than the average salary:**

```
SELECT CustName, Salary FROM customer WHERE Salary > (SELECT AVG(Salary) FROM customer);
```

**Group customers by city and calculate the total salary per city:**


```
SELECT City, SUM(Salary) AS TotalSalary FROM customer GROUP BY City;
```

** Find the highest salary per city: **

```
SELECT City, MAX(Salary) AS HighestSalary FROM customer GROUP BY City;
```

## Happy Learning! 🎓
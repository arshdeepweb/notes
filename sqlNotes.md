# SQL Command Cheat Sheet

This document provides a quick reference guide for commonly used SQL commands, along with their syntax and examples. 

## Table of Contents

1. [Show Databases](#show-databases)
2. [Create Database](#create-database)
3. [Drop Database](#drop-database)
4. [Use Database](#use-database)
5. [Create Table](#create-table)
6. [Show All Tables](#show-all-tables)
7. [Describe Table](#describe-table)
8. [Table Alter](#table-alter)
    - [Add Column](#add-column)
    - [Modify Column](#modify-column)
    - [Rename Column](#rename-column)
    - [Delete Column](#delete-column)
9. [Show Table Values](#show-table-values)
10. [Insert Data](#insert-data)
    - [Single Column Values](#single-column-values)
    - [Multiple Values](#multiple-values)
11. [Update Values](#update-values)
12. [Delete Values](#delete-values)
13. [Select and Alias](#select-and-alias)
    - [Select All Columns](#select-all-columns)
    - [Select Selected Columns](#select-selected-columns)
    - [Temporary Names](#temporary-names)
14. [Select with Conditions](#select-with-conditions)
    - [AND Command](#and-command)
    - [OR Command](#or-command)
    - [NOT Command](#not-command)
15. [Order By](#order-by)
    - [Ascending Order](#ascending-order)
    - [Descending Order](#descending-order)
    - [Two Conditions](#two-conditions)
16. [LIMIT Condition](#limit-condition)
17. [Aggregate Functions](#aggregate-functions)
    - [AVG](#avg)
    - [SUM](#sum)
    - [COUNT](#count)

---

## Show Databases

- **Description:** Display all databases.
- **Syntax:** `SHOW DATABASES;`
- **Example:** `SHOW DATABASES;`

## Create Database

- **Description:** Create a new database.
- **Syntax:** `CREATE DATABASE [dbname];`
- **Example:** `CREATE DATABASE mydatabase;`

## Drop Database

- **Description:** Delete a database.
- **Syntax:** `DROP DATABASE [dbname];`
- **Example:** `DROP DATABASE mydatabase;`

## Use Database

- **Description:** Select a database to use.
- **Syntax:** `USE [dbname];`
- **Example:** `USE mydatabase;`

## Create Table

- **Description:** Create a new table.
- **Syntax:** `CREATE TABLE [tablename] (col1 colType(size) extra...);`
- **Example:** `CREATE TABLE users (id INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(100), age INT);`

## Show All Tables

- **Description:** Display all tables in the current database.
- **Syntax:** `SHOW TABLES;`
- **Example:** `SHOW TABLES;`

## Describe Table

- **Description:** Describe the structure of a table.
- **Syntax:** `DESC [tablename];`
- **Example:** `DESC users;`

## Table Alter

### Add Column

- **Description:** Add a new column to an existing table.
- **Syntax:** `ALTER TABLE [tablename] ADD [column_name] datatype;`
- **Example:** `ALTER TABLE users ADD email VARCHAR(100);`

### Modify Column

- **Description:** Modify the datatype of an existing column.
- **Syntax:** `ALTER TABLE [tablename] MODIFY [column_name] [new datatype];`
- **Example:** `ALTER TABLE users MODIFY age TINYINT;`

### Rename Column

- **Description:** Rename an existing column.
- **Syntax:** `ALTER TABLE [tablename] RENAME COLUMN [oldcolumnname] TO [newcolumnname];`
- **Example:** `ALTER TABLE users RENAME COLUMN name TO fullname;`

### Delete Column

- **Description:** Remove a column from a table.
- **Syntax:** `ALTER TABLE [tablename] DROP [column_name];`
- **Example:** `ALTER TABLE users DROP email;`

## Show Table Values

- **Description:** Display all records from a table.
- **Syntax:** `SELECT * FROM [tableName];`
- **Example:** `SELECT * FROM users;`

## Insert Data

### Single Column Values

- **Description:** Insert a single row of data into a table.
- **Syntax:** `INSERT INTO [tableName] (cols) VALUES (values);`
- **Example:** `INSERT INTO users (name, age) VALUES ('John Doe', 30);`

### Multiple Values

- **Description:** Insert multiple rows of data into a table.
- **Syntax:** `INSERT INTO [tableName] (cols) VALUES (values), (values), (values);`
- **Example:** `INSERT INTO users (name, age) VALUES ('Alice', 25), ('Bob', 27);`

## Update Values

- **Description:** Update existing records in a table.
- **Syntax:** `UPDATE [tableName] SET col1 = value, col2 = value WHERE [colName] = ?;`
- **Example:** `UPDATE users SET age = 31 WHERE name = 'John Doe';`

## Delete Values

- **Description:** Delete records from a table.
- **Syntax:** `DELETE FROM [tableName] WHERE [colName] = ?;`
- **Example:** `DELETE FROM users WHERE name = 'John Doe';`

## Select and Alias

### Select All Columns

- **Description:** Select all columns from a table.
- **Syntax:** `SELECT * FROM [tableName];`
- **Example:** `SELECT * FROM users;`

### Select Selected Columns

- **Description:** Select specific columns from a table.
- **Syntax:** `SELECT [column1], [column2] FROM [tableName];`
- **Example:** `SELECT name, age FROM users;`

### Temporary Names

- **Description:** Assign a temporary name to columns or tables for readability.
- **Syntax:** `SELECT [column_name] AS [temporary_column_name] FROM [tableName] AS [temporary_table_name];`
- **Example:** `SELECT name AS fullname FROM users AS u;`

## Select with Conditions

### AND Command

- **Description:** Use AND to filter records based on multiple conditions.
- **Syntax:** `SELECT * FROM [tableName] WHERE condition1 AND condition2;`
- **Example:** `SELECT * FROM users WHERE city = 'Khem Karan' AND name = 'Karan';`

### OR Command

- **Description:** Use OR to filter records based on alternative conditions.
- **Syntax:** `SELECT * FROM [tableName] WHERE condition1 OR condition2;`
- **Example:** `SELECT * FROM users WHERE city = 'Khem Karan' OR name = 'Karan';`

### NOT Command

- **Description:** Use NOT to exclude records based on a condition.
- **Syntax:** `SELECT * FROM [tableName] WHERE NOT condition;`
- **Example:** `SELECT * FROM users WHERE NOT city = 'Khem Karan';`

## Order By

### Ascending Order

- **Description:** Order records in ascending order based on a column.
- **Syntax:** `SELECT * FROM [tableName] ORDER BY [columnName];`
- **Example:** `SELECT * FROM users ORDER BY name;`

### Descending Order

- **Description:** Order records in descending order based on a column.
- **Syntax:** `SELECT * FROM [tableName] ORDER BY [columnName] DESC;`
- **Example:** `SELECT * FROM users ORDER BY name DESC;`

### Two Conditions

- **Description:** Order records based on multiple columns.
- **Syntax:** `SELECT * FROM [tableName] ORDER BY [column1] DESC, [column2] ASC;`
- **Example:** `SELECT * FROM users ORDER BY name DESC, age ASC;`

## LIMIT Condition

- **Description:** Limit the number of records returned.
- **Syntax:** `SELECT * FROM [tableName] LIMIT [number];`
- **Example:** `SELECT * FROM users LIMIT 3;`

- **Description:** Limit records with offset.
- **Syntax:** `SELECT * FROM [tableName] LIMIT [number] OFFSET [offset];`
- **Example:** `SELECT * FROM users LIMIT 3 OFFSET 2;`

- **Description:** Combine ORDER BY with LIMIT and OFFSET.
- **Syntax:** `SELECT * FROM [tableName] ORDER BY [column] DESC LIMIT [number] OFFSET [offset];`
- **Example:** `SELECT * FROM users ORDER BY name DESC LIMIT 3 OFFSET 2;`

## Aggregate Functions

### AVG

- **Description:** Calculate the average value of a column.
- **Syntax:** `SELECT AVG([columnName]) FROM [tableName];`
- **Example:** `SELECT AVG(age) FROM users;`

### SUM

- **Description:** Calculate the sum of a column.
- **Syntax:** `SELECT SUM([columnName]) FROM [tableName];`
- **Example:** `SELECT SUM(fees) FROM users;`

### COUNT

- **Description:** Count the number of rows in a table.
- **Syntax:** `SELECT COUNT([columnName]) FROM [tableName];`
- **Example:** `SELECT COUNT(name) FROM users;`

---

This cheat sheet provides a comprehensive overview of essential SQL commands for database management and querying. Feel free to expand or adjust it based on your needs!

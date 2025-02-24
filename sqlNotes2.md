# MySQL Step-by-Step Guide

## 1. Introduction to MySQL
### What is MySQL?
- MySQL is an open-source relational database management system (RDBMS) based on Structured Query Language (SQL).
- It is used to store, retrieve, manage, and manipulate structured data efficiently.

### Installation
- Download MySQL from [MySQL Official Website](https://dev.mysql.com/downloads/).
- Install MySQL Server and MySQL Workbench for database management.
- Verify installation by running:
  ```sh
  mysql --version
  ```

## 2. Creating and Managing Databases
### Creating a Database
```sql
CREATE DATABASE database_name;
```
### Viewing Databases
```sql
SHOW DATABASES;
```
### Using a Database
```sql
USE database_name;
```
### Dropping a Database
```sql
DROP DATABASE database_name;
```

## 3. Creating and Managing Tables
### Creating a Table
```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    age INT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```
### Viewing Tables
```sql
SHOW TABLES;
```
### Describing Table Structure
```sql
DESC users;
```
### Dropping a Table
```sql
DROP TABLE users;
```

## 4. SQL Data Types
- **Integer Types:** `TINYINT`, `SMALLINT`, `MEDIUMINT`, `INT`, `BIGINT`
- **String Types:** `CHAR`, `VARCHAR`, `TEXT`
- **Date & Time:** `DATE`, `DATETIME`, `TIMESTAMP`
- **Boolean:** `BOOLEAN`

## 5. SQL Constraints
- `PRIMARY KEY`: Uniquely identifies a record.
- `FOREIGN KEY`: Establishes a relationship with another table.
- `NOT NULL`: Ensures a column cannot have NULL values.
- `UNIQUE`: Ensures all values in a column are unique.
- `DEFAULT`: Assigns a default value if none is provided.
- `CHECK`: Ensures values meet a specific condition.

## 6. Data Manipulation (CRUD Operations)
### Inserting Data
```sql
INSERT INTO users (name, email, age) VALUES ('John Doe', 'john@example.com', 25);
```
### Selecting Data
```sql
SELECT * FROM users;
SELECT name, email FROM users WHERE age > 20;
```
### Updating Data
```sql
UPDATE users SET age = 30 WHERE name = 'John Doe';
```
### Deleting Data
```sql
DELETE FROM users WHERE id = 1;
```

## 7. SQL Clauses
### Ordering Results
```sql
SELECT * FROM users ORDER BY age DESC;
```
### Limiting Results
```sql
SELECT * FROM users LIMIT 5;
```
### Grouping Data
```sql
SELECT age, COUNT(*) FROM users GROUP BY age;
```
### Filtering Grouped Data
```sql
SELECT age, COUNT(*) FROM users GROUP BY age HAVING COUNT(*) > 2;
```

## 8. Joins in MySQL
### Inner Join
```sql
SELECT users.name, orders.order_id FROM users
INNER JOIN orders ON users.id = orders.user_id;
```
### Left Join
```sql
SELECT users.name, orders.order_id FROM users
LEFT JOIN orders ON users.id = orders.user_id;
```
### Right Join
```sql
SELECT users.name, orders.order_id FROM users
RIGHT JOIN orders ON users.id = orders.user_id;
```
### Full Join (Using UNION)
```sql
SELECT users.name, orders.order_id FROM users
LEFT JOIN orders ON users.id = orders.user_id
UNION
SELECT users.name, orders.order_id FROM users
RIGHT JOIN orders ON users.id = orders.user_id;
```

## 9. Subqueries
```sql
SELECT name FROM users WHERE age > (SELECT AVG(age) FROM users);
```

## 10. Indexing
```sql
CREATE INDEX idx_name ON users(name);
```

## 11. Transactions
```sql
START TRANSACTION;
UPDATE users SET age = 35 WHERE name = 'John Doe';
ROLLBACK;
COMMIT;
```

## 12. Views
```sql
CREATE VIEW user_view AS SELECT name, email FROM users;
```

## 13. Foreign Key Cascading
```sql
CREATE TABLE orders (
    order_id INT PRIMARY KEY,
    user_id INT,
    FOREIGN KEY (user_id) REFERENCES users(id) ON DELETE CASCADE
);
```

## 14. Backup and Restore
### Backup
```sh
mysqldump -u root -p database_name > backup.sql
```
### Restore
```sh
mysql -u root -p database_name < backup.sql
```

## Conclusion
This step-by-step guide provides a solid foundation for working with MySQL. Continue practicing queries and database management techniques to improve your skills!


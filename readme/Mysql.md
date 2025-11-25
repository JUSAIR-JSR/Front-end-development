🛢️ MySQL — Complete Beginner to Advanced Database Course

(Full README)

📌 Table of Contents

What is MySQL?

Install MySQL

MySQL Shell / Workbench

Database Basics

Create / Drop Database

Tables

Data Types

Insert Data

Select Queries

WHERE Conditions

AND, OR, NOT

ORDER BY

LIMIT

UPDATE

DELETE

Functions

LIKE (search)

JOIN (INNER, LEFT, RIGHT)

PRIMARY KEY / FOREIGN KEY

Constraints

INDEX

AUTO_INCREMENT

Aggregate Functions

GROUP BY

HAVING

Subqueries

Views

Stored Procedures

Triggers

Transactions

Backup & Restore

MySQL with Python

MySQL with Node.js

MySQL with Django

Final Projects

1️⃣ What is MySQL?

MySQL is a relational database system used to store structured data.

Used in:

✔ Web apps
✔ E-commerce
✔ Banking
✔ Python/Node/Django/React projects
✔ APIs

2️⃣ Install MySQL

Download from:
https://dev.mysql.com

Check version:

mysql --version

3️⃣ Open MySQL Shell
mysql -u root -p

4️⃣ Create Database
CREATE DATABASE school;


Show databases:

SHOW DATABASES;


Use database:

USE school;


Drop database:

DROP DATABASE school;

5️⃣ Create Table
CREATE TABLE students (
    id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(100),
    age INT,
    email VARCHAR(100)
);


Show tables:

SHOW TABLES;

6️⃣ Data Types
Type	Example	Use
INT	10	numbers
VARCHAR(255)	"John"	text
TEXT	long text	blogs
DATE	2025-01-01	date
DATETIME	timestamp	logs
BOOLEAN	true/false	flags
FLOAT/DOUBLE	1.23	decimal
7️⃣ Insert Data
INSERT INTO students (name, age, email)
VALUES ("John", 20, "john@email.com");


Multiple insert:

INSERT INTO students (name, age) VALUES
("A", 10),
("B", 15),
("C", 18);

8️⃣ Select Query
SELECT * FROM students;


Select specific columns:

SELECT name, age FROM students;

9️⃣ WHERE Condition
SELECT * FROM students WHERE age > 15;

🔟 AND, OR, NOT
SELECT * FROM students WHERE age > 15 AND name="John";

SELECT * FROM students WHERE age < 18 OR name="A";

SELECT * FROM students WHERE NOT age = 20;

1️⃣1️⃣ ORDER BY
SELECT * FROM students ORDER BY age ASC;
SELECT * FROM students ORDER BY name DESC;

1️⃣2️⃣ LIMIT
SELECT * FROM students LIMIT 5;

1️⃣3️⃣ UPDATE
UPDATE students SET age=25 WHERE id=1;

1️⃣4️⃣ DELETE
DELETE FROM students WHERE id=1;

1️⃣5️⃣ LIKE (search)
SELECT * FROM students WHERE name LIKE "J%";   -- starts with J
SELECT * FROM students WHERE name LIKE "%n";   -- ends with n
SELECT * FROM students WHERE name LIKE "%oh%"; -- contains oh

1️⃣6️⃣ Aggregate Functions
SELECT COUNT(*) FROM students;
SELECT MAX(age) FROM students;
SELECT MIN(age) FROM students;
SELECT AVG(age) FROM students;
SELECT SUM(age) FROM students;

1️⃣7️⃣ GROUP BY
SELECT age, COUNT(*) FROM students GROUP BY age;

1️⃣8️⃣ HAVING

Used with GROUP BY:

SELECT age, COUNT(*)
FROM students
GROUP BY age
HAVING COUNT(*) > 2;

1️⃣9️⃣ Primary & Foreign Keys
Parent table:
CREATE TABLE departments (
  id INT PRIMARY KEY,
  department_name VARCHAR(100)
);

Child table:
CREATE TABLE employees (
  id INT PRIMARY KEY,
  name VARCHAR(100),
  dept_id INT,
  FOREIGN KEY (dept_id) REFERENCES departments(id)
);

2️⃣0️⃣ JOIN
INNER JOIN
SELECT employees.name, departments.department_name
FROM employees
INNER JOIN departments
ON employees.dept_id = departments.id;

LEFT JOIN
SELECT *
FROM employees
LEFT JOIN departments
ON employees.dept_id = departments.id;

2️⃣1️⃣ INDEX
CREATE INDEX idx_name ON students(name);

2️⃣2️⃣ AUTO_INCREMENT
id INT PRIMARY KEY AUTO_INCREMENT

2️⃣3️⃣ Views
CREATE VIEW student_view AS
SELECT name, age FROM students;

2️⃣4️⃣ Stored Procedures
DELIMITER //
CREATE PROCEDURE GetStudents()
BEGIN
  SELECT * FROM students;
END //
DELIMITER ;


Run:

CALL GetStudents();

2️⃣5️⃣ Triggers
CREATE TRIGGER before_insert
BEFORE INSERT ON students
FOR EACH ROW
SET NEW.name = UPPER(NEW.name);

2️⃣6️⃣ Transactions
START TRANSACTION;

UPDATE students SET age = 30 WHERE id = 1;

COMMIT; -- or ROLLBACK;

2️⃣7️⃣ Backup & Restore
Backup:
mysqldump -u root -p school > backup.sql

Restore:
mysql -u root -p school < backup.sql

2️⃣8️⃣ MySQL + Python

Install:

pip install mysql-connector-python


Connect:

import mysql.connector
db = mysql.connector.connect(
    host="localhost",
    user="root",
    password="",
    database="school"
)

2️⃣9️⃣ MySQL + Node.js (Express)

Install:

npm install mysql2


Use:

import mysql from "mysql2";

const db = mysql.createConnection({
  host:"localhost",
  user:"root",
  password:"",
  database:"school"
});

3️⃣0️⃣ MySQL + Django

Install:

pip install mysqlclient


settings.py:

DATABASES = {
 'default': {
   'ENGINE': 'django.db.backends.mysql',
   'NAME': 'school',
   'USER': 'root',
   'PASSWORD': '',
   'HOST': 'localhost',
 }
}

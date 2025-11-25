📘 PostgreSQL Course — Complete Beginner to Advanced Guide

Modern PostgreSQL (psql + SQL + indexing + relations + functions + joins + optimization)
Use this as your PostgreSQL.md, README.md, or PostgreSQL course page.

📚 Table of Contents

What is PostgreSQL?

Install PostgreSQL

PostgreSQL GUI tools (pgAdmin / TablePlus / DBeaver)

Connecting to PostgreSQL (psql)

Creating database, tables

CRUD operations

Data types

Constraints

Keys (Primary, Foreign)

Joins

Functions

Views

Indexes

Stored Procedures

Transactions

Aggregations

Operators

Backup & Restore

User management & permissions

Advanced topics

Real-world project example

Useful commands cheat sheet

1️⃣ What is PostgreSQL?

PostgreSQL is a powerful open-source relational database known for:

✓ SQL compliance
✓ High performance
✓ JSON support
✓ Indexing & full-text search
✓ Enterprise reliability

Used by: Instagram, GitHub, Apple, Reddit, Spotify.

2️⃣ Install PostgreSQL
Windows / Mac / Linux installer

https://www.postgresql.org/download/

Installer includes:

PostgreSQL Server

pgAdmin (GUI)

Command line tool (psql)

3️⃣ GUI Tools for PostgreSQL

Use any:

✓ pgAdmin (official & free)
✓ TablePlus (best UI)
✓ DBeaver (advanced)
✓ DataGrip (JetBrains)
4️⃣ Connect to PostgreSQL (psql)
psql -U postgres


List databases:

\l


Connect:

\c mydatabase;

5️⃣ Create Database & Tables
Create a database:
CREATE DATABASE students_db;

Create a table:
CREATE TABLE students (
  id SERIAL PRIMARY KEY,
  name VARCHAR(50),
  age INT,
  city VARCHAR(50)
);

6️⃣ CRUD Operations
Insert data:
INSERT INTO students (name, age, city)
VALUES ('Rahul', 21, 'Delhi');

Read data:
SELECT * FROM students;

Update:
UPDATE students SET city='Mumbai' WHERE id=1;

Delete:
DELETE FROM students WHERE id=1;

7️⃣ PostgreSQL Data Types

Common types:

Type	Example
INTEGER	1
SERIAL	Auto increment
VARCHAR(n)	'Hello'
TEXT	Paragraphs
BOOLEAN	TRUE/FALSE
DATE	'2025-10-05'
TIMESTAMP	'2025-10-05 10:30'
JSON / JSONB	{"name": "Ali"}
8️⃣ Constraints
NOT NULL  
UNIQUE  
PRIMARY KEY  
FOREIGN KEY  
CHECK  
DEFAULT  


Example:

CREATE TABLE users(
   id SERIAL PRIMARY KEY,
   email VARCHAR(60) UNIQUE NOT NULL,
   age INT CHECK(age > 0)
);

9️⃣ Primary & Foreign Keys
Primary Key
id SERIAL PRIMARY KEY

Foreign Key
CREATE TABLE orders(
  id SERIAL PRIMARY KEY,
  user_id INT REFERENCES users(id)
);

🔟 JOINS
Inner Join
SELECT users.name, orders.amount
FROM users
INNER JOIN orders ON users.id = orders.user_id;

Left Join
SELECT * FROM users
LEFT JOIN orders ON users.id = orders.user_id;

1️⃣1️⃣ Functions (Built-in + Custom)
Built-in functions
SELECT COUNT(*), MAX(age), MIN(age) FROM students;

Custom function
CREATE FUNCTION get_student_count()
RETURNS INT AS $$
  SELECT COUNT(*) FROM students;
$$ LANGUAGE SQL;

1️⃣2️⃣ Views

Virtual tables:

CREATE VIEW student_view AS
SELECT name, city FROM students;


Get data:

SELECT * FROM student_view;

1️⃣3️⃣ Indexes (Performance)
CREATE INDEX idx_student_city
ON students(city);


Improves search speed.

1️⃣4️⃣ Stored Procedures
CREATE PROCEDURE add_student(n varchar, a int)
LANGUAGE SQL
AS $$
  INSERT INTO students(name, age)
  VALUES (n, a);
$$;


Call:

CALL add_student('Ahmed', 22);

1️⃣5️⃣ Transactions

All-or-nothing operations:

BEGIN;
UPDATE accounts SET balance = balance - 100 WHERE id=1;
UPDATE accounts SET balance = balance + 100 WHERE id=2;
COMMIT;


Rollback:

ROLLBACK;

1️⃣6️⃣ Aggregations
SELECT COUNT(*), SUM(age), AVG(age)
FROM students;

1️⃣7️⃣ Operators
Comparison

=, !=, >, <, >=, <=

Logical

AND, OR, NOT

Pattern Matching
SELECT * FROM students WHERE name LIKE 'A%';

1️⃣8️⃣ Backup & Restore
Backup:
pg_dump students_db > backup.sql

Restore:
psql students_db < backup.sql

1️⃣9️⃣ User Management

Create user:

CREATE USER test WITH PASSWORD '1234';


Grant permissions:

GRANT ALL PRIVILEGES ON DATABASE students_db TO test;


Revoke:

REVOKE ALL PRIVILEGES ON DATABASE students_db FROM test;

2️⃣0️⃣ Advanced PostgreSQL Topics

You will learn:

✔ JSONB usage
✔ Full-text search (TSVECTOR)
✔ Views & Materialized views
✔ Triggers
✔ CTE (WITH clause)
✔ Window functions
✔ Query optimization & EXPLAIN ANALYZE
✔ Partitioning

2️⃣1️⃣ Real World Project Example
Student Management System

Tables:

students

courses

enrollments

Example ERD:
students (1)───(∞) enrollments (∞)───(1) courses

Create tables:
CREATE TABLE courses(
  id SERIAL PRIMARY KEY,
  title VARCHAR(50)
);

CREATE TABLE enrollments(
  id SERIAL PRIMARY KEY,
  student_id INT REFERENCES students(id),
  course_id INT REFERENCES courses(id)
);

List all enrolled students:
SELECT students.name, courses.title 
FROM enrollments
JOIN students ON enrollments.student_id = students.id
JOIN courses ON enrollments.course_id = courses.id;

2️⃣2️⃣ PostgreSQL Commands Cheat Sheet
List databases
\l

List tables
\dt

Describe table:
\d students

Clear screen:
\! cls   (windows)
\! clear (mac / linux)

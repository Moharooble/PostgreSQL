# PostgreSQL Operations & SQL Code Examples

---

## 📘 PostgreSQL Introduction

PostgreSQL is a powerful, open-source object-relational database system. It is known for its standards compliance, reliability, and support for advanced data types and performance optimization features.

---

## 🏗️ Create Database

CREATE DATABASE school_db;

yaml
Copy
Edit

This command creates a new database named `school_db`.

---

## 🧱 Create Tables

CREATE TABLE students (
id SERIAL PRIMARY KEY,
name VARCHAR(100),
class_id INT
);

CREATE TABLE classes (
id INT PRIMARY KEY,
class_name VARCHAR(100)
);

yaml
Copy
Edit

These commands create two tables: `students` and `classes`.

---

## 📥 Insert Data

INSERT INTO students (name, class_id) VALUES
('Ali', 101),
('Amina', 102),
('Mahad', 103);

INSERT INTO classes (id, class_name) VALUES
(101, 'Math'),
(102, 'English'),
(104, 'Science');

yaml
Copy
Edit

---

## 📄 Get All Data from Students

SELECT * FROM students;

yaml
Copy
Edit

| id | name  | class_id |
|----|-------|----------|
| 1  | Ali   | 101      |
| 2  | Amina | 102      |
| 3  | Mahad | 103      |

---

## 🔍 Get Single Record

SELECT * FROM students WHERE id = 2;

yaml
Copy
Edit

| id | name  | class_id |
|----|-------|----------|
| 2  | Amina | 102      |

---

## ✏️ Update a Record

UPDATE students
SET name = 'Amina Ali'
WHERE id = 2;

Copy
Edit
SELECT * FROM students WHERE id = 2;

yaml
Copy
Edit

| id | name       | class_id |
|----|------------|----------|
| 2  | Amina Ali  | 102      |

---

## ❌ Delete a Record

DELETE FROM students WHERE id = 1;

Copy
Edit
SELECT * FROM students;

yaml
Copy
Edit

| id | name       | class_id |
|----|------------|----------|
| 2  | Amina Ali  | 102      |
| 3  | Mahad      | 103      |

---

## 🔗 INNER JOIN

SELECT s.name, c.class_name
FROM students s
INNER JOIN classes c ON s.class_id = c.id;

yaml
Copy
Edit

| name       | class_name |
|------------|------------|
| Amina Ali  | English    |

---

## 🔸 LEFT JOIN

SELECT s.name, c.class_name
FROM students s
LEFT JOIN classes c ON s.class_id = c.id;

yaml
Copy
Edit

| name       | class_name |
|------------|------------|
| Amina Ali  | English    |
| Mahad      | NULL       |

---

## 🔸 RIGHT JOIN

SELECT s.name, c.class_name
FROM students s
RIGHT JOIN classes c ON s.class_id = c.id;

yaml
Copy
Edit

| name       | class_name |
|------------|------------|
| Amina Ali  | English    |
| NULL       | Math       |
| NULL       | Science    |

---

## 🟣 FULL OUTER JOIN

SELECT s.name, c.class_name
FROM students s
FULL OUTER JOIN classes c ON s.class_id = c.id;

yaml
Copy
Edit

| name       | class_name |
|------------|------------|
| Amina Ali  | English    |
| Mahad      | NULL       |
| NULL       | Math       |
| NULL       | Science    |

---

## 📊 Count Students per Class

SELECT class_id, COUNT(*) AS total
FROM students
GROUP BY class_id;

yaml
Copy
Edit

| class_id | total |
|----------|--------|
| 102      | 1      |
| 103      | 1      |

---

## 🔠 Order Students by Name

SELECT * FROM students
ORDER BY name ASC;

yaml
Copy
Edit

| id | name       | class_id |
|----|------------|----------|
| 2  | Amina Ali  | 102      |
| 3  | Mahad      | 103      |

---

## 🛠️ Alter Table: Rename Column

ALTER TABLE students
RENAME COLUMN name TO full_name;

Copy
Edit
SELECT * FROM students;

yaml
Copy
Edit

| id | full_name  | class_id |
|----|------------|----------|
| 2  | Amina Ali  | 102      |
| 3  | Mahad      | 103      |

---

## 🧹 Drop Table

DROP TABLE students;

sql
Copy
Edit

Deletes the `students` table from the database.

---

## 📌 Summary

| Operation     | Example                                 |
|---------------|-----------------------------------------|
| Create DB     | CREATE DATABASE db_name;                |
| Create Table  | CREATE TABLE ...                        |
| Insert        | INSERT INTO table VALUES (...);         |
| Select All    | SELECT * FROM table;                    |
| Select One    | SELECT * FROM table WHERE condition;    |
| Update        | UPDATE table SET ... WHERE ...;         |
| Delete        | DELETE FROM table WHERE ...;            |
| Inner Join    | SELECT ... FROM A INNER JOIN B ON ...;  |
| Left Join     | SELECT ... FROM A LEFT JOIN B ON ...;   |
| Right Join    | SELECT ... FROM A RIGHT JOIN B ON ...;  |
| Full Join     | SELECT ... FROM A FULL OUTER JOIN B ON ...; |
| Group & Count | SELECT col, COUNT(*) FROM ... GROUP BY col; |
| Order By      | SELECT * FROM ... ORDER BY col ASC;     |
| Rename Column | ALTER TABLE table RENAME COLUMN a TO b; |
| Drop Table    | DROP TABLE table_name;                  |

---
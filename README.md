# PostgreSQL CRUD Operations & Joins Explained

This repository demonstrates PostgreSQL CRUD operations and join types using sample student/class data. The examples show practical SQL syntax with real query results.

## Sample Data

### Students Table
| id | name  | class_id |
|----|-------|----------|
| 1  | Ali   | 101      |
| 2  | Amina | 102      |
| 3  | Mahad | 103      |

### Classes Table
| id  | class_name |
|-----|------------|
| 101 | Math       |
| 102 | English    |
| 104 | Science    |

---

## CRUD Operations
Result:

id	name	class_id
2	Amina	102
### 📝 Create (INSERT)
```sql
-- Add new student
INSERT INTO students (name, class_id) 
VALUES ('Fatima', 104);

-- Add new class
INSERT INTO classes (id, class_name)
VALUES (105, 'History');


......................................


# PostgreSQL Operations & SQL JOINs – SQL Code & Results

---

## 📘 PostgreSQL: Create Database

CREATE DATABASE school_db;

yaml
Copy
Edit

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

## 📄 Get All Students

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

## 🔗 INNER JOIN Example

SELECT s.name, c.class_name
FROM students s
INNER JOIN classes c ON s.class_id = c.id;

pgsql
Copy
Edit

| name  | class_name |
|-------|------------|
| Ali   | Math       |
| Amina | English    |
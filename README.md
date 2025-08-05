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
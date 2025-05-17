# Experiment 2: DDL Commands
## AIM
To study and implement DDL commands and different types of constraints.

## THEORY

### 1. CREATE
Used to create a new relation (table).

**Syntax:**
```sql
CREATE TABLE (
  field_1 data_type(size),
  field_2 data_type(size),
  ...
);
```
### 2. ALTER
Used to add, modify, drop, or rename fields in an existing relation.
(a) ADD
```sql
ALTER TABLE std ADD (Address CHAR(10));
```
(b) MODIFY
```sql
ALTER TABLE relation_name MODIFY (field_1 new_data_type(size));
```
(c) DROP
```sql
ALTER TABLE relation_name DROP COLUMN field_name;
```
(d) RENAME
```sql
ALTER TABLE relation_name RENAME COLUMN old_field_name TO new_field_name;
```
### 3. DROP TABLE
Used to permanently delete the structure and data of a table.
```sql
DROP TABLE relation_name;
```
### 4. RENAME
Used to rename an existing database object.
```sql
RENAME TABLE old_relation_name TO new_relation_name;
```
### CONSTRAINTS
Constraints are used to specify rules for the data in a table. If there is any violation between the constraint and the data action, the action is aborted by the constraint. It can be specified when the table is created (using CREATE TABLE) or after it is created (using ALTER TABLE).
### 1. NOT NULL
When a column is defined as NOT NULL, it becomes mandatory to enter a value in that column.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) NOT NULL
);
```
### 2. UNIQUE
Ensures that values in a column are unique.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) UNIQUE
);
```
### 3. CHECK
Specifies a condition that each row must satisfy.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) CHECK (logical_expression)
);
```
### 4. PRIMARY KEY
Used to uniquely identify each record in a table.
Properties:
Must contain unique values.
Cannot be null.
Should contain minimal fields.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size) PRIMARY KEY
);
```
### 5. FOREIGN KEY
Used to reference the primary key of another table.
Syntax:
```sql
CREATE TABLE Table_Name (
  column_name data_type(size),
  FOREIGN KEY (column_name) REFERENCES other_table(column)
);
```
### 6. DEFAULT
Used to insert a default value into a column if no value is specified.

Syntax:
```sql
CREATE TABLE Table_Name (
  col_name1 data_type,
  col_name2 data_type,
  col_name3 data_type DEFAULT 'default_value'
);
```

**Question 1**
--
![Screenshot (5)](https://github.com/user-attachments/assets/f7d7607d-8baf-4ffe-a214-db98e989df98)


```sql
CREATE TABLE Locations(
LocationID INTEGER,
LocationName TEXT ,
Address TEXT
)
```

**Output:**

![Screenshot (6)](https://github.com/user-attachments/assets/518cf3e1-7e77-4e73-b3b3-e537f9b7de21)

**Question 2**
---
![Screenshot (7)](https://github.com/user-attachments/assets/939c72de-af93-4e07-9e32-386aa4bc5157)


```sql
INSERT INTO Employee(EmployeeID,Name,Position,Department,Salary)
VALUES('001','Sarah Parker','Manager','HR',60000)
```

**Output:**

![Screenshot (8)](https://github.com/user-attachments/assets/ce5fc351-352f-4e34-89a1-40e781ace476)


**Question 3**
---
![Screenshot (9)](https://github.com/user-attachments/assets/64ed3439-f72e-4c6f-9c21-3c858d64d6da)


```sql
CREATE TABLE Products(
ProductID PRIMARY KEY,
ProductName NOT NULL,
Price REAL CHECK(Price>0),
Stock INTEGER CHECK(Stock>0)
)
```

**Output:**

![Screenshot (10)](https://github.com/user-attachments/assets/f7b93714-87e1-4616-ac58-225ebbfa6be0)



**Question 4**
---
![Screenshot (11)](https://github.com/user-attachments/assets/cc6e6d5e-f6b4-4b8f-bea5-7a73e19dd55f)


```sql
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT(4),

FOREIGN KEY  (icom_id) REFERENCES company(com_id)
    ON UPDATE SET NULL
    ON DELETE SET NULL
)
```

**Output:**

![Screenshot (12)](https://github.com/user-attachments/assets/193c4486-be33-477b-a202-a6f1e0bd5415)


**Question 5**
---
![Screenshot (13)](https://github.com/user-attachments/assets/ffdad1e8-7725-45e5-a55e-a19e3a142354)


```sql
INSERT INTO Books(ISBN,Title,Author,Publisher,YearPublished)
SELECT ISBN,Title,Author,Publisher,YearPublished
FROM Out_of_print_books
```

**Output:**

![Screenshot (14)](https://github.com/user-attachments/assets/481433a7-0e39-4298-a8ac-2ffc8daa8e34)

**Question 6**
---
![Screenshot (15)](https://github.com/user-attachments/assets/299a14b8-cd80-4051-988c-46a4f763d0ef)


```sql
ALTER TABLE customer
ADD COLUMN birth_date timestamp
```

**Output:**

![Screenshot (16)](https://github.com/user-attachments/assets/a72fc7dc-a78a-4a57-88f7-66aeaffd5987)

**Question 7**
---
![Screenshot (17)](https://github.com/user-attachments/assets/ced5aed5-0fe7-4665-8c4c-55591e48398f)


```sql
ALTER TABLE Companies
ADD COLUMN designation varchar(50);

ALTER TABLE Companies
ADD COLUMN net_salary number;

ALTER TABLE Companies
ADD COLUMN dob date;
```

**Output:**

![Screenshot (18)](https://github.com/user-attachments/assets/ccaf83ba-02c7-46ee-9254-315d8cf08849)

**Question 8**
---
![Screenshot (19)](https://github.com/user-attachments/assets/eb820353-6a29-410f-bc8f-a73d19e1a835)

```sql
CREATE TABLE products(
product_id INTEGER PRIMARY KEY,
product_name TEXT NOT NULL,
list_price DECIMAL(10 ,2) NOT NULL,
discount DECIMAL(10,2) NOT NULL DEFAULT 0,
CHECK(list_price>=discount and discount>=0 and list_price >=0)
)
```

**Output:**

![Screenshot (20)](https://github.com/user-attachments/assets/9d638414-d6d4-42bb-8711-c0474a3bda16)


**Question 9**
---
![Screenshot (21)](https://github.com/user-attachments/assets/55d7d893-4c0c-4fab-9f62-4895697b4d4a)


```sql
CREATE TABLE item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT(4),
FOREIGN KEY (icom_id) REFERENCES company(com_id)
    ON UPDATE CASCADE
    ON DELETE CASCADE
)
```

**Output:**

![Screenshot (22)](https://github.com/user-attachments/assets/2693f1ba-52cf-450d-aeb9-951d141a52e4)


**Question 10**
---
![Screenshot (23)](https://github.com/user-attachments/assets/36b2dc60-2fda-4d18-a29d-7de2543b065a)


```sql
CREATE TABLE Events(
EventID INTEGER,
EventName TEXT,
EventDate DATE
)
```

**Output:**

![Screenshot (24)](https://github.com/user-attachments/assets/be484bf8-4e90-459b-a310-dd07ca51b55c)



## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

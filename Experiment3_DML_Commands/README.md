# Experiment 3: DML Commands
## AIM
To study and implement DML (Data Manipulation Language) commands.

## THEORY

### 1. INSERT INTO
Used to add records into a relation.
These are three type of INSERT INTO queries which are as
A)Inserting a single record
**Syntax (Single Row):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES (value_1, value_2, ...);
```
**Syntax (Multiple Rows):**
```sql
INSERT INTO table_name (field_1, field_2, ...) VALUES
(value_1, value_2, ...),
(value_3, value_4, ...);
```
**Syntax (Insert from another table):**
```sql
INSERT INTO table_name SELECT * FROM other_table WHERE condition;
```
### 2. UPDATE
Used to modify records in a relation.
Syntax:
```sql
UPDATE table_name SET column1 = value1, column2 = value2 WHERE condition;
```
### 3. DELETE
Used to delete records from a relation.
**Syntax (All rows):**
```sql
DELETE FROM table_name;
```
**Syntax (Specific condition):**
```sql
DELETE FROM table_name WHERE condition;
```
### 4. SELECT
Used to retrieve records from a table.
**Syntax:**
```sql
SELECT column1, column2 FROM table_name WHERE condition;
```
**Question 1**
--
![Screenshot (26)](https://github.com/user-attachments/assets/1138cba3-50d5-4223-89c3-ff5209f8c9b2)


```sql
UPDATE products
SET availability=availability*2
WHERE product_id=1;
```

**Output:**

![Screenshot (27)](https://github.com/user-attachments/assets/efa3d479-9d89-4114-aae9-a9bb7db8248f)


**Question 2**
---
![Screenshot (28)](https://github.com/user-attachments/assets/6a8ac243-6105-4f2b-b290-680f09fb4c35)


```sql
UPDATE Employees
SET SALARY = SALARY * 2
WHERE job_id ='MK_MAN' and department_id=20;
```

**Output:**

![Screenshot (29)](https://github.com/user-attachments/assets/2cd6d5fb-a5a2-412d-bfaf-f73420338c99)


**Question 3**
---
![Screenshot (30)](https://github.com/user-attachments/assets/75955293-e7bb-4b5b-88f3-be6ab1de1465)

```sql
UPDATE suppliers
SET supplier_name=UPPER(supplier_name)
WHERE contact_person LIKE '%Singh%'
```

**Output:**

![Screenshot (31)](https://github.com/user-attachments/assets/974cdd22-3899-42f7-88bd-8a5d65ad96bd)


**Question 4**
---
![Screenshot (32)](https://github.com/user-attachments/assets/90c6573a-d1e0-436d-b519-59712afcf2a3)

```sql
UPDATE Products
SET sell_price=CAST(cost_price*1.35 AS INTEGER)
WHERE((sell_price-cost_price)/sell_price)<0.30;
```

**Output:**

![Screenshot (33)](https://github.com/user-attachments/assets/7f148668-48da-4d0b-ba82-819d42a4ee4f)


**Question 5**
---
![Screenshot (34)](https://github.com/user-attachments/assets/1df1c235-fcfe-44b7-b432-35f8f770f114)

```sql
DELETE FROM Customer
WHERE (GRADE IS '2' AND CUST_NAME LIKE 'M%') AND PAYMENT_AMT <5000;
```

**Output:**

![Screenshot (35)](https://github.com/user-attachments/assets/82eba1f2-9a94-4e0a-857c-f487b2de9612)

**Question 6**
---
![Screenshot (36)](https://github.com/user-attachments/assets/a09f4a56-d22b-4483-a996-404d20661e86)


```sql
DELETE FROM Customer
WHERE CUST_COUNTRY NOT IN ('UK','USA','Canada') AND GRADE >=3;
```

**Output:**

![Screenshot (37)](https://github.com/user-attachments/assets/8fe1cbf8-23fc-4438-8583-95ba771ad074)


**Question 7**
---
![Screenshot (38)](https://github.com/user-attachments/assets/858b661f-73d2-4636-bf31-abf85f0a23d3)


```sql
DELETE FROM Doctors
WHERE doctor_id =1;
```

**Output:**
![Screenshot (39)](https://github.com/user-attachments/assets/01654bc7-86df-4147-b589-e80185563123)


**Question 8**
---
![Screenshot (40)](https://github.com/user-attachments/assets/18e57c61-6f11-439e-b34a-0cca16c4c3db)


```sql
DELETE FROM Customer
WHERE CUST_CITY <> 'New York' AND OUTSTANDING_AMT>5000;
```

**Output:**

![Screenshot (41)](https://github.com/user-attachments/assets/43ec576d-a2c4-442e-905a-cf1582a9e1a3)


**Question 9**
---
![Screenshot (42)](https://github.com/user-attachments/assets/0915b592-702a-4dd6-a072-31fba6a9c631)


```sql
SELECT EmpID, EmpFname,EmpLname,Department,Project,Address,DOB,Gender
FROM EmployeeInfo
WHERE EmpLname LIKE '____A'  ;
```

**Output:**

![Screenshot (43)](https://github.com/user-attachments/assets/ca4d6e76-d8fe-4287-b920-4d1a732dfcd4)


**Question 10**
---
![Screenshot (44)](https://github.com/user-attachments/assets/7343ab8e-3c37-4e87-84ae-0e81502c457d)

```sql
SELECT salesman_id,name,city,commission
FROM salesman
WHERE commission BETWEEN 0.12 AND 0.14;
```

**Output:**

![Screenshot (45)](https://github.com/user-attachments/assets/e835c194-1065-40b1-a065-3b24a1c6d552)

## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

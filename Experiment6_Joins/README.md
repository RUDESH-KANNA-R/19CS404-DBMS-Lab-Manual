# Experiment 6: Joins
## AIM
To study and implement different types of joins.

## THEORY

SQL Joins are used to combine records from two or more tables based on a related column.

### 1. INNER JOIN
Returns records with matching values in both tables.

**Syntax:**
```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### 2. LEFT JOIN
Returns all records from the left table, and matched records from the right.

**Syntax:**

```sql
SELECT columns
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```
### 3. RIGHT JOIN
Returns all records from the right table, and matched records from the left.

**Syntax:**

```sql
SELECT columns
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```
### 4. FULL OUTER JOIN
Returns all records when there is a match in either left or right table.

**Syntax:**

```sql
SELECT columns
FROM table1
FULL OUTER JOIN table2
ON table1.column = table2.column;
```

**Question 1**
--
![Screenshot (87)](https://github.com/user-attachments/assets/b1e0fd31-0362-4c95-8fcb-bf1c5db41a73)


```sql
SELECT t.*
FROM PATIENTS p
INNER JOIN test_results t ON p.patient_id=t.patient_id
WHERE p.first_name='Alice';
```

**Output:**

![Screenshot (88)](https://github.com/user-attachments/assets/56ddb082-c065-4628-b5d9-809c44d53c50)


**Question 2**
---
![Screenshot (89)](https://github.com/user-attachments/assets/cfa028ef-7e73-4eda-990e-3639192ee817)


```sql
SELECT s.name AS Salesman,c.cust_name,c.city
FROM salesman s
JOIN customer c on s.city=c.city;
```

**Output:**

![Screenshot (90)](https://github.com/user-attachments/assets/89a669e4-75a5-47b7-ba37-2271aaec6e14)


**Question 3**
---
![Screenshot (91)](https://github.com/user-attachments/assets/5be98ed7-95d1-4e9a-b465-d42d9ef623be)


```sql
SELECT c.cust_name AS "Customer Name",c.city,s.name AS "Salesman",s.commission
FROM customer c
JOIN salesman s ON c.salesman_id=s.salesman_id;
```

**Output:**

![Screenshot (92)](https://github.com/user-attachments/assets/c5fac354-dea9-44ca-b91e-c6a928358d12)


**Question 4**
---
![Screenshot (93)](https://github.com/user-attachments/assets/3e526a53-d6eb-4b0e-8e0e-73e93977ea3c)


```sql
SELECT c.cust_name,c.city,c.grade,s.name AS "Salesman",s.city
FROM customer c
JOIN salesman s ON c.salesman_id=s.salesman_id
ORDER BY c.customer_id ASC;
```

**Output:**

![Screenshot (94)](https://github.com/user-attachments/assets/cb335d4f-d838-47dc-823a-9ca901abd11f)

**Question 5**
---
![Screenshot (95)](https://github.com/user-attachments/assets/7a6baa88-e726-42cb-95ae-c49a860afd67)


```sql
SELECT o.ord_no,o.purch_amt,c.cust_name,c.city
FROM orders o
JOIN customer c ON o.customer_id=c.customer_id
WHERE o.purch_amt BETWEEN 500 and 2000;
```

**Output:**

![Screenshot (96)](https://github.com/user-attachments/assets/fefd25ae-ed20-471a-a13e-cc577b3c7df0)


**Question 6**
---
![Screenshot (97)](https://github.com/user-attachments/assets/f778fce1-5da5-479c-998a-302b0184a00f)


```sql
SELECT p.date_of_birth,a.appointment_id,p.patient_id,p.doctor_id,a.appointment_date
FROM patients p
INNER JOIN appointments a ON p.patient_id=a.patient_id
WHERE p.first_name='Alice';
```

**Output:**

![Screenshot (98)](https://github.com/user-attachments/assets/02576a26-1387-4030-bf44-9c6afff062b0)


**Question 7**
---
![Screenshot (99)](https://github.com/user-attachments/assets/188c6aeb-666d-4a4d-9c57-00135af9c4df)

```sql
SELECT p.first_name,s.surgery_id,p.patient_id,s.surgeon_id,s.surgery_date
FROM patients p
INNER JOIN surgeries s ON p.patient_id=s.patient_id
WHERE p.date_of_birth >'1990-01-01';
```

**Output:**

![Screenshot (100)](https://github.com/user-attachments/assets/b40f1f46-3f12-4094-8849-61ab44722eaa)

**Question 8**
---
![Screenshot (101)](https://github.com/user-attachments/assets/e019a19d-fcfd-419a-8d6c-5bd1edf946bd)


```sql
SELECT c.cust_name FROM customer c
LEFT JOIN orders o ON c.customer_id=o.customer_id;
```

**Output:**

![Screenshot (102)](https://github.com/user-attachments/assets/df4350b2-b8b0-411c-b5fd-00dd93b118a4)


**Question 9**
---
![Screenshot (103)](https://github.com/user-attachments/assets/af16e9c7-602b-4fc3-bed9-2d6d05882740)


```sql
SELECT c.* FROM customer c
LEFT JOIN orders o ON c.customer_id=o.customer_id
WHERE o.ord_date BETWEEN '2012-07-01' AND '2012-07-30';
```

**Output:**

![Screenshot (104)](https://github.com/user-attachments/assets/52fd6065-8d3a-42f0-a223-10d6a0df109a)

**Question 10**
---
![Screenshot (105)](https://github.com/user-attachments/assets/4fc010a7-9ce1-454b-a49f-44acf0795cda)

```sql
SELECT c.cust_name FROM customer c
LEFT JOIN orders o ON c.customer_id=o.customer_id
WHERE o.purch_amt<100;
```

**Output:**

![Screenshot (106)](https://github.com/user-attachments/assets/09afbbdd-4bbe-4306-98cc-aba32ca9e4d6)



## RESULT
Thus, the SQL queries to implement different types of joins have been executed successfully.

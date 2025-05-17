# Experiment 4: Aggregate Functions, Group By and Having Clause
## AIM
To study and implement aggregate functions, GROUP BY, and HAVING clause with suitable examples.

## THEORY

### Aggregate Functions
These perform calculations on a set of values and return a single value.

- **MIN()** – Smallest value  
- **MAX()** – Largest value  
- **COUNT()** – Number of rows  
- **SUM()** – Total of values  
- **AVG()** – Average of values

**Syntax:**
```sql
SELECT AGG_FUNC(column_name) FROM table_name WHERE condition;
```
### GROUP BY
Groups records with the same values in specified columns.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name;
```
### HAVING
Filters the grouped records based on aggregate conditions.
**Syntax:**
```sql
SELECT column_name, AGG_FUNC(column_name)
FROM table_name
GROUP BY column_name
HAVING condition;
```

**Question 1**
--
![Screenshot (46)](https://github.com/user-attachments/assets/01c30935-fe9b-49b0-8eac-cd8ee9072cb6)


```sql
SELECT Address,COUNT(PatientID) AS TotalPatients
FROM Patients
GROUP BY Address;
```

**Output:**

![Screenshot (47)](https://github.com/user-attachments/assets/7269be0d-2dbe-4d6e-a853-8cf3ad5653af)


**Question 2**
---
![Screenshot (48)](https://github.com/user-attachments/assets/b1cf8aa7-1d8e-4bdf-9949-8e228800ccc0)


```sql
SELECT Gender,COUNT(PatientID) AS TotalPatients
FROM Patients
GROUP BY Gender;
```

**Output:**

![Screenshot (49)](https://github.com/user-attachments/assets/0a403ee4-2202-4648-8522-5dc382bff204)


**Question 3**
---
![Screenshot (50)](https://github.com/user-attachments/assets/c6468357-4b34-4175-94d5-f22d13807cb9)


```sql
SELECT COUNT(city) AS COUNT
FROM customer
WHERE city='Noida';
```

**Output:**

![Screenshot (51)](https://github.com/user-attachments/assets/9df55630-b2a9-4310-89fa-07ecc545bcce)


**Question 4**
---
![Screenshot (52)](https://github.com/user-attachments/assets/edc0a16c-5ee1-45d4-bb7c-b51864bd3424)


```sql
SELECT COUNT( DISTINCT salesman_id) AS COUNT
FROM orders;
```

**Output:**

![Screenshot (53)](https://github.com/user-attachments/assets/a6c1dc53-00a3-4d47-9ae1-a82c0a507911)


**Question 5**
---
![Screenshot (54)](https://github.com/user-attachments/assets/008189a5-b89d-4d06-9123-b902eb05bd44)


```sql
SELECT name,LENGTH(name) AS length
FROM customer
GROUP BY  length 
ORDER BY length DESC 
LIMIT 1;
```

**Output:**

![Screenshot (55)](https://github.com/user-attachments/assets/dab05f60-027a-42db-b2a3-48f25331d599)


**Question 6**
---
![Screenshot (56)](https://github.com/user-attachments/assets/9bfeb4f1-4946-4a53-bbf3-042bde017770)


```sql
SELECT MAX(price)-MIN(price) AS price_diff
FROM fruits;
```

**Output:**

![Screenshot (57)](https://github.com/user-attachments/assets/97c38298-76db-4dd9-b21e-db723bd30a01)


**Question 7**
---
![Screenshot (58)](https://github.com/user-attachments/assets/8797ea2a-6542-4d7c-8b6d-4cedd589e7f5)


```sql
SELECT jdate,MIN(workhour) AS 'MIN(workhour)'
FROM employee1
GROUP BY jdate
HAVING MIN(workhour)<10;
```

**Output:**

![Screenshot (59)](https://github.com/user-attachments/assets/948c8c23-9e3b-4565-8fce-f82051804114)

**Question 8**
---
![Screenshot (60)](https://github.com/user-attachments/assets/0f9b2174-93e7-4e09-a87e-75a73a4061d5)

```sql
SELECT jdate,MAX(workhour) AS 'MAX(workhour)'
FROM employee1
GROUP BY jdate
HAVING MAX(workhour)>12;
```

**Output:**

![Screenshot (61)](https://github.com/user-attachments/assets/83da169b-4537-407e-a260-f61118b54efe)


**Question 9**
---
![Screenshot (62)](https://github.com/user-attachments/assets/ecb73d45-a405-41e0-8ed2-6ca4531cdb2a)

```sql
SELECT age ,AVG(income) AS 'AVG(income)'
FROM employee
GROUP BY age
HAVING income BETWEEN 300000 AND 500000;
```

**Output:**

![Screenshot (63)](https://github.com/user-attachments/assets/df2cd98a-6d81-4c76-869f-608483c9c061)


**Question 10**
---
![Screenshot (64)](https://github.com/user-attachments/assets/9ba17f7b-b092-4132-8551-c76eaf755aec)


```sql
SELECT PatientID ,COUNT(*) AS TotalRecords
FROM MedicalRecords
GROUP BY PatientID
HAVING TotalRecords>3;
```

**Output:**

![Screenshot (65)](https://github.com/user-attachments/assets/e11877ed-7446-4d2b-977f-c3c2759b481a)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.

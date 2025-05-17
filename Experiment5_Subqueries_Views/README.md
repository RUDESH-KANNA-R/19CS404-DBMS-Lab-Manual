# Experiment 5: Subqueries and Views
## AIM
To study and implement subqueries and views.

## THEORY

### Subqueries
A subquery is a query inside another SQL query and is embedded in:
- WHERE clause
- HAVING clause
- FROM clause

**Types:**
- **Single-row subquery**:
  Sub queries can also return more than one value. Such results should be made use along with the operators in and any.
- **Multiple-row subquery**:
  Here more than one subquery is used. These multiple sub queries are combined by means of ‘and’ & ‘or’ keywords.
- **Correlated subquery**:
  A subquery is evaluated once for the entire parent statement whereas a correlated Sub query is evaluated once per row processed by the parent statement.

**Example:**
```sql
SELECT * FROM employees
WHERE salary > (SELECT AVG(salary) FROM employees);
```
### Views
A view is a virtual table based on the result of an SQL SELECT query.
**Create View:**
```sql
CREATE VIEW view_name AS
SELECT column1, column2 FROM table_name WHERE condition;
```
**Drop View:**
```sql
DROP VIEW view_name;
```

**Question 1**
--
![Screenshot (66)](https://github.com/user-attachments/assets/29fa55aa-d1c8-49a5-959e-80c0342caf45)

```sql
SELECT grade ,COUNT(*) 
FROM customer
GROUP BY grade
HAVING grade >(SELECT AVG(grade)
FROM customer
WHERE city = 'New York');

```

**Output:**

![Screenshot (67)](https://github.com/user-attachments/assets/5813663f-fa3a-4fc5-9039-700301eeaaf1)


**Question 2**
---
![Screenshot (69)](https://github.com/user-attachments/assets/9eb539a2-aebc-4c44-a14f-5dfdb6a14b59)


```sql
SELECT department_id as depar, department_name
FROM departments
WHERE LENGTH(department_name) > (
    SELECT AVG(LENGTH(department_name)) FROM departments
);

```

**Output:**

![Screenshot (70)](https://github.com/user-attachments/assets/bfe5d175-f2fc-4fdf-bb87-30848d366258)


**Question 3**
---
![Screenshot (71)](https://github.com/user-attachments/assets/b2bf6054-a136-45f8-a3c1-7252a309fb09)


```sql
SELECT * FROM GRADES g
WHERE g.grade=(SELECT MAX(grade)
               FROM GRADES
              WHERE subject=g.subject);
```

**Output:**

![Screenshot (72)](https://github.com/user-attachments/assets/dfaec538-4a07-4a49-b8e7-82894ded4dba)


**Question 4**
---
![Screenshot (73)](https://github.com/user-attachments/assets/965b7936-2f4a-4676-aa32-64147ea25336)

```sql
SELECT * FROM Employee
WHERE age <(
SELECT AVG(age)
FROM Employee
WHERE income>1000000);
```

**Output:**

![Screenshot (74)](https://github.com/user-attachments/assets/fe483b8b-888a-43c5-9cb2-93aab75848ec)


**Question 5**
---
![Screenshot (75)](https://github.com/user-attachments/assets/048069fb-110e-46f1-8283-a95492d3c87a)


```sql
SELECT * FROM CUSTOMERS
WHERE ADDRESS ='Delhi';
```

**Output:**

![Screenshot (76)](https://github.com/user-attachments/assets/82e46355-f537-4eae-9b31-6253c511eb0c)

**Question 6**
---
![Screenshot (77)](https://github.com/user-attachments/assets/a400ad7a-ec1d-438d-a770-b6698ebe610d)


```sql
SELECT o.ord_no,o.purch_amt,o.ord_date,o.customer_id,o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id=s.salesman_id
WHERE s.city = 'London';
```

**Output:**

![Screenshot (78)](https://github.com/user-attachments/assets/7878da96-c5e9-46f9-9a08-1fc660c4db26)


**Question 7**
---
![Screenshot (79)](https://github.com/user-attachments/assets/45f82d16-0d4a-4674-b511-560970075a23)


```sql
SELECT s.salesman_id,s.name
FROM salesman s
JOIN customer c ON s.salesman_id=c.salesman_id
GROUP BY s.salesman_id,s.name
HAVING COUNT(c.customer_id)>1;
```

**Output:**

![Screenshot (80)](https://github.com/user-attachments/assets/c5930c8d-f1e6-4e0c-8907-83cdc1723ceb)


**Question 8**
---
![Screenshot (81)](https://github.com/user-attachments/assets/6ef1964b-14c5-4bfd-9233-faa4a7069c72)

```sql
SELECT 
    o.ord_no,
    o.purch_amt,
    o.ord_date,
    o.salesman_id
FROM orders o
JOIN salesman s ON o.salesman_id = s.salesman_id
WHERE s.commission = (
    SELECT MAX(commission) FROM salesman
);

```

**Output:**

![Screenshot (82)](https://github.com/user-attachments/assets/fc5fa268-39f8-4b6c-a2eb-9aa744b70ca9)


**Question 9**
---
![Screenshot (83)](https://github.com/user-attachments/assets/9283812d-c83e-419e-9ee4-1906e56a065c)

```sql
SELECT * FROM CUSTOMERS
WHERE AGE < 30;
```

**Output:**

![Screenshot (84)](https://github.com/user-attachments/assets/dbadad47-ee94-44c3-8b1e-e73b876c3ae9)


**Question 10**
---
![Screenshot (85)](https://github.com/user-attachments/assets/1b2f0484-4ba1-4bb4-8024-41cdc09c189a)


```sql
SELECT customer_id,cust_name,city,grade,salesman_id
FROM customer
WHERE customer_id = (SELECT salesman_id -2001
FROM salesman
WHERE name = 'Mc Lyon')
```

**Output:**

![Screenshot (86)](https://github.com/user-attachments/assets/df2e634f-8e73-49f5-bb19-75ac57790474)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.

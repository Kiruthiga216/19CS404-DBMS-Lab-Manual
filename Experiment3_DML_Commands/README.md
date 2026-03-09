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

Write a SQL query to find all employees who were hired in the year 2022 from emp table

```
SELECT *
FROM emp
WHERE strftime('%Y',hiredate)='2022';
```

**Output:**

<img width="788" height="351" alt="image" src="https://github.com/user-attachments/assets/ea12cb23-800e-4d5b-82d5-7db0a10e9f0c" />


**Question 2**

Write a SQL query to label rows in the Calculations table as 'Even' if value1 is even, otherwise 'Odd'

```
SELECT id,
       value1,
       CASE
           WHEN value1%2==0 THEN 'Even'
           ELSE 'Odd'
       END AS parity
FROM Calculations;
```

**Output:**

<img width="540" height="168" alt="image" src="https://github.com/user-attachments/assets/3a1aa750-dd5d-4040-a733-9857cd7a5278" />

**Question 3**

Write a SQL query to Select all patients whose name starts with A

```
SELECT *
FROM Patients
WHERE first_name LIKE 'A%';
```

**Output:**

<img width="783" height="182" alt="image" src="https://github.com/user-attachments/assets/4a8412c0-0dd0-4392-b2fc-c8a9d61df7e6" />


**Question 4**

Write a SQL query to calculate the number of days between the hiredate and a specified date ('2024-12-31') for each employee using
the JULIANDAY function from the emp table

```
SELECT ename,
       hiredate,
       JULIANDAY('2024-12-31')-JULIANDAY(hiredate) AS days_worked
FROM emp;
```

**Output:**

<img width="565" height="162" alt="image" src="https://github.com/user-attachments/assets/216e30a8-fcd1-4c1d-a317-d3f5fcc22d1b" />

**Question 5**

Write a SQL statement to Display the order number, orderdate and the purchase amount of
orders table which will be delivered by the salesman with ID 5001

```
SELECT order_no,
order_date,
purch_amt
FROM orders
WHERE salesman_id =5001;
```

**Output:**

<img width="532" height="202" alt="image" src="https://github.com/user-attachments/assets/96bb814a-a1fa-4232-911c-374c5628ae95" />

**Question 6**

Write a SQL query to Delete customers from 'customer' table where 'OPENING_AMT' is between 4000 and 6000.

```
DELETE FROM Customer
WHERE OPENING_AMT BETWEEN 4000 AND 6000;
```

**Output:**

<img width="777" height="864" alt="image" src="https://github.com/user-attachments/assets/6e7281a4-178c-4e60-b8c1-488c786110a5" />


**Question 7**

Write a SQL query to Delete customers from 'customer' table where 'GRADE' is greater than or equal to 2

```
DELETE FROM Customer
WHERE GRADE>=2;
```

**Output:**

<img width="466" height="364" alt="image" src="https://github.com/user-attachments/assets/c629ff9b-bb2d-40f8-8c49-0d20062f7b82" />


**Question 8**

Write a SQL statement to Double the salary for employees in department 20 who have a job_id ending with 'MAN'

```
UPDATE Employees
SET salary=salary*2
WHERE department_id=20
      AND job_id LIKE '%MAN';
```

**Output:**

<img width="784" height="329" alt="image" src="https://github.com/user-attachments/assets/78f3197e-c4c7-4e00-8f73-a2b9776d4395" />


**Question 9**

Write a SQL statement to change the email column of employees table with 'Unavailable' for all employees in employees table.

```
UPDATE Employees
SET email='Unavailable';
```
**Output:**

<img width="790" height="462" alt="image" src="https://github.com/user-attachments/assets/6a780995-9a5c-4e78-b4e2-91893eb122ec" />


**Question 10**

Write a SQL statement to change salary of employee to 8000 whose Employee ID is 105, if the existing salary is less than 5000

```
UPDATE Employees
SET salary=8000
WHERE employee_id=105
      AND salary<5000;
```
**Output:**

<img width="786" height="183" alt="image" src="https://github.com/user-attachments/assets/fe74ff3f-dbf4-425a-9f23-e7cd8c0a4817" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

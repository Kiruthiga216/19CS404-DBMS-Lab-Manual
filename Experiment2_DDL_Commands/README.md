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

Create a new table named item with the following specifications and constraints:
1. item_id as TEXT and as primary key.
2. item_desc as TEXT.
3. rate as INTEGER.
4. icom_id as TEXT with a length of 4.
5. icom_id is a foreign key referencing com_id in the company table.
6. The foreign key should cascade updates and deletes.
7. item_desc and rate should not accept NULL

```
CREATE TABLE item(
item_id  TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT(4),
FOREIGN KEY(icom_id) REFERENCES company(com_id)
ON UPDATE CASCADE
ON DELETE CASCADE
);
```

**Output:**

![Output1](output.png)

**Question 2**

Write a SQL Query  to add attribute ISBN as varchar(30) and domain_dept as varchar(30) in the table 'books'

```
ALTER TABLE books ADD COLUMN ISBN varchar(30);
ALTER TABLE books ADD COLUMN domain_dep varchar(30);
```

**Output:**

![Output2](output.png)

**Question 3**

Insert the below data into the Student_details table, allowing the Subject and MARKS columns to take their default values.

```
INSERT INTO Student_details(RollNo, Name,Gender)
VALUES(204,'Samuel Black','M');
```


**Output:**

![Output3](output.png)

**Question 4**

Insert all customers from Old_customers into Customers
Table attributes are CustomerID, Name, Address, Email

```
INSERT INTO Customers(CustomerID,Name,Address,Email)
SELECT CustomerID,Name,Address,Email
FROM Old_customers;
```

**Output:**

![Output4](output.png)

**Question 5**

Create a table named Orders with the following columns:

OrderID as INTEGER

OrderDate as TEXT

CustomerID as INTEGER

```
CREATE TABLE Orders(
OrderID  INTEGER,
OrderDate  TEXT,
CustomerID  INTEGER
);
```

**Output:**

![Output5](output.png)

**Question 6**

Create a table named Shipments with the following constraints:

ShipmentID as INTEGER should be the primary key.

ShipmentDate as DATE.

SupplierID as INTEGER should be a foreign key referencing Suppliers(SupplierID).

OrderID as INTEGER should be a foreign key referencing Orders(OrderID)

```
CREATE TABLE Shipments(
ShipmentID  INTEGER PRIMARY KEY,
ShipmentDate DATE,
SupplierID INTEGER, 
OrderID INTEGER,
FOREIGN KEY(SupplierID) REFERENCES Suppliers(SupplierID),
FOREIGN KEY(OrderID) REFERENCES Orders(OrderID)
);
```

**Output:**

![Output6](output.png)

**Question 7**

In the Books table, insert a record where some fields are NULL, another record where all fields are filled without any NULL values, and a
third record where some fields are filled, and others are left as NULL.

```
INSERT INTO Books(ISBN ,Title,Author,Publisher,Year)
VALUES
('978-1234567890' , 'Introduction to AI', 'John Doe', NULL,NULL),
('978-9876543210' ,  'Deep Learning','Jane Doe', 'TechPress', 2022),
('978-1122334455', 'Cybersecurity Essentials' ,  'Alice Smith', NULL,2021);
```

**Output:**

![Output7](output.png)

**Question 8**

Create a table named Products with the following constraints:

ProductID as INTEGER should be the primary key.

ProductName as TEXT should be unique and not NULL.

Price as REAL should be greater than 0.

StockQuantity as INTEGER should be non-negative.

```
CREATE TABLE Products(
ProductID  INTEGER PRIMARY KEY,
ProductName TEXT UNIQUE NOT NULL,
Price REAL CHECK (Price>0),
StockQuantity INTEGER CHECK (StockQuantity >=0)
);
```
**Output:**

![Output8](output.png)

**Question 9**

Write a SQL query to add birth_date attribute as timestamp (datatype) in the table customer

```
ALTER TABLE customer ADD COLUMN  birth_date   timestamp ;
```

**Output:**

![Output9](output.png)

**Question 10**

Create a new table named products with the following specifications:

product_id as INTEGER and primary key.

product_name as TEXT and not NULL.

list_price as DECIMAL (10, 2) and not NULL.

discount as DECIMAL (10, 2) with a default value of 0 and not NULL.

A CHECK constraint at the table level to ensure:

list_price is greater than or equal to discount

discount is greater than or equal to 0

list_price is greater than or equal to 0

```
CREATE TABLE products(
product_id INTEGER  PRIMARY KEY,
product_name TEXT NOT NULL,
list_price DECIMAL (10, 2) NOT NULL,
discount DECIMAL (10, 2)
DEFAULT 0,
CHECK(list_price >= discount),
CHECK(discount >= 0),
CHECK(list_price >= 0)
);
```

**Output:**

![Output10](output.png)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

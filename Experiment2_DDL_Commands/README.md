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
-- Create a table named Orders with the following constraints:
OrderID as INTEGER should be the primary key.
OrderDate as DATE should be not NULL.
CustomerID as INTEGER should be a foreign key referencing Customers(CustomerID).


```sql
-- create table Orders(
OrderID integer PRIMARY KEY,
OrderDate date NOT NULL,
CustomerID integer,
FOREIGN KEY(CustomerID) REFERENCES Customers(CustomerID));
```

**Output:**
![image](https://github.com/user-attachments/assets/6a1932eb-47fd-42c1-b2a4-a912e8014ae8)



**Question 2**
---
-- Write a SQL query to Add a new column mobilenumber as number in the Student_details table.

Sample table: Student_details

 cid              name             type   notnull     dflt_value  pk
---------------  ---------------  -----  ----------  ----------  ----------
0                RollNo           int    0                       1
1                Name             VARCH  1                       0
2                Gender           TEXT   1                       0
3                Subject          VARCH  0                       0
4                MARKS            INT (  0                       0

```sql
--alter table Student_details
add column mobilenumber number;
```

**Output:**
![image](https://github.com/user-attachments/assets/da895e0d-d40f-4d7b-80fc-ac0a436ad2a6)


**Question 3**
---
-- Create a table named Shipments with the following constraints: ShipmentID as
INTEGER should be the primary key. ShipmentDate as DATE. SupplierID as INTEGER
should be a foreign key referencing Suppliers(SupplierID). OrderID as INTEGER should
be a foreign key referencing Orders(OrderID).


```sql
-- CREATE TABLE Shipments (
ShipmentID INTEGER PRIMARY KEY,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
FOREIGN KEY (SupplierID) REFERENCES Suppliers(SupplierID),
FOREIGN KEY (OrderID) REFERENCES Orders(OrderID)
);
```

**Output:**
![image](https://github.com/user-attachments/assets/6134088d-a337-4b1b-8a2d-3720d2a2275c)


**Question 4**
---
-- Create a table named ProjectAssignments with the following constraints:
AssignmentID as INTEGER should be the primary key. EmployeeID as INTEGER should
be a foreign key referencing Employees(EmployeeID). ProjectID as INTEGER should be a
foreign key referencing Projects(ProjectID). AssignmentDate as DATE should be NOT
NULL.


```sql
-- CREATE TABLE ProjectAssignments (
AssignmentID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
ProjectID INTEGER,
AssignmentDate DATE NOT NULL,
FOREIGN KEY (EmployeeID) REFERENCES Employees(EmployeeID),
FOREIGN KEY (ProjectID) REFERENCES Projects(ProjectID)
);
```

**Output:**
![image](https://github.com/user-attachments/assets/26f25ad6-ad77-481d-9619-c88a2b95b105)


**Question 5**
---
-- Create a table named Department with the following constraints: DepartmentID as
INTEGER should be the primary key. DepartmentName as TEXT should be unique and
not NULL. Location as TEXT.


```sql
-- CREATE TABLE Department(
DepartmentID INTEGER PRIMARY KEY,
DepartmentName TEXT UNIQUE NOT NULL,
Location TEXT
);
```

**Output:**
![image](https://github.com/user-attachments/assets/04606c25-b8d5-41b2-bdf8-c71167fb5327)



**Question 6**
---
-- Create a table named Department with the following constraints:
DepartmentID as INTEGER should be the primary key.
DepartmentName as TEXT should be unique and not NULL.
Location as TEXT.

```sql
-- create table Department(
DepartmentID INTEGER PRIMARY KEY,
DepartmentName TEXT UNIQUE NOT NULL,
Location TEXT);
```

**Output:**
![image](https://github.com/user-attachments/assets/4736357e-261b-4257-9ea2-7c32fc0bfe2e)


**Question 7**
---
-- - Insert all employees from Former_employees into Employee
Table attributes are EmployeeID, Name, Department, Salary

```sql
--  Insert into Employee (EmployeeID,Name,Department,Salary)
Select EmployeeID,Name,Department,Salary from Former_employees;
```

**Output:**
![image](https://github.com/user-attachments/assets/bb725b00-23f8-4010-86b2-f2d567d6961b)


![Output7](output.png)

**Question 8**
---
-- Create a table named ProjectAssignments with the following constraints:
AssignmentID as INTEGER should be the primary key.
EmployeeID as INTEGER should be a foreign key referencing Employees(EmployeeID).
ProjectID as INTEGER should be a foreign key referencing Projects(ProjectID).
AssignmentDate as DATE should be NOT NULL.

```sql
-- create table ProjectAssignments(
AssignmentID INTEGER PRIMARY KEY,
EmployeeID INTEGER,
ProjectID INTEGER,
AssignmentDate DATE NOT NULL,
FOREIGN KEY(EmployeeID) REFERENCES Employees(EmployeeID),
FOREIGN KEY(ProjectID) REFERENCES Projects(ProjectID));
```

**Output:**
![image](https://github.com/user-attachments/assets/38043a80-da61-412e-b36e-fb81c5e5ec04)



**Question 9**
---
-- Create a new table named item with the following specifications and constraints:
item_id as TEXT and as primary key.
item_desc as TEXT.
rate as INTEGER.
icom_id as TEXT with a length of 4.
icom_id is a foreign key referencing com_id in the company table.
The foreign key should set NULL on updates and deletes.
item_desc and rate should not accept NULL.

```sql
-- create table item(
item_id TEXT PRIMARY KEY,
item_desc TEXT NOT NULL,
rate INTEGER NOT NULL,
icom_id TEXT(4),
FOREIGN KEY(icom_id) REFERENCES company(com_id) 
ON UPDATE SET NULL 
ON DELETE SET NULL);
```

**Output:**
![image](https://github.com/user-attachments/assets/f9584bb3-f5a3-4a80-84c4-adce2fa8cf1b)


**Question 10**
---
-- Write a SQL query for adding a new column named "email" with the datatype
VARCHAR(100) to the table "customer"


```sql
--ALTER TABLE Customer
ADD COLUMN email VARCHAR(100);
```

**Output:**

![image](https://github.com/user-attachments/assets/fdeab58d-cf88-4b42-9edc-21d1ae544d15)




## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

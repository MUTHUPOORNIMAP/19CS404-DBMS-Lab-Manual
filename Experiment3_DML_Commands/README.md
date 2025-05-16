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
-- - Write a SQL statement to Update the reorder level to 20 where the quantity in stock
is less than 10 and product category is 'Snacks' in the products table

```sql
update Products
set reorder_lvl=20
where quantity<10 and category ='Snacks';
```

**Output:**
![image](https://github.com/user-attachments/assets/27d60413-9423-47dc-a30a-8ea4a75eada4)


**Question 2**
---
-- Write a SQL statement to Increase the selling price by 15% in the products table
where quantity in stock is less than 50 and supplier ID is 10.

```sql
update Products
set sell_price=sell_price*1.15
where quantity <50 and supplier_id =10;
```

**Output:**
![image](https://github.com/user-attachments/assets/bbebf03c-89bb-41b9-97c9-8e74c65a4a87)


**Question 3**
---
-- - Write a SQL statement to change the EMAIL and COMMISSION_PCT column of the
following EMPLOYEES table with 'not available' and 0.55 for those employees whose
DEPARTMENT_ID is 110.


```sql
UPDATE Employees
set EMAIL='not available',commission_pct=0.55
where DEPARTMENT_ID =110;
```

**Output:**
![image](https://github.com/user-attachments/assets/eaa89fe3-3520-4ecc-bfdf-49fe292ed8e3)


**Question 4**
---
Write a SQL statement to Update the hire_date of employees in department 50 to
2024-01-24.


```sql
update Employees
set hire_date='2024-01-24';
```

**Output:**
![image](https://github.com/user-attachments/assets/1e41c76a-73e5-4753-92b4-b943dd2f584f)


**Question 5**
---
-- Write a SQL statement to Update the address to '58 Lakeview, Magnolia' where supplier ID is 5 in the suppliers table.

```sql
UPDATE suppliers
SET address='58 Lakeview, Magnolia'
WHERE supplier_id=5;
```

**Output:**
![image](https://github.com/user-attachments/assets/e624a857-f035-4631-9257-38f091352113)


**Question 6**
---
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is
exactly 2.

```sql
delete from customer
where grade =2;
```

**Output:**

![image](https://github.com/user-attachments/assets/5acf9855-cb55-433d-b3e5-a8246e3df668)


**Question 7**
---
Write a SQL query to Delete customers with 'GRADE' 3 and whose 'CUST_NAME'
contains the substring 'BBB', and 'PAYMENT_AMT' is greater than 2000

```sql
delete from customer
where grade= 3
and cust_name like '%BBB%'
and payment_amt>2000;
```

**Output:**
![image](https://github.com/user-attachments/assets/2fe274d3-b76b-431b-a260-82ade2877cbd)


**Question 8**
---
Write a SQL query to Delete customers from 'customer' table where 'CUST_CITY' is not 'New York' and 'OUTSTANDING_AMT' is greater than 5000.

```sql
DELETE from customer where CUST_CITY<>'New York' AND OUTSTANDING_AMT>5000;
```

**Output:**
![image](https://github.com/user-attachments/assets/7b999482-87bf-4352-99e9-93f72031e128)



**Question 9**
---
Write a SQL query to Delete customers from 'customer' table where 'GRADE' is greater than or equal to 2.

```sql
DELETE FROM customer WHERE GRADE>=2;
```

**Output:**
![image](https://github.com/user-attachments/assets/406a40de-9837-469b-a613-f7187887f2ef)


**Question 10**
---
Write a SQL statement to Find those salesmen with all information whose name containing the 1st character is 'N' and the 4th character is 'l' and rests may be any character.

```sql
SELECT * FROM salesman WHERE name like 'N_I%';
```

**Output:**
![image](https://github.com/user-attachments/assets/43b6d085-1d46-414e-b16a-a96e6a892613)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

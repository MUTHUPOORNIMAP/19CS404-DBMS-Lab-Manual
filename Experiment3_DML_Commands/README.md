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

### Question 1
Decrease the reorder level by 30 percent where the product name contains 'cream' and quantity in stock is higher than reorder level in the products table.
```sql
UPDATE products SET reorder_lvl = reorder_lvl * 0.7 
WHERE LOWER(product_name) LIKE "%cream%" AND quantity > reorder_lvl;
```
OUTPUT
![image](https://github.com/user-attachments/assets/0656d6d7-2083-4513-b0d5-44c848a233eb)
![image](https://github.com/user-attachments/assets/04efbe8b-7c37-4bac-b982-cc0c24c06fb9)


### Question 2
Write a SQL statement to Update the product_name to 'Premium Bread' whose product ID is 5 in the products table.

Products table

product_id product_name category cost_price sell_price reorder_lvl quantity supplier_id
```sql
UPDATE Products SET product_name = 'Premium Bread' WHERE product_id = 5;
```
OUTPUT
![image](https://github.com/user-attachments/assets/6eacd601-b356-4808-b726-4c7df4046d58)
![image](https://github.com/user-attachments/assets/bf9405ef-8b88-48ad-b79a-e9012e4a7bdb)

### Question 3
Write a SQL statement to Update the reorder level to 20 where the quantity in stock is less than 10 and product category is 'Snacks' in the products table.

Products table

product_id product_name category cost_price sell_price reorder_lvl quantity supplier_id
```sql
UPDATE Products SET reorder_lvl = 20 WHERE quantity < 10 AND category = 'Snacks';
```
OUTPUT
![image](https://github.com/user-attachments/assets/f0127cdb-f33e-4033-a15e-927762adb972)
![image](https://github.com/user-attachments/assets/f5396e36-8f13-42cc-a800-ac6e0aa647a9)

### Question 4
Write a SQL statement to Update the address to '58 Lakeview, Magnolia' where supplier ID is 5 in the suppliers table.

Suppliers Table

name type

supplier_id INT supplier_name VARCHAR(100) contact_person VARCHAR(100) phone_number VARCHAR(20) email VARCHAR(100) address VARCHAR(250)
```sql
UPDATE Suppliers SET address = '58 Lakeview, Magnolia' WHERE supplier_id = 5;
```
OUTPUT
![image](https://github.com/user-attachments/assets/9d5df2d2-925e-447d-b5ff-e444c023fc2f)
![image](https://github.com/user-attachments/assets/0fb78d67-3f13-4072-9e8a-1131222a0fdd)


### Question 5
Write a SQL statement to Update the hire_date of employees in department 50 to 2024-01-24.

Employees table

employee_id first_name last_name email phone_number hire_date job_id salary commission_pct manager_id department_id
```sql
UPDATE Employees SET hire_date = '2024-01-24' WHERE department_id = 50;
```
OUTPUT
![image](https://github.com/user-attachments/assets/41dc4270-7949-4167-bb01-8690ef4f17ab)

### Question 6
Write a SQL query to Delete a Specific Surgery which was made on 28th Feb 2024.

Sample table: Surgeries

attributes: surgery_id, patient_id, surgeon_id, surgery_date
```sql
DELETE FROM Surgeries WHERE surgery_date = '2024-02-28';
```

OUTPUT
![image](https://github.com/user-attachments/assets/a1eb34df-7415-408c-a2ba-9fb9bdf68116)

### Question 7
Write a SQL query to remove rows from the table 'customer' with the following condition -

'cust_city' should begin with the letter 'L',
```sql
DELETE FROM Customer WHERE CUST_CITY LIKE 'L%';
```
OUTPUT
![image](https://github.com/user-attachments/assets/94c99bd4-f979-4aa6-9c02-4afa5a723c07)

### Question 8
Write a SQL query to Delete all Doctors whose Specialization is either 'Pediatrics' or 'Cardiology' and Last Name is Brown.

Sample table: Doctors

attributes : doctor_id, first_name, last_name, specialization
```sql
DELETE FROM Doctors WHERE (specialization = 'Pediatrics' OR specialization = 'Cardiology') AND (last_name LIKE '%Brown');
```
OUTPUT
![image](https://github.com/user-attachments/assets/9598cbe9-1646-4f65-ac42-a6094f811a8b)

### Question 9
Write a SQL query to Delete customers from 'customer' table where 'CUST_NAME' contains the substring 'Holmes'.

Sample table: Customer
```sql
DELETE FROM Customer WHERE CUST_NAME LIKE '%Holmes%';
```
OUTPUT
![image](https://github.com/user-attachments/assets/678e4295-90ff-4ba7-807d-9de58dd7051d)
![image](https://github.com/user-attachments/assets/77778b2c-1e47-4ef2-a0eb-3ad417785595)

### Question 10
Write a SQL query to Delete customers with 'CUST_COUNTRY' 'UK' and 'WORKING_AREA' 'London' whose 'GRADE' is less than 3

Sample table: Customer
```sql
DELETE FROM Customer WHERE CUST_COUNTRY = 'UK' AND WORKING_AREA = 'London' AND GRADE < 3;
```
OUTPUT
![image](https://github.com/user-attachments/assets/05329a18-1f30-4730-bc57-6b9c0920612a)
![image](https://github.com/user-attachments/assets/a6cd8c94-46d0-41d2-8c3d-12a08fb4458c)














## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

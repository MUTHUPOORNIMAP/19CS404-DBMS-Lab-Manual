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
### Question 1
Write the SQL query that achieves the selection of the "cust_name" column from the "customer" table (aliased as "c"), and the "ord_no," "ord_date," and "purch_amt" columns from the "orders" table (aliased as "o"), with a left join on the "customer_id" column and a condition filtering for orders with a purchase amount greater than 1000.
```sql
select c.cust_name,o.ord_no,o.ord_date,o.purch_amt
from customer c
LEFT JOIN orders o on c.customer_id=o.customer_id
WHERE o.purch_amt>1000;
```

OUTPUT

![image](https://github.com/user-attachments/assets/c15e9c19-fcfa-409e-a167-5a8c35d188b9)

### Question 2
From the following tables write a SQL query to find the details of an order. Return ord_no, ord_date, purch_amt, Customer Name, grade, Salesman, commission. 

Sample table: orders,customer,salesman
```sql
select o.ord_no,o.ord_date,o.purch_Amt,c.cust_name as "Customer Name",c.grade,s.name as "Salesman",s.commission
from orders o
LEFT JOIN customer c ON o.customer_id=c.customer_id
LEFT JOIN salesman s ON o.salesman_id=s.salesman_id;
```

OUTPUT

![image](https://github.com/user-attachments/assets/fa2c2651-6272-43d5-a942-29060e540fb7)
![image](https://github.com/user-attachments/assets/7aa1cb42-afc4-4d78-bac1-5b4b5554423c)

### Question 3
write a SQL query to find the salesperson and customer who reside in the same city. Return Salesman, cust_name and city.
```sql
select s.name as Salesman,c.cust_name,c.city
from salesman as s,customer as c
WHERE s.city=c.city;
```
OUTPUT

![image](https://github.com/user-attachments/assets/422c0ad2-8952-40f0-a174-5663bc0d8f44)

### Question 4
Write the SQL query that achieves the selection of the "cust_name" column from the "customer" table (aliased as "c") and the "commission" column from the "salesman" table (aliased as "s"), with a left join on the "salesman_id" column.
```sql
select c.cust_name,s.commission
from customer c
LEFT JOIN salesman s ON c.salesman_id=s.salesman_id;
```

OUTPUT

![image](https://github.com/user-attachments/assets/af880c93-6fd4-4f2c-aa52-2c86b00716da)

### Question 5
Write the SQL query that achieves the selection of the first name from the "patients" table (aliased as "patient_name"), with an inner join on the "doctor_id" column and conditions filtering for patients whose doctor has the first name 'Emily', last name 'Johnson', and a non-null discharge date.
```sql
select p.first_name as patient_name 
from patients p
INNER JOIN doctors d ON p.doctor_id=d.doctor_id
WHERE d.first_name='Emily' AND d.last_name='Johnson' AND p.discharge_date IS NOT NULL;
```
OUTPUT

![image](https://github.com/user-attachments/assets/1613828c-f4f3-43e9-869c-dbe234da73bd)

### Question 6
From the following tables write a SQL query to find the salesperson(s) and the customer(s) he represents. Return Customer Name, city, Salesman, commission.
```sql
select c.cust_name as "Customer Name",c.city,s.name as Salesman,s.commission
from customer c
JOIN salesman s ON c.salesman_id=s.salesman_id;
```

OUTPUT

![image](https://github.com/user-attachments/assets/d8e50967-cfb0-4273-b516-cd4aec8582e7)

### Question 7
From the following tables write a SQL query to display the customer name, customer city, grade, salesman, salesman city. The results should be sorted by ascending customer_id.  
```sql
select c.cust_name,c.city,c.grade,s.name as Salesman,s.city
from customer c
JOIN salesman s
ON c.salesman_id=s.salesman_id
ORDER BY c.customer_id ASC;
```

OUTPUT

![image](https://github.com/user-attachments/assets/f53d5b73-dd91-47ab-92e8-8c4d3617adc4)

### Question 8
Write the SQL query that achieves the selection of all columns from the "patients" table (aliased as "p"), with an inner join on the "patient_id" column and a condition filtering for test results with a test date between '2024-03-01' and '2024-03-31'.
```sql
select p.*
from patients p
INNER JOIN test_results t ON p.patient_id=t.patient_id
WHERE t.test_date BETWEEN '2024-03-01' AND '2024-03-31'
```
OUTPUT

![image](https://github.com/user-attachments/assets/ab32807f-3638-46ad-b836-6d4cb1903892)

### Question 9
 From the following tables write a SQL query to find salespeople who received commissions of more than 12 percent from the company. Return Customer Name, customer city, Salesman, commission.  
 ```sql
select c.cust_name as "Customer Name",c.city,s.name as Salesman,s.commission
from customer c
JOIN salesman s ON c.salesman_id=s.salesman_id
WHERE s.commission>0.12;
```
OUTPUT

![image](https://github.com/user-attachments/assets/90ed564c-9ab3-48ca-a94d-229cb3eee920)


### Question 10
Write the SQL query that accomplishes the selection of the first name and last name from the "patients" table, with an inner join on the "patient_id" column and a condition filtering for surgeries with a surgery date between '2024-01-01' and '2024-01-31'.
```sql
select p.first_name,p.last_name
from patients p
INNER JOIN surgeries s
ON p.patient_id=s.patient_id
WHERE s.surgery_date BETWEEN '2024-01-01' AND '2024-01-31'
```

OUTPUT

![image](https://github.com/user-attachments/assets/2bbd17c6-bf7c-4821-ba43-76511922e848)

## RESULT
![image](https://github.com/user-attachments/assets/10827580-fddd-4cae-9de2-2db3f31bba65)

Thus, the SQL queries to implement different types of joins have been executed successfully.

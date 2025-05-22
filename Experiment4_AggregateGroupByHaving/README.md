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

### Question 1
How many appointments are scheduled for each patient?

Sample table: Appointments Table
```sql
select PatientID,count(*) as TotalAppointments from
Appointments
GROUP BY PatientID;
```
OUTPUT

![image](https://github.com/user-attachments/assets/30bd4bea-e20f-4be8-a042-0dc18df825ac)

### Question 2
Write the SQL query that achieves the grouping of data by occupation, calculates the minimum work hours for each occupation, and excludes occupations where the minimum work hour is not greater than 8.

Sample table: employee1
```sql
select occupation,MIN(workhour) from employee1
GROUP BY occupation
HAVING MIN(workhour)!=8;
```

OUPUT

![image](https://github.com/user-attachments/assets/4661711e-2d50-468d-bb7b-045cffa5c1e0)


### Question 3
Write the SQL query that accomplishes the selection of product which has lowest price in each category from the "products" table and includes only those products where the minimum price is less than 10.

Sample table: products

```sql
select category_id,MIN(price) as Price from products
GROUP BY category_id
HAVING MIN(price)<10;
```
OUTPUT

![image](https://github.com/user-attachments/assets/6529c9d3-4794-4a18-9afd-71ba0ff06d1d)

### Question 4
Write the SQL query that accomplishes the grouping of data by age, calculates the average income for each age group, and includes only those age groups where the average income falls between 300,000 and 500,000.

Sample table: employee
```sql
select age,AVG(income) from employee
GROUP BY age
HAVING AVG(income) between 300000 and 500000;
```
OUTPUT

![image](https://github.com/user-attachments/assets/41bf120d-8dd4-40e0-92ea-6030d2438f3b)

### Question 5
Write a SQL query to find the total amount of fruits with a unit type of 'LB'.

Note: Inventory attribute contains amount of fruits
```sql
select sum(inventory) as total from fruits where unit='LB';
```
OUTPUT

![image](https://github.com/user-attachments/assets/15df161e-2472-4a54-ac2b-39391f57df21)


### Question 6
Write a SQL query to find the average length of email addresses (in characters):

Table: customer
```sql
select avg(LENGTH(email)) as avg_email_length from customer;
```

OUTPUT

![image](https://github.com/user-attachments/assets/430f051c-f036-48f3-b49b-0139aaf67a45)

### Question 7
Write a SQL query to find the Fruit with the lowest available quantity.

Note: Inventory attribute contains amount of fruits

Table: fruits

```sql
select name as fruit_name,min(inventory) as lowest_quantity from 
fruits;
```

OUTPUT

![image](https://github.com/user-attachments/assets/4517cbd6-3d29-440b-80ec-b42dea24e3e5)

### Question 8
Write a SQL query that counts the number of unique salespeople. Return number of salespeople.

Sample table: orders
```sql
select count( DISTINCT salesman_id) as COUNT from
orders;
```

OUTPUT

![image](https://github.com/user-attachments/assets/37e0e46d-9ca0-4215-95b8-8114322c061b)

### Question 9
How many prescriptions were written by each doctor?

Sample tablePrescriptions Table
```sql
select DoctorID,count(*) as TotalPrescriptions from
Prescriptions
GROUP BY DoctorID;
```
OUTPUT

![image](https://github.com/user-attachments/assets/baca60ab-90c7-4199-b154-60d0c9b83d3d)

### Question 10
Write a SQL Query to find how many medications are prescribed for each patient?

Sample table:MedicalRecords Table
```sql
select PatientID, count(*) as AvgMedications from MedicalRecords
GROUP BY PatientID;
```

OUTPUT

![image](https://github.com/user-attachments/assets/1916474c-ef6b-4f76-a60f-4539e3e3cd29)









## RESULT
![image](https://github.com/user-attachments/assets/f2fbdaf9-04c1-4353-8a49-f36b56608a39)

Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.

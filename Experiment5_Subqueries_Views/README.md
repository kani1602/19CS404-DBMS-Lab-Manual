
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
```
From the following tables, write a SQL query to find all the orders issued by the salesman 'Paul Adam'. Return ord_no, purch_amt, ord_date, customer_id and salesman_id.

salesman table

name             type
---------------  ---------------
salesman_id      numeric(5)
name             varchar(30)
city             varchar(15)
commission       decimal(5,2)

orders table

name             type
---------------  --------
order_no         int
purch_amt        real
order_date       text
customer_id      int
salesman_id      int
```

```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id = (
    SELECT salesman_id
    FROM salesman
    WHERE name = 'Paul Adam'
);
```

**Output:**

<img width="1238" height="371" alt="image" src="https://github.com/user-attachments/assets/9d257a50-17bd-4d08-b762-e7eae2a2489c" />

**Question 2**
---
```
From the following tables, write a SQL query to find all the orders generated in New York city. Return ord_no, purch_amt, ord_date, customer_id and salesman_id.

SALESMAN TABLE

name               type
-----------        ----------
salesman_id        numeric(5)
name               varchar(30)
city               varchar(15)
commission         decimal(5,2)

ORDERS TABLE

name            type
----------      ----------
ord_no          int
purch_amt       real
ord_date        text
customer_id     int
salesman_id     int
```

```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE salesman_id IN (
    SELECT salesman_id
    FROM salesman
    WHERE city = 'New York'
);
```

**Output:**

<img width="1233" height="477" alt="image" src="https://github.com/user-attachments/assets/72c462a6-83be-4eca-9db3-48c3486bc938" />

**Question 3**
---
```
Write a SQL query to retrieve all columns from the CUSTOMERS table for customers whose AGE is LESS than $30

Sample table: CUSTOMERS

ID          NAME        AGE         ADDRESS     SALARY
----------  ----------  ----------  ----------  ----------

1          Ramesh        32          Ahmedabad     2000
2          Khilan        25          Delhi         1500
3          Kaushik       23          Kota          2000
4          Chaitali      25          Mumbai        6500
5          Hardik        27          Bhopal        8500
6          Komal         22          Hyderabad     4500
7          Muffy         24          Indore        10000
```
```sql
select * from CUSTOMERS 
where AGE<30;
```

**Output:**

<img width="1228" height="565" alt="image" src="https://github.com/user-attachments/assets/a00b425c-8650-4a0e-b901-f45eb35f48f6" />


**Question 4**
---
Write a SQL query that retrieve all the columns from the table "Grades", where the grade is equal to the maximum grade achieved in each subject.

Sample table: GRADES (attributes: student_id, student_name, subject, grade)

<img width="754" height="284" alt="image" src="https://github.com/user-attachments/assets/d8f4f4b3-7f9d-4172-8dcb-1a4b31261305" />


```sql
SELECT *
FROM Grades
WHERE grade = (
    SELECT MAX(grade)
    FROM Grades AS g2
    WHERE g2.subject = Grades.subject
);

```

**Output:**

<img width="1233" height="434" alt="image" src="https://github.com/user-attachments/assets/27bf7cac-55e3-4383-a941-e9c33c3438bf" />

**Question 5**
---
Write a SQL query that retrieves the all the columns from the Table Grades, where the grade is equal to the minimum grade achieved in each subject.

Sample table: GRADES (attributes: student_id, student_name, subject, grade)
<img width="754" height="284" alt="image" src="https://github.com/user-attachments/assets/d8f4f4b3-7f9d-4172-8dcb-1a4b31261305" />

```sql
SELECT *
FROM Grades
WHERE grade = (
    SELECT MIN(grade)
    FROM Grades AS g2
    WHERE g2.subject = Grades.subject
);

```

**Output:**

<img width="1239" height="442" alt="image" src="https://github.com/user-attachments/assets/2a7c2379-fd87-4799-b1c7-b83aaa086715" />


**Question 6**
---
```
From the following tables write a SQL query to find all orders generated by London-based salespeople. Return ord_no, purch_amt, ord_date, customer_id, salesman_id.

salesman table

name             type
---------------  ---------------
salesman_id      numeric(5)
name             varchar(30)
city             varchar(15)
commission       decimal(5,2)

orders table

name             type
---------------  --------
order_no         int
purch_amt        real
order_date       text
customer_id      int
salesman_id      int

```
```sql
select * from orders
where salesman_id in (
select salesman_id from salesman
where city="London");
```

**Output:**

<img width="1232" height="400" alt="image" src="https://github.com/user-attachments/assets/7f344caa-0a6f-4ebc-8280-836b293e9cc9" />

**Question 7**
---
```
Write a SQL query to Identify customers whose city is different from the city of the customer with the highest ID

SAMPLE TABLE: customer

name             type
---------------  ---------------
id               INTEGER
name             TEXT
city             TEXT
email            TEXT
phone            INTEGER
```
```sql
SELECT *
FROM customer
WHERE city <> (
    SELECT city
    FROM customer
    WHERE id = (
        SELECT MAX(id)
        FROM customer
    )
);

```

**Output:**

<img width="1238" height="487" alt="image" src="https://github.com/user-attachments/assets/af83f628-ba0b-4cb8-b37a-2d6c1d4a8d37" />


**Question 8**
---
Write a SQL query to List departments with names longer than the average length

Departments Table (attributes: department_id, department_name)

<img width="993" height="161" alt="image" src="https://github.com/user-attachments/assets/d3b9e144-aef4-4656-9678-13520d965564" />


```sql
SELECT *
FROM departments
WHERE LENGTH(department_name) > (
    SELECT AVG(LENGTH(department_name))
    FROM departments
);

```

**Output:**

<img width="572" height="388" alt="image" src="https://github.com/user-attachments/assets/55e81161-5184-435a-a836-f162489e4387" />


**Question 9**
---
```
From the following tables write a SQL query to find the order values greater than the average order value of 10th October 2012. Return ord_no, purch_amt, ord_date, customer_id, salesman_id.

Note: date should be yyyy-mm-dd format

ORDERS TABLE

name            type
----------     ----------
ord_no          int
purch_amt       real
ord_date        text
customer_id     int
salesman_id     int
```

```sql
SELECT ord_no, purch_amt, ord_date, customer_id, salesman_id
FROM orders
WHERE purch_amt > (
    SELECT AVG(purch_amt)
    FROM orders
    WHERE ord_date = '2012-10-10'
);

```

**Output:**

<img width="1229" height="441" alt="image" src="https://github.com/user-attachments/assets/e56f0c6a-e3fd-4390-85be-76a225491b5d" />

**Question 10**
---
```
Write a SQL query to Find employees who have an age less than the average age of employees with incomes over 1 million

Employee Table

name             type

------------   ---------------

id              INTEGER

name            TEXT

age             INTEGER

city            TEXT

income          INTEGER
```

```sql
select * from Employee
where age < (
select avg(age) from Employee
where income>1000000);
```

**Output:**

<img width="1241" height="416" alt="image" src="https://github.com/user-attachments/assets/e87d6a38-7fd9-4ea3-81d7-ff75b64bf66b" />



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.

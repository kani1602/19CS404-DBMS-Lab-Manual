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

<img width="917" height="400" alt="image" src="https://github.com/user-attachments/assets/5ffb3f71-82de-4bb4-bc29-28f9bdbf6ba3" />

```
select gender, count(*) as TotalPatients
from patients 
group by Gender;
```

**Output:**

<img width="678" height="320" alt="image" src="https://github.com/user-attachments/assets/41e6a0f9-585d-473b-aec8-eccad39829ec" />


**Question 2**

<img width="926" height="564" alt="image" src="https://github.com/user-attachments/assets/905ff8a8-6fc7-4276-8d2b-b363806c05dd" />

```
select Medication, count(*) as TotalPrescriptions
from Prescriptions
group by Medication;
```

**Output:**

<img width="745" height="674" alt="image" src="https://github.com/user-attachments/assets/7a8a17b7-b5f7-4e73-9bc4-49e4267d39f4" />


**Question 3**

<img width="859" height="604" alt="image" src="https://github.com/user-attachments/assets/aa9c9d37-56b6-43d8-8fb1-36a96d793f55" />

```
select InsuranceCompany,
    avg(date(enddate)-date(startdate)) as AvgCoverageDurationDays
from Insurance
group by InsuranceCompany;
```

**Output:**

<img width="862" height="600" alt="image" src="https://github.com/user-attachments/assets/d20fced0-322b-4907-95eb-ae6c919ac02a" />


**Question 4**

<img width="884" height="496" alt="image" src="https://github.com/user-attachments/assets/b056d42d-dc4d-43a8-a690-ffb9b58a0728" />


```
select  sum(inventory) as total_available_amount
from fruits
where price>0.5;
```

**Output:**

<img width="574" height="273" alt="image" src="https://github.com/user-attachments/assets/ef615613-801d-43b6-a0ce-959569fd5deb" />

  
**Question 5**

<img width="853" height="462" alt="image" src="https://github.com/user-attachments/assets/6def8d5d-d799-4b1b-98d3-b522e1bc0bf8" />


```
select count(*) as COUNT
from customer 
where city = 'Noida';
```

**Output:**

<img width="362" height="260" alt="image" src="https://github.com/user-attachments/assets/e29c6775-3b65-4148-ba14-3c53ec1e4639" />

**Question 6**

<img width="733" height="423" alt="image" src="https://github.com/user-attachments/assets/882096b2-7e84-4a27-8c7b-73fc08ece5d8" />

```
select COUNT(DISTINCT city) as unique_cities
from customer;
```

**Output:**

<img width="451" height="274" alt="image" src="https://github.com/user-attachments/assets/ed12845e-2696-4441-9c55-5af92fba4682" />


**Question 7**

<img width="704" height="431" alt="image" src="https://github.com/user-attachments/assets/31db427c-d55a-4f0b-92c8-0191423c77d0" />


```
select count(*) as employees_count
from employee
where income>50000;
```

**Output:**

<img width="470" height="273" alt="image" src="https://github.com/user-attachments/assets/c6f267ab-d142-463f-8a03-20a9658ec705" />


**Question 8**
<img width="1234" height="452" alt="image" src="https://github.com/user-attachments/assets/699906a5-f120-4c24-af33-8b2bfa34f6cb" />


```
select age,max(income) as "MAX(income)"
from employee
group by age
having max(income)>2000000;
```

**Output:**

<img width="569" height="305" alt="image" src="https://github.com/user-attachments/assets/e5aeef05-329b-44a4-b93f-57430d78f6d5" />


**Question 9**

<img width="1252" height="426" alt="image" src="https://github.com/user-attachments/assets/e3f57f68-a701-4275-897e-aad2e1e22bb1" />


```
select category_id,avg(price) as "AVG(Price)"
from products
group by category_id
having avg(price) between 10 and 15;
```

**Output:**

<img width="589" height="293" alt="image" src="https://github.com/user-attachments/assets/ee164b36-b74d-4c24-94fc-8a7af96ac8c6" />


**Question 10**

<img width="1185" height="481" alt="image" src="https://github.com/user-attachments/assets/6eb2dd05-502b-4ccb-aa89-a8f722aaaf65" />


```
select occupation,min(workhour) as "MIN(workhour)"
from employee1
group by occupation
having min(workhour)>8;

```

**Output:**

<img width="650" height="426" alt="image" src="https://github.com/user-attachments/assets/ae01ec98-760c-4ac8-a473-78e3e733c7e6" />



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.

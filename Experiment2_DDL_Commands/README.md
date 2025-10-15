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
<img width="1317" height="437" alt="Screenshot 2025-10-15 154942" src="https://github.com/user-attachments/assets/de43b5e6-63bc-4c83-9e3d-545af567464b" />


```
insert into Employee(EmployeeID,Name,Position,Department,Salary)
values(5,'George Clark','Consultant',null,null),
(7,'Noah Davis','Manager','HR',60000),
(8,'Ava Miller','Consultant','IT',null);
```

**Output:**

<img width="1253" height="264" alt="Screenshot 2025-10-15 155011" src="https://github.com/user-attachments/assets/cd57f322-9b69-4a79-9200-7c46768bcae9" />


**Question 2**
---
<img width="1260" height="405" alt="Screenshot 2025-10-15 155025" src="https://github.com/user-attachments/assets/927a17af-2f53-4b12-8447-3d56ff4da83c" />


```
create table item(
item_id text primary key,
item_desc text not null,
rate integer not null,
icom_id text(4),
foreign key (icom_id) references company(com_id) on update set null on delete set null
);
```

**Output:**

<img width="1174" height="245" alt="Screenshot 2025-10-15 155246" src="https://github.com/user-attachments/assets/9f5c60fa-0d78-413b-a610-cbc28df379a8" />


**Question 3**
---
<img width="987" height="340" alt="Screenshot 2025-10-15 155301" src="https://github.com/user-attachments/assets/afee5bc1-f24e-4a5d-9b18-b0e33af3fb36" />


```
create table Locations(
LocationID INTEGER,
LocationName TEXT,
Address TEXT
);
```

**Output:**

<img width="1035" height="174" alt="Screenshot 2025-10-15 155323" src="https://github.com/user-attachments/assets/1f2780e1-fd05-4f28-a426-19229db2252b" />


**Question 4**
---
<img width="777" height="266" alt="Screenshot 2025-10-15 155335" src="https://github.com/user-attachments/assets/824ba854-7b2c-4732-829a-2d5a864a83ed" />


```
insert into Customers(CustomerID,Name,Address,Email)
select CustomerID,Name,Address,Email from Old_Customers;
```

**Output:**

<img width="1206" height="192" alt="Screenshot 2025-10-15 155503" src="https://github.com/user-attachments/assets/cd85e23c-f095-4672-a685-f02f80474012" />


**Question 5**
---
<img width="863" height="185" alt="Screenshot 2025-10-15 155509" src="https://github.com/user-attachments/assets/0496e16c-dab4-4951-bf7c-46f1dea57364" />


```
insert into Employee(EmployeeID,Name,Position,Department,Salary)
values(001,'Sarah Parker','Manager','HR',60000);
```

**Output:**

<img width="1248" height="154" alt="Screenshot 2025-10-15 155517" src="https://github.com/user-attachments/assets/b3ff3b24-c2b1-4869-8376-16501c6aaa30" />


**Question 6**
---
<img width="1164" height="268" alt="Screenshot 2025-10-15 155525" src="https://github.com/user-attachments/assets/76021cce-5206-4ddd-850b-7f9e7e0789ac" />


```
create table Orders(
OrderID integer primary key,
OrderDate date not null,
CustomerID integer,
foreign key (CustomerID) references Customers(CustomerID)
);
```

**Output:**

<img width="993" height="126" alt="Screenshot 2025-10-15 155539" src="https://github.com/user-attachments/assets/b9f2726a-f393-40d6-8f94-8e4b0458a771" />


**Question 7**
---

<img width="1238" height="354" alt="Screenshot 2025-10-15 155549" src="https://github.com/user-attachments/assets/ef6f02d6-99cf-4ea4-8f18-0bfcd049333c" />


```
create table orders(
ord_id text check(length(ord_id)=4) not null,
item_id text not null,
ord_date date,
ord_qty integer,
cost integer,
primary key (item_id,ord_date)
);
```

**Output:**

<img width="1122" height="146" alt="Screenshot 2025-10-15 155603" src="https://github.com/user-attachments/assets/891362c6-252b-4dd4-805f-b4004ccb597e" />


**Question 8**
---
<img width="940" height="492" alt="Screenshot 2025-10-15 155617" src="https://github.com/user-attachments/assets/6b153688-3ed0-4d93-948d-ca64dd4e2635" />


```
alter table Student_details
add Mobilenumber number;
```

**Output:**

<img width="1199" height="223" alt="Screenshot 2025-10-15 155625" src="https://github.com/user-attachments/assets/b32b15d2-12bd-40e5-ab38-4acb2ce2aa5c" />


**Question 9**
---
<img width="692" height="292" alt="Screenshot 2025-10-15 155635" src="https://github.com/user-attachments/assets/668f0cb1-a951-448e-b78a-71c7bcc0995e" />


```
create table Products(
ProductID primary key,
ProductName not null,
Price real check(Price>0),
Stock integer check(Stock>=0)
);
```

**Output:**

<img width="1169" height="201" alt="Screenshot 2025-10-15 155728" src="https://github.com/user-attachments/assets/922dc117-f493-4bcb-a4c0-300a386d877a" />


**Question 10**
---
<img width="925" height="485" alt="Screenshot 2025-10-15 155743" src="https://github.com/user-attachments/assets/85dc4d94-6d52-439c-ad45-eb30b3fecfdc" />


```
alter table Student_details
add Country TEXT;
```

**Output:**

<img width="1237" height="229" alt="Screenshot 2025-10-15 155754" src="https://github.com/user-attachments/assets/ae84bf58-64bd-4e2b-b153-2877f1d5e80e" />

**Score:**

<img width="1412" height="176" alt="image" src="https://github.com/user-attachments/assets/a0bc4eb9-2988-45ee-93f7-e1fed51ca097" />


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

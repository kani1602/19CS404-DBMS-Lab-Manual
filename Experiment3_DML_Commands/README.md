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


<img width="933" height="355" alt="image" src="https://github.com/user-attachments/assets/e0232bdc-1ad4-4f53-ad24-23a23ea66acd" />

```
update PRODUCTS set sell_price=sell_price+(sell_price*0.10) where supplier_id=6;
```

**Output:**

<img width="1191" height="257" alt="image" src="https://github.com/user-attachments/assets/e3008543-0dc3-4f18-8b8f-675e1bb5b9c8" />


**Question 2**

<img width="1182" height="333" alt="image" src="https://github.com/user-attachments/assets/eef1c663-bc8a-4e85-a518-f870c6710ad0" />


```
update PRODUCTS set reorder_lvl=reorder_lvl-(reorder_lvl*0.30) where product_name like '%cream%' and quantity>reorder_lvl;
```

**Output:**

<img width="1348" height="236" alt="image" src="https://github.com/user-attachments/assets/3fba50ab-0786-42b2-b1c5-d96fba6606a8" />


**Question 3**

<img width="1231" height="417" alt="image" src="https://github.com/user-attachments/assets/bc2a1d8c-24fe-4cbf-b4ee-4cc92caff5f5" />

```
update Employees set email='not available' , commission_pct=0.55 where department_id=110;
```

**Output:**

<img width="1277" height="285" alt="image" src="https://github.com/user-attachments/assets/bfeff1bd-19e5-4034-855a-f384d27dd4df" />


**Question 4**

<img width="811" height="261" alt="image" src="https://github.com/user-attachments/assets/dbff30fb-3153-430c-8b19-d978eb97d90e" />


```
update Products set category = 'Household' where product_name like '%Detergent%';
```

**Output:**

<img width="1277" height="233" alt="image" src="https://github.com/user-attachments/assets/99d14e12-2613-4fe0-b6bc-b19265787084" />


**Question 5**

<img width="1080" height="410" alt="image" src="https://github.com/user-attachments/assets/1381f135-5ac6-477b-8ff4-fcc1475538ec" />


```
update Employees set email = 'Unavailable';
```

**Output:**

<img width="1201" height="373" alt="image" src="https://github.com/user-attachments/assets/29de85be-6d4b-4f79-adbd-8e313cd6644b" />


**Question 6**

<img width="1283" height="222" alt="image" src="https://github.com/user-attachments/assets/78c26181-3fc1-4ed3-99f3-7f7eb5d713f9" />


```
delete from Customer where GRADE=2 and CUST_NAME like 'M%' and PAYMENT_AMT<3000;
```

**Output:**

<img width="1349" height="204" alt="image" src="https://github.com/user-attachments/assets/b52b52ee-df38-4676-b3af-b40207450023" />


**Question 7**

<img width="851" height="288" alt="image" src="https://github.com/user-attachments/assets/27aeb3f9-5245-4cf8-aa63-0be0c3ad4417" />


```
delete from Surgeries where surgery_id=3 or surgeon_id=4;
```

**Output:**

<img width="1111" height="813" alt="image" src="https://github.com/user-attachments/assets/803efaf8-833a-4ba8-bf7d-5cba8eaea810" />


**Question 8**

<img width="1279" height="216" alt="image" src="https://github.com/user-attachments/assets/cea6b60a-5657-43ce-977c-84ff6a607ffc" />


```
delete from Customer where CUST_COUNTRY not in ('India','USA');
```

**Output:**

<img width="1296" height="367" alt="image" src="https://github.com/user-attachments/assets/63021458-d0ea-480f-9410-fab34fcd5f24" />


**Question 9**

<img width="748" height="508" alt="image" src="https://github.com/user-attachments/assets/79c36ec7-ba16-4ad9-a90c-5c360a640244" />


```
delete from Doctors where last_name is  NULL;
```

**Output:**

<img width="1128" height="619" alt="image" src="https://github.com/user-attachments/assets/374485b4-ed11-48a9-a5c5-869edd4ca812" />


**Question 10**

<img width="969" height="145" alt="image" src="https://github.com/user-attachments/assets/7c5fe9b9-840b-4393-b3b2-8c78e20e0431" />


```
delete from Doctors where specialization = 'Cardiology';
```

**Output:**

<img width="1133" height="320" alt="image" src="https://github.com/user-attachments/assets/f5a817a6-0878-4bed-805c-1ffc295f3b44" />


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

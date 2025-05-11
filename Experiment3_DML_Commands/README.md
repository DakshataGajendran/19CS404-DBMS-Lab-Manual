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
![image](https://github.com/user-attachments/assets/610ac1e9-da05-493f-9058-82bb879ccdfe)

```sql
update employees
set first_name = 'John'
where department_id = 80 and 
commission_pct < 0.35 ;
```

**Output:**

![image](https://github.com/user-attachments/assets/127b23d4-f0f1-487f-962d-e61b7d309230)


**Question 2**
---
![image](https://github.com/user-attachments/assets/cc4d3b47-b265-4087-b503-6a7c1c9b2b15)

```sql
update suppliers
set supplier_name = upper(supplier_name)
where contact_person like '%Singh%';
```

**Output:**
![image](https://github.com/user-attachments/assets/e96c315f-1ebb-4eb5-85ec-ff14c40781c2)


**Question 3**
---
![image](https://github.com/user-attachments/assets/cad41593-7508-4900-8a59-8dc9a9d07165)


```sql
update products 
set reorder_lvl = reorder_lvl * 0.7
where cost_price > 50
and quantity < 100;
```

**Output:**
![image](https://github.com/user-attachments/assets/6ed47a08-a5ce-4355-8541-daca64a3b218)


**Question 4**
---
![image](https://github.com/user-attachments/assets/44b7f809-87ce-4585-88cf-2ae6ca17cd6e)


```sql
update products 
set availability = availability * 2
where product_id =1;
```

**Output:**

![image](https://github.com/user-attachments/assets/b3eb1bed-c77b-4779-a19f-1dbefdd020d3)


**Question 5**
---
![image](https://github.com/user-attachments/assets/e9266bad-a178-44d6-b312-c52977189a09)


```sql
update employees
set email = 'not available',
commission_pct = 0.55
where department_id =110;
```

**Output:**

![image](https://github.com/user-attachments/assets/fb135b6f-20cd-45b1-bf38-abb79b9595cd)


**Question 6**
---
![image](https://github.com/user-attachments/assets/e344a610-7e58-41d4-ae80-028b614f7897)


```sql
delete from customer where cust_country not in ('UK','USA','Canada') and grade >= 3;
```

**Output:**
![image](https://github.com/user-attachments/assets/22384a10-602e-428c-b8c9-4ed6b71606f9)

**Question 7**
---
![image](https://github.com/user-attachments/assets/400b5a08-1897-4f7f-b6d7-4661565476d1)


```sql
delete from Doctors where specialization = 'Cardiology';
```

**Output:**

![image](https://github.com/user-attachments/assets/c98b4e6b-eb9f-4e07-9624-d93f49305170)


**Question 8**
---
![image](https://github.com/user-attachments/assets/38f1330c-dfb8-4e76-8ce0-04d00eaf8f20)


```sql
delete from Customer where (GRADE =3 or AGENT_CODE = 'A008')and OUTSTANDING_AMT < 5000;
```

**Output:**

![image](https://github.com/user-attachments/assets/dca2efac-405d-4769-acc2-e27ddce76949)

**Question 9**
---

![image](https://github.com/user-attachments/assets/18c3e210-39e5-47af-93fe-8cbfa3234106)

```sql
delete from Customer where CUST_NAME like '%Holmes%';
```

**Output:**
![image](https://github.com/user-attachments/assets/fff07a44-0b7f-402a-92ed-5e3ef7f18093)

**Question 10**
---
![image](https://github.com/user-attachments/assets/2f455271-739b-443b-aa56-360351e841ae)


```sql
delete from Customer where AGENT_CODE in ('A003','A008');
```

**Output:**
![image](https://github.com/user-attachments/assets/1bddad8d-adb8-4882-9833-4d8e72e2f4d2)


## RESULT
Thus, the SQL queries to implement DML commands have been executed successfully.

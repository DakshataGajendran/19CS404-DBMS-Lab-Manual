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
![image](https://github.com/user-attachments/assets/988fd11e-75c1-42d3-b6a3-491dd2338c5f)


```sql
create table Events(
EventID INTEGER,
EventName TEXT,
EventDate  DATE);

```

**Output:**

![image](https://github.com/user-attachments/assets/2e0ebb82-538e-469f-88a4-1397cdd99e91)


**Question 2**
---
![image](https://github.com/user-attachments/assets/a774a2e5-208f-4d0d-9d27-09ef11e94850)


```sql
create table Shipments(
ShipmentID INTEGER primary key,
ShipmentDate DATE,
SupplierID INTEGER,
OrderID INTEGER,
foreign key (SupplierID) references Suppliers(SupplierID),
foreign key (OrderID) references  Orders(OrderID));

```

**Output:**

![image](https://github.com/user-attachments/assets/b139e1fd-ddb4-4004-8732-faa348956471)


**Question 3**
---
![image](https://github.com/user-attachments/assets/1259c172-3fc1-445a-ac2f-cb446bf5c60a)


```sql
alter table employee add column first_name varchar(50);
alter table employee add column last_name varchar(50);
```

**Output:**

![image](https://github.com/user-attachments/assets/46601632-6b0a-4ce8-a43f-7c0a5bbe8953)


**Question 4**
---

![image](https://github.com/user-attachments/assets/111b2368-35f8-4043-810f-7aee53d7a629)


```sql
insert into Employee(EmployeeID,Name,Position) values (5,'George Clark','Consultant');
insert into Employee(EmployeeID,Name,Position,Department,Salary) values (7,'Noah Davis','Manager','HR', 60000);
insert into Employee(EmployeeID,Name,Position,Department)values (8,'Ava Miller','Consultant','IT');
```

**Output:**

![image](https://github.com/user-attachments/assets/008f2bfb-77c5-4c5a-9737-f6bcfdb697c2)


**Question 5**
---

![image](https://github.com/user-attachments/assets/73160fb4-0469-4d14-a801-9e798e5061e4)

```sql
alter table employee rename column id to employee_id;
```

**Output:**

![image](https://github.com/user-attachments/assets/176b6fad-bc50-4f47-aba2-0772b7f29dc1)


**Question 6**
---

![image](https://github.com/user-attachments/assets/40aa3cbb-22c8-40db-b5d2-96be49849ef3)


```sql
create table Members(
MemberID INTEGER,
MemberName TEXT,
JoinDate DATE);

```

**Output:**

![image](https://github.com/user-attachments/assets/0bdfe8ad-4ecc-42c7-aa16-c0a617d3daa9)


**Question 7**
---

![image](https://github.com/user-attachments/assets/43dbfa57-1fc1-4b9e-adc5-8cf1159546ff)


```sql
create table Invoices(
InvoiceID INTEGER primary key,
InvoiceDate DATE NOT NULL,
Amount REAL check(Amount >0),
DueDate DATE check(DueDate > InvoiceDate),
OrderID INTEGER ,
FOREIGN KEY (OrderID) REFERENCES Orders(OrderID));
```

**Output:**

![image](https://github.com/user-attachments/assets/6586bba4-c6ca-4982-9606-5827ad0d1708)


**Question 8**
---

![image](https://github.com/user-attachments/assets/b8f8e9a3-5960-483d-be24-311bfbd8bd62)


```sql
alter table Companies ADD designation varchar(50);
alter table Companies ADD net_salary  number;
alter table Companies ADD dob date;
```

**Output:**

![image](https://github.com/user-attachments/assets/249680f6-11f3-4397-84f2-208af3932b34)


**Question 9**
---

![image](https://github.com/user-attachments/assets/a3ee4890-2a3f-4172-8113-7e9cec342f4d)


```sql
create table item(
item_id TEXT primary key,
item_desc TEXT,
rate INTEGER,
icom_id TEXT,
foreign key(icom_id) references company(com_id) on update cascade on delete cascade,
check(length(icom_id)=4)
);
```

**Output:**


![image](https://github.com/user-attachments/assets/61985adf-11fe-42e7-9abc-10face5251d1)


**Question 10**
---

![image](https://github.com/user-attachments/assets/e77e29ab-e9ab-443b-a836-7dcfbbb39c8d)


```sql
alter table Student_details add ParentsNumber number;
alter table Student_details add Adhar_Number number;
```

**Output:**
![image](https://github.com/user-attachments/assets/5500c7f3-c520-4af2-a005-7ac9bdf046ec)


## RESULT
Thus, the SQL queries to implement different types of constraints and DDL commands have been executed successfully.

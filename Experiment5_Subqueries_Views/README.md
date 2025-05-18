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
![image](https://github.com/user-attachments/assets/24cc2cb5-9abc-4a80-a929-75824e7c01e9)


```sql
select o.ord_no,o.purch_amt,c.cust_name,c.city
from orders o inner join customer c 
on o.customer_id=c.customer_id
where o.purch_amt between 500 and 2000
```

**Output:**

![image](https://github.com/user-attachments/assets/e493a1f7-2157-46d3-aeb0-2615782e9c16)


**Question 2**
---
![image](https://github.com/user-attachments/assets/6d881d42-21f5-4acd-b6eb-d1e629010345)


```sql
select s.* from Salesman s left join Customer c on s.salesman_id=c.salesman_id where c.cust_name = 'Fabian Johns'
```

**Output:**

![image](https://github.com/user-attachments/assets/5e934b80-034a-43f7-a526-2a2d91042a72)


**Question 3**
---
![image](https://github.com/user-attachments/assets/eda0feb2-b314-4de6-b0b9-310f1862dfd0)


```sql
select p.first_name as "patient_name" from PATIENTS p inner join TEST_RESULTS t 
on p.patient_id=t.patient_id 
where t.test_name = 'Blood Pressure'
```

**Output:**

![image](https://github.com/user-attachments/assets/dbb8e062-ce6b-4f9a-837c-1680c3285d6c)


**Question 4**
![image](https://github.com/user-attachments/assets/f7681b7e-a4d1-48d7-8928-6ceed8bf4f12)


```sql
select o.ord_no,o.purch_amt,o.ord_date,c.cust_name,c.city as "customer_city",c.grade,s.name as "salesman_name",s.city as "salesman_city",s.commission
from orders o join customer c on o.customer_id=c.customer_id
join salesman s on o.salesman_id=s.salesman_id
```

**Output:**

![image](https://github.com/user-attachments/assets/993cbb3a-305b-4ad1-8766-8bf48dea814b)


**Question 5**
---

![image](https://github.com/user-attachments/assets/1cfda04a-515d-4c2a-ac08-6ff32ef6812f)


```sql
select t.* from TEST_RESULTS t inner join PATIENTS p on p.patient_id = t.patient_id where first_name = "Alice"

```

**Output:**

![image](https://github.com/user-attachments/assets/94557e22-ae2c-44ac-aaa5-49f74db22d90)


**Question 6**
---

![image](https://github.com/user-attachments/assets/ae71be6b-eecf-4d10-a151-a44ae572a3a1)


```sql
SELECT 
    o.ord_no,
    o.ord_date,
    o.purch_amt,
    c.cust_name AS "Customer Name",
    c.grade,
    s.name AS "Salesman",
    s.commission
FROM 
    orders o
JOIN 
    customer c ON o.customer_id = c.customer_id
JOIN 
    salesman s ON o.salesman_id = s.salesman_id;

```

**Output:**

![image](https://github.com/user-attachments/assets/5eb646a3-6f3d-4769-8178-86b71881afb4)


**Question 7**
---

![image](https://github.com/user-attachments/assets/7c9c8815-241d-4b02-a424-ae5ed6479e8a)


```sql
SELECT 
    p.first_name AS patient_name,
    t.*
FROM 
    test_results t
INNER JOIN 
    patients p ON t.patient_id = p.patient_id
WHERE 
    p.admission_date BETWEEN '2024-01-01' AND '2024-01-31';
```

**Output:**

![image](https://github.com/user-attachments/assets/f1f3552f-e245-4794-a9d9-9352ddc0453c)


**Question 8**
---

![image](https://github.com/user-attachments/assets/1e178ce4-eb5c-4ab6-a2bf-e5b3ac65615b)


```sql
SELECT 
    c.cust_name,
    c.city ,
    c.grade,
    s.name AS Salesman,
    s.city AS city
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id
ORDER BY 
    c.customer_id ASC;

```

**Output:**

![image](https://github.com/user-attachments/assets/d99654f4-1de9-43c4-b180-dbaa4b1b076a)



**Question 9**
---

![image](https://github.com/user-attachments/assets/158c3493-0678-4e49-90f2-618078b4783a)

```sql
SELECT 
    c.cust_name,
    c.city ,
    c.grade,
    s.name AS Salesman,
    s.city
FROM 
    customer c
JOIN 
    salesman s ON c.salesman_id = s.salesman_id
WHERE 
    c.grade < 300
ORDER BY 
    c.customer_id ASC;


```

**Output:**

![image](https://github.com/user-attachments/assets/22e9f4a5-5791-43e5-aff6-7f029aecb337)


**Question 10**
---

![image](https://github.com/user-attachments/assets/e5778ab6-300b-402b-8f90-0aac2c160efa)


```sql
SELECT DISTINCT s.name
FROM salesman s
LEFT JOIN customer c ON s.salesman_id = c.salesman_id
WHERE c.city = 'London';


```

**Output:**

![image](https://github.com/user-attachments/assets/0b504c2b-cf3a-4ca9-8bdd-16ce08e3ff90)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.

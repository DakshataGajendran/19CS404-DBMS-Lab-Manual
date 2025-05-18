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
![image](https://github.com/user-attachments/assets/672dff9d-dc0d-47fb-bcf5-3c2b137b00d0)

```sql
SELECT * FROM CUSTOMERS WHERE AGE<30;
```

**Output:**

![image](https://github.com/user-attachments/assets/5561af8b-7549-48ac-8150-144d8c4fcab4)

**Question 2**
---
![image](https://github.com/user-attachments/assets/29aebadf-03f3-4e0e-b6d2-8c9496ff90b2)

```sql
SELECT * FROM ORDERS WHERE salesman_id in (SELECT salesman_id FROM SALESMAN WHERE city='New York');
```

**Output:**

![image](https://github.com/user-attachments/assets/cf1b1c1c-78de-40e1-88ba-02f7e15aee87)

**Question 3**
---
![image](https://github.com/user-attachments/assets/cb7ef18c-e9c6-4cd9-8079-3605a805b3b6)

```sql
SELECT salesman_id, name FROM salesman WHERE salesman_id IN (SELECT salesman_id FROM customer GROUP BY salesman_id HAVING COUNT(customer_id)>1);
```

**Output:**

![image](https://github.com/user-attachments/assets/bac95387-b1d7-45fb-9b3b-79b7eeb0a8de)

**Question 4**
---
![image](https://github.com/user-attachments/assets/1ae021bf-80fc-45ca-bd75-ae8129811048)

```sql
SELECT medication_id AS medic, medication_name, dosage FROM Medications WHERE dosage=(SELECT MAX(dosage) FROM Medications);
```

**Output:**

![image](https://github.com/user-attachments/assets/c7eb764f-6434-4b13-9941-ec3299991ca5)

**Question 5**
---
![image](https://github.com/user-attachments/assets/be29cded-1017-4c97-8ddf-b81bcba7ed8b)

```sql
SELECT * FROM orders WHERE salesman_id IN (SELECT salesman_id FROM salesman WHERE city='London');
```

**Output:**

![image](https://github.com/user-attachments/assets/b22a69a7-7633-4244-af07-a1994afb9562)

**Question 6**
---
-- ![image](https://github.com/user-attachments/assets/b43fdf96-feed-4630-8cc8-5fc6a22e5cc9)


```sql
-- SELECT *
FROM CUSTOMERS
WHERE SALARY < 2500;
```

**Output:**

![image](https://github.com/user-attachments/assets/bd2f6ab4-634d-496c-aa4d-2dfa49220605)


**Question 7**
---
-- ![image](https://github.com/user-attachments/assets/68418b73-c953-49ff-aefa-79cf7e33afd1)


```sql
-- SELECT *
FROM CUSTOMERS
WHERE ADDRESS = 'Delhi';
```

**Output:**

![image](https://github.com/user-attachments/assets/c48f9d71-e923-4141-ba1d-158942f30545)


**Question 8**
---
-- ![image](https://github.com/user-attachments/assets/e8e88ffc-e873-4623-8c9f-54ae8f9ca142)


```sql
-- SELECT name
FROM customer
WHERE phone NOT IN (
    SELECT phone
    FROM customer
    GROUP BY phone
    HAVING COUNT(phone) > 1
);
```

**Output:**

![image](https://github.com/user-attachments/assets/9201cbdd-7e3b-4871-baad-63ea191a4666)


**Question 9**
---
-- ![image](https://github.com/user-attachments/assets/e44a2306-a371-4ee5-aa0b-c670c72ea42b)


```sql
-- select  * from orders where salesman_id in (select salesman_id from salesman where name='Paul Adam');
```

**Output:**

![image](https://github.com/user-attachments/assets/42be4875-2eb4-40ec-9200-695e1271b020)


**Question 10**
---
-- ![image](https://github.com/user-attachments/assets/5399e750-d2d0-41ac-9ca7-b36b78350b25)


```sql
-- select * from Employee where age<(select avg(age) from Employee where income>1000000);
```

**Output:**

![image](https://github.com/user-attachments/assets/cbf2f68a-0875-45a3-b6bc-e310b31379c9)



## RESULT
Thus, the SQL queries to implement subqueries and views have been executed successfully.


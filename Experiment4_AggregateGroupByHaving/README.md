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
---
![image](https://github.com/user-attachments/assets/f04ded3c-f9a9-4a5b-8a2a-6ad93d9ae5a2)


```sql
SELECT Medication, count(*) as TotalPrescriptions from Prescriptions GROUP BY Medication;
```

**Output:**
![image](https://github.com/user-attachments/assets/86529338-6e4c-48a2-82ff-d672366e7c70)

**Question 2**
---
![image](https://github.com/user-attachments/assets/13ee6e0e-bd4e-4e2a-b39e-1f7e5758969a)


```sql
select Gender, count(*) as TotalPatients from Patients group by Gender;
```

**Output:**
![image](https://github.com/user-attachments/assets/bfe784c2-2437-4262-b8e0-718a1b174251)


**Question 3**
---
![image](https://github.com/user-attachments/assets/2512ee5c-a6e7-4f1b-86e6-987fad8608f1)


```sql
select date(AppointmentDateTime) as AppointmentDate,
count(*) as TotalAppointments from  Appointments group by date(AppointmentDateTime) order by AppointmentDate;
```

**Output:**
![image](https://github.com/user-attachments/assets/da805e1d-d19b-4c31-b7db-f0b96766759b)

**Question 4**
---
![image](https://github.com/user-attachments/assets/96a33d20-9d8a-4996-b8e2-7757bd175cfa)


```sql
select count(*) as COUNT from customer where city = 'Noida';
```

**Output:**

![image](https://github.com/user-attachments/assets/fa6cd22b-c8d0-458a-ac66-e03f1d517255)


**Question 5**
---
![image](https://github.com/user-attachments/assets/8ce85d5c-5556-4559-8b3f-f5c3d3bf0e4b)


```sql
select COUNT(*) as COUNT from customer where grade is not null;
```

**Output:**

![image](https://github.com/user-attachments/assets/ff61b499-87b5-484d-8a2a-e66c41d0237c)


**Question 6**
---
![image](https://github.com/user-attachments/assets/6f0ca657-b0e4-42a6-823e-0c6e06d1f2fe)


```sql
select SUM(income) as "total_income" from employee where age >= 40;
```

**Output:**
![image](https://github.com/user-attachments/assets/9d27319f-e044-401b-8027-cb27bec6664c)


**Question 7**
---
![image](https://github.com/user-attachments/assets/494e07c9-fb29-4d26-966e-a717371fb103)


```sql
select address,SUM(salary) from customer1 group by address having sum(salary) > 2000;
```

**Output:**
![image](https://github.com/user-attachments/assets/fdbd7825-c8e1-4d16-947f-e4e235a7602c)


**Question 8**
---
![image](https://github.com/user-attachments/assets/cf860c6a-6030-4b11-ad26-8ce1ff0b1179)

```sql
select city, SUM(income) as Income from employee group by city having SUM(income) > 200000;
```

**Output:**

![image](https://github.com/user-attachments/assets/277ce56d-e50e-4381-a637-6d4b748ddc5c)


**Question 9**
---
![image](https://github.com/user-attachments/assets/6bec265c-622b-4ee5-8542-bda00af11d5e)


```sql
select jdate, MAX(workhour) from employee1 group by jdate having MAX(workhour) > 12;
```

**Output:**

![image](https://github.com/user-attachments/assets/877d43bf-c20a-48d3-8ae5-4392d343fb79)


**Question 10**
---
![image](https://github.com/user-attachments/assets/74df017d-aaf7-48dd-9970-37df934be482)


```sql
select DoctorID,count(*) as TotalPrescriptions from Prescriptions group by DoctorID
```

**Output:**

![image](https://github.com/user-attachments/assets/54bda26f-9c93-48fd-ad64-5c90b7b7d655)



## RESULT
Thus, the SQL queries to implement aggregate functions, GROUP BY, and HAVING clause have been executed successfully.

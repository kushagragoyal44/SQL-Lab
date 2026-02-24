# SQL Lab – Experiment 2
## Aim
To retrieve data from tables using basic SQL queries with conditions and filtering.

### Question 1
List all distinct job in Employee.
### Query
```sql
SELECT DISTINCT JOB
FROM EMPLOYEE;
```

### Question 2
List all information about employee in Department Number 30.
### Query
```sql
SELECT *
FROM EMPLOYEE
WHERE DEPTNO = 30;
```

### Question 3
Find all department number with department names greater than 20.
### Query
```sql
SELECT DEPTNO, DNAME
FROM DEPARTMENT
WHERE DEPTNO > 20;
```

### Question 4
Find all information about all the managers as well as the clerks in department 30.
### Query
```sql
SELECT *
FROM EMPLOYEE
WHERE (JOB = 'MANAGER' OR JOB = 'CLERK')
AND DEPTNO = 30;
```

### Question 5
List the Employee name, Employee numbers and department of all clerks.
### Query
```sql
SELECT ENAME, EMPNO, DEPTNO
FROM EMPLOYEE
WHERE JOB = 'CLERK';
```

### Question 6
Find all managers not in department 30.
### Query
```sql
SELECT *
FROM EMPLOYEE
WHERE JOB = 'MANAGER'
AND DEPTNO <> 30;
```

### Question 7
List information about all Employees in department 10 who are not manager or clerks.
### Query
```sql
SELECT *
FROM EMPLOYEE
WHERE DEPTNO = 10
AND JOB NOT IN ('MANAGER', 'CLERK');
```

### Question 8
Find Employees and jobs earning between 1200 and 1400.
### Query
```sql
SELECT ENAME, JOB, SAL
FROM EMPLOYEE
WHERE SAL BETWEEN 1200 AND 1400;
```

### Question 9
List Name and Department Number of employee who are clerks, analyst or salesman.
### Query
```sql
SELECT ENAME, DEPTNO
FROM EMPLOYEE
WHERE JOB IN ('CLERK', 'ANALYST', 'SALESMAN');
```

### Question 10
List Name and Department Number of employee whose names began with M.
### Query
```sql
SELECT ENAME, DEPTNO
FROM EMPLOYEE
WHERE ENAME LIKE 'M%';
```
# SQL Lab – Experiment 7
## Aim
To perform advanced queries using grouping, subqueries, matrix queries, and salary comparisons.

### Question 1
Compute the no. of days remaining in this year.
### Query
```sql
SELECT (TO_DATE('31-DEC-' || TO_CHAR(SYSDATE,'YYYY'),'DD-MON-YYYY') - SYSDATE) AS DAYS_REMAINING
FROM DUAL;
```

### Question 2
Find the highest and lowest salaries and the difference between them.
### Query
```sql
SELECT MAX(SAL) AS HIGHEST_SALARY,
       MIN(SAL) AS LOWEST_SALARY,
       (MAX(SAL) - MIN(SAL)) AS DIFFERENCE
FROM EMPLOYEE;
```

### Question 3
List employee whose commission is greater than 25 % of their salaries.
### Query
```sql
SELECT *
FROM EMPLOYEE
WHERE COMM > (SAL * 0.25);
```

### Question 4
Make a query that displays salary in dollar format.
### Query
```sql
SELECT ENAME,
       TO_CHAR(SAL,'$99,999.99') AS SALARY_IN_DOLLAR
FROM EMPLOYEE;
```

### Question 5
Create a matrix query to display the job, the salary for that job based on department number, and the total salary for that job for all departments, giving each column an appropriate heading.
### Query
```sql
SELECT JOB,
       SUM(DECODE(DEPTNO,10,SAL)) AS DEPT10,
       SUM(DECODE(DEPTNO,20,SAL)) AS DEPT20,
       SUM(DECODE(DEPTNO,30,SAL)) AS DEPT30,
       SUM(DECODE(DEPTNO,40,SAL)) AS DEPT40,
       SUM(SAL) AS TOTAL
FROM EMPLOYEE
GROUP BY JOB;
```

### Question 6
Query that will display the total no of employees, and of that total the number who were hired in 1980,1981,1982 and 1983. Give appropriate column heading.
### Query
```sql
SELECT COUNT(*) AS TOTAL_EMPLOYEES,
       SUM(DECODE(TO_CHAR(HIREDATE,'YYYY'),'1980',1,0)) AS Y1980,
       SUM(DECODE(TO_CHAR(HIREDATE,'YYYY'),'1981',1,0)) AS Y1981,
       SUM(DECODE(TO_CHAR(HIREDATE,'YYYY'),'1982',1,0)) AS Y1982,
       SUM(DECODE(TO_CHAR(HIREDATE,'YYYY'),'1983',1,0)) AS Y1983
FROM EMPLOYEE;
```

### Question 7
Query to get the last Sunday of Any Month.
### Query
```sql
SELECT NEXT_DAY(LAST_DAY(SYSDATE) - 7, 'SUNDAY') AS LAST_SUNDAY
FROM DUAL;
```

### Question 8
Display department numbers and total number of employees working in each department.
### Query
```sql
SELECT DEPTNO,
       COUNT(*) AS TOTAL_EMPLOYEES
FROM EMPLOYEE
GROUP BY DEPTNO;
```

### Question 9
Display the various jobs and total number of employees within each job group.
### Query
```sql
SELECT JOB,
       COUNT(*) AS TOTAL_EMPLOYEES
FROM EMPLOYEE
GROUP BY JOB;
```

### Question 10
Display the department numbers and total salary for each department.
### Query
```sql
SELECT DEPTNO,
       SUM(SAL) AS TOTAL_SALARY
FROM EMPLOYEE
GROUP BY DEPTNO;
```
# SQL Lab – Experiment 8
## Aim
To perform SQL queries using joins and subqueries to retrieve related data from multiple tables and generate detailed reports.

### Question 1
Display all employees with their dept name.
### Query
```sql
SELECT EMPLOYEE.ENAME, DEPARTMENT.DNAME
FROM EMPLOYEE
JOIN DEPARTMENT
ON EMPLOYEE.DEPTNO = DEPARTMENT.DEPTNO;
```

### Question 2
Display those employees whose manager name is JONES, and also display their manager name.
### Query
```sql
SELECT EMPLOYEE.ENAME AS EMPLOYEE_NAME,
       MANAGER.ENAME AS MANAGER_NAME
FROM EMPLOYEE
JOIN EMPLOYEE MANAGER
ON EMPLOYEE.MGR = MANAGER.EMPNO
WHERE MANAGER.ENAME = 'JONES';
```

### Question 3
Display employee name, his job, his dept name, his manager name, his grade and make out of an under department wise.
### Query
```sql
SELECT DEPARTMENT.DNAME,
       EMPLOYEE.ENAME,
       EMPLOYEE.JOB,
       MANAGER.ENAME AS MANAGER_NAME,
       SALGRADE.GRADE
FROM EMPLOYEE
JOIN DEPARTMENT
ON EMPLOYEE.DEPTNO = DEPARTMENT.DEPTNO
LEFT JOIN EMPLOYEE MANAGER
ON EMPLOYEE.MGR = MANAGER.EMPNO
JOIN SALGRADE
ON EMPLOYEE.SAL BETWEEN SALGRADE.LOSAL AND SALGRADE.HISAL
ORDER BY DEPARTMENT.DNAME;
```

### Question 4
List out all the employees name, job, and salary grade and department name for everyone in the company except 'clerk'. Sort on salary display the highest salary.
### Query
```sql
SELECT EMPLOYEE.ENAME,
       EMPLOYEE.JOB,
       SALGRADE.GRADE,
       DEPARTMENT.DNAME,
       EMPLOYEE.SAL
FROM EMPLOYEE
JOIN DEPARTMENT
ON EMPLOYEE.DEPTNO = DEPARTMENT.DEPTNO
JOIN SALGRADE
ON EMPLOYEE.SAL BETWEEN SALGRADE.LOSAL AND SALGRADE.HISAL
WHERE EMPLOYEE.JOB <> 'CLERK'
ORDER BY EMPLOYEE.SAL DESC;
```

### Question 5
Display employee name, his job and his manager. Display also employees who are without manager.
### Query
```sql
SELECT EMPLOYEE.ENAME,
       EMPLOYEE.JOB,
       NVL(MANAGER.ENAME,'NO MANAGER') AS MANAGER_NAME
FROM EMPLOYEE
LEFT JOIN EMPLOYEE MANAGER
ON EMPLOYEE.MGR = MANAGER.EMPNO;
```

### Question 6
List the employee name, job, annual salary, deptno, dept name and grade who earn 36000 a year or who are not clerks.
### Query
```sql
SELECT EMPLOYEE.ENAME,
       EMPLOYEE.JOB,
       (EMPLOYEE.SAL * 12) AS ANNUAL_SALARY,
       EMPLOYEE.DEPTNO,
       DEPARTMENT.DNAME,
       SALGRADE.GRADE
FROM EMPLOYEE
JOIN DEPARTMENT
ON EMPLOYEE.DEPTNO = DEPARTMENT.DEPTNO
JOIN SALGRADE
ON EMPLOYEE.SAL BETWEEN SALGRADE.LOSAL AND SALGRADE.HISAL
WHERE (EMPLOYEE.SAL * 12 = 36000)
OR EMPLOYEE.JOB <> 'CLERK';
```

### Question 7
List ename, job, annual sal, deptno, dname and grade who earn 30000 per year and who are not clerks.
### Query
```sql
SELECT EMPLOYEE.ENAME,
       EMPLOYEE.JOB,
       (EMPLOYEE.SAL * 12) AS ANNUAL_SALARY,
       EMPLOYEE.DEPTNO,
       DEPARTMENT.DNAME,
       SALGRADE.GRADE
FROM EMPLOYEE
JOIN DEPARTMENT
ON EMPLOYEE.DEPTNO = DEPARTMENT.DEPTNO
JOIN SALGRADE
ON EMPLOYEE.SAL BETWEEN SALGRADE.LOSAL AND SALGRADE.HISAL
WHERE (EMPLOYEE.SAL * 12 = 30000)
AND EMPLOYEE.JOB <> 'CLERK';
```

### Question 8
List out all employees by name and number along with their manager’s name and number also display 'no manager' who has no manager.
### Query
```sql
SELECT EMPLOYEE.EMPNO,
       EMPLOYEE.ENAME,
       NVL(MANAGER.EMPNO,0) AS MANAGER_NUMBER,
       NVL(MANAGER.ENAME,'NO MANAGER') AS MANAGER_NAME
FROM EMPLOYEE
LEFT JOIN EMPLOYEE MANAGER
ON EMPLOYEE.MGR = MANAGER.EMPNO;
```

### Question 9
Select dept name, dept no and sum of sal.
### Query
```sql
SELECT DEPARTMENT.DNAME,
       DEPARTMENT.DEPTNO,
       SUM(EMPLOYEE.SAL) AS TOTAL_SALARY
FROM EMPLOYEE
JOIN DEPARTMENT
ON EMPLOYEE.DEPTNO = DEPARTMENT.DEPTNO
GROUP BY DEPARTMENT.DNAME, DEPARTMENT.DEPTNO;
```

### Question 10
Display employee number, name and location of the department in which he is working.
### Query
```sql
SELECT EMPLOYEE.EMPNO,
       EMPLOYEE.ENAME,
       DEPARTMENT.LOC
FROM EMPLOYEE
JOIN DEPARTMENT
ON EMPLOYEE.DEPTNO = DEPARTMENT.DEPTNO;
```

### Question 11
Display employee name and department name for each employee.
### Query
```sql
SELECT EMPLOYEE.ENAME,
       DEPARTMENT.DNAME
FROM EMPLOYEE
JOIN DEPARTMENT
ON EMPLOYEE.DEPTNO = DEPARTMENT.DEPTNO;
```


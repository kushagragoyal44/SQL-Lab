# SQL Lab – Experiment 6
## Aim
To implement SQL functions related to date, time, conversion, and formatting.

### Question 1
Display empno, ename, deptno from employee table. Instead of display department numbers display the related department name (Use decode function).
### Query
```sql
SELECT EMPNO,
       ENAME,
       DECODE(DEPTNO,
              10, 'RESEARCH',
              20, 'ACCOUNTING',
              30, 'SALES',
              40, 'OPERATIONS') AS DEPARTMENT
FROM EMPLOYEE;
```

### Question 2
Display your age in days.
### Query
```sql
SELECT (SYSDATE - TO_DATE('01-JAN-2005','DD-MON-YYYY')) AS AGE_IN_DAYS
FROM DUAL;
```

### Question 3
Display your age in months.
### Query
```sql
SELECT MONTHS_BETWEEN(SYSDATE, TO_DATE('01-JAN-2005','DD-MON-YYYY')) AS AGE_IN_MONTHS
FROM DUAL;
```

### Question 4
Display the current date as 15th August Friday Nineteen Ninety-Seven.
### Query
```sql
SELECT TO_CHAR(TO_DATE('15-AUG-1997','DD-MON-YYYY'),
       'DDth Month Day YYYY') AS FORMATTED_DATE
FROM DUAL;
```

### Question 5
Find the date for nearest Saturday after current date.
### Query
```sql
SELECT NEXT_DAY(SYSDATE, 'SATURDAY') AS NEXT_SATURDAY
FROM DUAL;
```

### Question 6
Display current time.
### Query
```sql
SELECT TO_CHAR(SYSDATE, 'HH:MI:SS AM') AS CURRENT_TIME
FROM DUAL;
```

### Question 7
Display the date three months Before the current date.
### Query
```sql
SELECT ADD_MONTHS(SYSDATE, -3) AS DATE_BEFORE_3_MONTHS
FROM DUAL;
```

### Question 8
Display those employees who joined in the company in the month of Dec.
### Query
```sql
SELECT *
FROM EMPLOYEE
WHERE TO_CHAR(HIREDATE, 'MON') = 'DEC';
```

### Question 9
Display those employees whose first 2 characters from hire date - last 2 characters of salary.
### Query
```sql
SELECT ENAME,
       SUBSTR(TO_CHAR(HIREDATE,'DDMMYYYY'),1,2) ||
       SUBSTR(TO_CHAR(SAL),-2) AS RESULT
FROM EMPLOYEE;
```

### Question 10
Display those employees whose 10% of salary is equal to year of joining.
### Query
```sql
SELECT *
FROM EMPLOYEE
WHERE (SAL * 0.10) = TO_NUMBER(TO_CHAR(HIREDATE,'YYYY'));
```

### Question 11
Display those employees who joined the company before 15 of the month.
### Query
```sql
SELECT *
FROM EMPLOYEE
WHERE TO_NUMBER(TO_CHAR(HIREDATE,'DD')) < 15;
```

### Question 12
Display those employees whose joining DATE is available in deptno.
### Query
```sql
SELECT *
FROM EMPLOYEE
WHERE TO_NUMBER(TO_CHAR(HIREDATE,'DD')) = DEPTNO;
```
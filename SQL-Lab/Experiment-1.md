# SQL Lab – Experiment 1
## Aim
To create tables with given constraints and perform basic DDL operations like create, alter, update, and drop.

## Question 1
Create Employee_master table with data using Employee table.
### Query
```sql
CREATE TABLE Employee_master AS
SELECT * 
FROM Employee;
```
## Question 2
Delete all record into Employee_master whose DeptNo is 10.
### Query
```sql
DELETE FROM Employee_master
WHERE DeptNo = 10;
```
## Question 3
Update 10% in his salary of DEPTNO 20 into Employee_Master.
### Query
```sql
UPDATE Employee_master
SET SAL = SAL + (SAL * 0.10)
WHERE DeptNo = 20;
```
## Question 4
Alter SAL with size 10,2 in Employee_Master.
### Query
```sql
ALTER TABLE Employee_Master
MODIFY SAL NUMBER(10,2);
```
## Question 5
Drop Employee_master Table.
### Query
``sql
DROP TABLE Employee_master;
```
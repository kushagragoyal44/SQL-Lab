# SQL BOLT – EXP 2
## Aim 1
Find the movie with a row id of 6 ✓
### Query
```sql
SELECT Title FROM movies Where id = 6 ;
```
## Aim 2
Find the movies released in the years between 2000 and 2010
## Query
```sql
Find the movies released in the years between 2000 and 2010
```

## Aim 3
Find the movies not released in the years between 2000 and 2010 ✓
## Query
```sql
SELECT Title FROM movies Where Year NOT BETWEEN  2000 AND 2010 ;
```

## Aim 4
Find the first 5 Pixar movies and their release year
## Query 
```sql
Select * From Movies Where id <= 5
```


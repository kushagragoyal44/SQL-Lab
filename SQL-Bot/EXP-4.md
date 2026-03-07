# SQL BOLT – EXP 4
## Aim 1
List all directors of Pixar movies (alphabetically), without duplicates ✓
### Query
```sql
SELECT DISTINCT director FROM movies
ORDER BY director ASC;
```

## Aim 2
List the last four Pixar movies released (ordered from most recent to least)
## Query
```sql
SELECT title, year FROM movies
ORDER BY year DESC
LIMIT 4;
```

## Aim 3
List the first five Pixar movies sorted alphabetically
## Query
```sql
SELECT title FROM movies
ORDER BY title ASC
LIMIT 5;
```

## Aim 4
List the next five Pixar movies sorted alphabetically
## Query 
```sql
SELECT title FROM movies
ORDER BY title ASC
LIMIT 5 OFFSET 5;
```


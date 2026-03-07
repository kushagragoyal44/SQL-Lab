# SQL BOLT – EXP 3
## Aim 1
Find all the Toy Story movies ✓
### Query
```sql
SELECT title, director FROM movies 
WHERE title LIKE "Toy Story%";
```

## Aim 2
Find all the movies directed by John Lasseter ✓
## Query
```sql
SELECT title, director FROM movies 
WHERE director = "John Lasseter";
```

## Aim 3
Find all the movies (and director) not directed by John Lasseter
## Query
```sql
SELECT title, director FROM movies 
WHERE director != "John Lasseter";
```

## Aim 4
Find all the WALL-* movies
## Query 
```sql
SELECT * FROM movies 
WHERE title LIKE "WALL-_";
```


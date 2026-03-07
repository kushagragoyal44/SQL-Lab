# SQL BOLT – EXP 5
## Aim 1
List all the Canadian cities and their populations
### Query
```sql
SELECT city, population FROM north_american_cities
WHERE country = "Canada";
```

## Aim 2
Order all the cities in the United States by their latitude from north to south
## Query
```sql
SELECT city, latitude FROM north_american_cities
WHERE country = "United States"
ORDER BY latitude DESC;
```

## Aim 3
List all the cities west of Chicago, ordered from west to east
## Query
```sql
SELECT city, longitude FROM north_american_cities
WHERE longitude < -87.629798
ORDER BY longitude ASC;
```

## Aim 4
List the two largest cities in Mexico (by population) ✓
## Query 
```sql
SELECT city, population FROM north_american_cities
WHERE country LIKE "Mexico"
ORDER BY population DESC
LIMIT 2;
```
## Aim 5
List the third and fourth largest cities (by population) in the United States and their population
## Query 
```sql
SELECT city, population FROM north_american_cities
WHERE country LIKE "United States"
ORDER BY population DESC
LIMIT 2 OFFSET 2;
```

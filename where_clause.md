
# SQL Cheat Sheet

- [Populating and Modifying Tables](README.md#populating-and-modifying-tables)
- [WHERE](where_clause.md)
- [Querying Multiple Tables](multiple_tables.md)
- [Using SETS (UNION, INTERSECT)](sets.md)
- [Temporary tables and Views](temporary_tables.md)
- [Data Generation, Manipulation,and Conversion](data_manipulation.md)



## Where Clause

```sql
SELECT * FROM users WHERE location='Massachusetts';
SELECT * FROM users WHERE location='Massachusetts' AND dept='sales';
SELECT * FROM users WHERE is_admin = 1;
SELECT * FROM users WHERE is_admin > 0;
SELECT * FROM film WHERE (rating = 'G' AND rental_duration >= 7) OR (rating = 'PG-13' AND rental_duration < 4);
SELECT * FROM rental WHERE rental_date BETWEEN '2005-06-14' AND '2005-06-16';
```
### Using subqueries
```sql
SELECT * FROM film WHERE rating IN (SELECT rating FROM film WHERE title LIKE '%PET%');
```

### Matching Conditions
```sql
SELECT * FROM customer WHERE left(last_name, 1) = 'Q';
SELECT * FROM customer WHERE last_name LIKE '_A_T%S';

// regular expressions

SELECT * FROM customerWHERE last_name REGEXP '^[QY]';
```

<br /><br />

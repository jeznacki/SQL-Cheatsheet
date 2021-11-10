
# SQL Cheat Sheet

- [Populating and Modifying Tables](README.md#populating-and-modifying-tables)
- [WHERE](where_clause.md)
- [Querying Multiple Tables](multiple_tables.md)
- [Using SETS (UNION, INTERSECT)](sets.md)
- [Temporary tables and Views](temporary_tables.md)
- [Data Generation, Manipulation,and Conversion](data_manipulation.md)


## SETS
when performing set operations on two data sets, the following guidelines must apply:

• Both data sets must have the same number of columns.
• The data types of each column across the two data sets must be the same (or the server must be able to convert one to the other).

### UNION & UNION ALL
union sorts the combined set and removes duplicates, whereas union all does not.

![See Image](myimage.png)

```sql
SELECT 'CUST' typ, c.first_name, c.last_name
 FROM customer c
 UNION ALL
 SELECT 'ACTR' typ, a.first_name, a.last_name
 FROM actor a;
```

### Intersect Operator

If the two queries in a compound query return nonoverlapping data sets, then the
intersection will be an empty set.

![See Image](intercest.png)

```sql
SELECT c.first_name, c.last_name
FROM customer c
WHERE c.first_name LIKE 'D%' AND c.last_name LIKE 'T%'
INTERSECT
SELECT a.first_name, a.last_name
FROM actor a
WHERE a.first_name LIKE 'D%' AND a.last_name LIKE 'T%';
```

### The except Operator

![See Image](except.png)

```sql
SELECT a.first_name, a.last_name
FROM actor a
WHERE a.first_name LIKE 'J%' AND a.last_name LIKE 'D%'
EXCEPT
SELECT c.first_name, c.last_name
FROM customer c
WHERE c.first_name LIKE 'J%' AND c.last_name LIKE 'D%';
```

<br /><br />

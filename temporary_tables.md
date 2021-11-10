
# SQL Cheat Sheet

- [Populating and Modifying Tables](README.md#populating-and-modifying-tables)
- [WHERE](where_clause.md)
- [Querying Multiple Tables](multiple_tables.md)
- [Using SETS (UNION, INTERSECT)](sets.md)
- [Temporary tables and Views](temporary_tables.md)
- [Data Generation, Manipulation,and Conversion](data_manipulation.md)


## Temporary tables and Views

### Temporary tables
These tables look just like permanent tables, but any data inserted into a temporary table will disappear at some point (generally at the
end of a transaction or when your database session is closed).

```sql

CREATE TEMPORARY TABLE actors_j (actor_id smallint(5), first_name varchar(45), last_name varchar(45));

INSERT INTO actors_j
-> SELECT actor_id, first_name, last_name
-> FROM actor
-> WHERE last_name LIKE 'J%';

```
These rows are held in memory temporarily and will disappear after your ses‐sion is closed.

### Views
A view is a query that is stored in the data dictionary. It looks and acts like a table, but
there is no data associated with a view (this is why I call it a virtual table).

```sql
CREATE VIEW cust_vw AS SELECT customer_id, first_name, last_name, active FROM customer;
```

When the view is created, no additional data is generated or stored: the server simply
tucks away the select statement for future use. Now that the view exists, you can
issue queries against it, as in:

```sql
SELECT first_name, last_name FROM cust_vw WHERE active = 0;
```
<br/><br/>

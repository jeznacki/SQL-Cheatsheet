# SQL Cheat Sheet

- [Populating and Modifying Tables](README.md#populating-and-modifying-tables)
- [WHERE](where_clause.md)
- [Querying Multiple Tables](multiple_tables.md)
- [Using SETS (UNION, INTERSECT)](sets.md)
- [Temporary tables and Views](temporary_tables.md)
- [Data Generation, Manipulation,and Conversion](data_manipulation.md)

## Populating and Modifying Tables


### Create Table

```sql
CREATE TABLE users(
id INT AUTO_INCREMENT,
   first_name VARCHAR(100),
   last_name VARCHAR(100),
   email VARCHAR(50),
   password VARCHAR(20),
   location VARCHAR(100),
   dept VARCHAR(100),
   is_admin TINYINT(1),
   register_date DATETIME,
   PRIMARY KEY(id)
);

//delete table

DROP TABLE tablename;
```

### Insert Row

```sql
INSERT INTO users (first_name, last_name, email, password, location, dept, is_admin, register_date) values ('Brad', 'Traversy', 'brad@gmail.com', '123456','Massachusetts', 'development', 1, now());

INSERT INTO users (first_name, last_name, email, password, location, dept,  is_admin, register_date) values ('Fred', 'Smith', 'fred@gmail.com', '123456', 'New York', 'design', 0, now()), ('Sara', 'Watson', 'sara@gmail.com', '123456', 'New York', 'design', 0, now()),('Will', 'Jackson', 'will@yahoo.com', '123456', 'Rhode Island', 'development', 1, now()),('Paula', 'Johnson', 'paula@yahoo.com', '123456', 'Massachusetts', 'sales', 0, now()),('Tom', 'Spears', 'tom@yahoo.com', '123456', 'Massachusetts', 'sales', 0, now());
```

### Update and Delete data
```sql

UPDATE person SET street = '1225 Tremont St.',city = 'Boston', state = 'MA', country = 'USA', postal_code = '02138' WHERE person_id = 1;

DELETE FROM person WHERE person_id = 2;
```






## Column Aliases
```sql

SELECT language_id, 'COMMON' language_usage, language_id * 3.1415927 lang_pi_value, upper(name) language_name FROM language;

//clearer
SELECT language_id,'COMMON' AS language_usage, language_id * 3.1415927 AS lang_pi_value, upper(name) AS language_name FROM language;

SELECT c.first_name, c.last_name FROM customer AS c 
INNER JOIN rental AS r
ON c.customer_id = r.customer_id
WHERE date(r.rental_date) = '2005-06-14';

```

## Removing Duplicates
DISTINCT

```sql
SELECT DISTINCT actor_id FROM film_actor ORDER BY actor_id;
```

## The from Clause

```sql
DELETE FROM users WHERE id = 6;
```

## Derived (subquery-generated) tables

```sql
SELECT concat(cust.last_name, ', ', cust.first_name) full_name 
-> FROM (SELECT first_name, last_name, email FROM customer WHERE first_name = 'JESSIE' ) cust;

+---------------+
| full_name |
+---------------+
| BANKS, JESSIE |
| MILAM, JESSIE |
+---------------+
```











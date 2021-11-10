# SQL Cheat Sheet

- [Populating and Modifying Tables](README.md#populating-and-modifying-tables)
- [WHERE](where_clause.md)
- [Querying Multiple Tables](multiple_tables.md)
- [Using SETS (UNION, INTERSECT)](sets.md)
- [Temporary tables and Views](temporary_tables.md)
- [Data Generation, Manipulation,and Conversion](data_manipulation.md)

## Data Generation, Manipulation, and Conversion

### Strings

#### Length
```sql
SELECT LENGTH(char_fld) char_length, LENGTH(vchar_fld) varchar_length, LENGTH(text_fld) text_length FROM string_tbl;
```
| char_length | varchar_length | text_length |
|-------------|----------------|-------------|
| 28 | 28 | 28 |

#### Position
```sql
SELECT POSITION('characters' IN vchar_fld) FROM string_tbl;
```
| POSITION('characters' IN vchar_fld) |
|-------------------------------------|
| 19 |

#### Instert / Replace

```sql
SELECT INSERT('goodbye world', 9, 0, 'cruel ') string;
```
| string |
|---------------------|
| goodbye cruel world |

### Numeric

//PAGE 131

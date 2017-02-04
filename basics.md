# SQL Basics
## Table
### Create Table
```sqlite
CREATE TABLE cats (
id INTEGER PRIMARY KEY,
     name TEXT, 
     age INTEGER
     );
```

### Alter Table
```sqlite
ALTER TABLE cats ADD COLUMN breed TEXT;
```

### Delete Table
```sqlite
DROP TABLE cats;
```

### Run SQL File
```bash
sqlite3 pets_database.db < 01_create_cats_table.sql
```

## Data Types

- TEXT
    - LENGTH(TEXT)

- INTEGER
- REAL
- BLOB

## Row

### Insert
```sqlite
INSERT INTO cats (name, age, breed)
VALUES ('Maru', 3, NULL);
```

### Select
#### Basics
```sqlite
SELECT [DISTINGCT] [names of columns we are going to select]
FROM [table we are selecting from]
WHERE [column name] = [some value]
-- or WHERE column_name BETWEEN value1 AND value2
-- or WHERE column_name IS NULL
ORDER BY column_name ASC|DESC -- ASC is default
LIMIT number_to_display;
```
#### Aggregate Functions
```sqlite
-- count the number of records that meet certain condition.
SELECT COUNT([column name])
FROM [table name]
WHERE [column name] = [value]
GROUP BY [column name(s)];
-- AVG(), SUM(), MIN(), MAX()
SELECT AVG(column_name) [AS the_other_colum_name] FROM table_name;

```

### Update
```sqlite
UPDATE [table name] SET [column name] = [new value]
WHERE [column name] = [value];
```

### Delete
```sqlite
DELETE FROM [table name]
WHERE [column name] = [value];
```

## Joins

```sqlite
SELECT column_name(s)
FROM first_table
[Methond] JOIN second_table
ON first_table.column_name=second_table.column_name;
```
Type|Description
:---:|---
INNER JOIN|Returns all rows when there is at least one match in BOTH tables
LEFT JOIN|Returns all rows from the left table, and the matched rows from the right table
RIGHT JOIN|Returns all rows from the right table, and the matched rows from the left table
FULL JOIN|Returns all rows when there is a match in ONE of the tables


## Display Settings
```sqlite
.header on       # output the name of each column
.mode column     # now we are in column mode, enabling us to run the next two .width commands
.width auto      # adjusts and normalizes column width
# or
.width NUM1, NUM2 # customize column width
```

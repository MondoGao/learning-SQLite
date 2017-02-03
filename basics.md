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
- INTEGER
- REAL
- BLOB

## Row

### Insert
```sqlite
INSERT INTO cats (name, age, breed) VALUES ('Maru', 3, 'Scottish Fold');
```
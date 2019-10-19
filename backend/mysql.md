# MySQL Cheatsheet

credit : https://devhints.io/mysql

### Backup Database
```
mysqldump -u Username -p dbNameYouWant > databasename_backup.sql
```

### Restore from backup SQL File
```
mysql - u Username -p dbNameYouWant < databasename_backup.sql
```

### Browsing
```
SHOW DATABASES
SHOW TABLES
SHOW FIELDS FROM table / DESCRIBE table
SHOW CREATE TABLE table
SHOW PROCESSLIST
KILL process_number
```

### Select
```
SELECT * FROM table
SELECT * FROM table1, table2, ...
SELECT field1, field2, ... FROM table1, table2, ...
SELECT ... FROM ... WHERE condition
SELECT ... FROM ... WHERE condition GROUPBY field
SELECT ... FROM ... WHERE condition GROUPBY field HAVING condition2
SELECT ... FROM ... WHERE condition ORDER BY field1, field2
SELECT ... FROM ... WHERE condition ORDER BY field1, field2 DESC
SELECT ... FROM ... WHERE condition LIMIT 10
SELECT DISTINCT field1 FROM ...
SELECT DISTINCT field1, field2 FROM ...
```

### Insert
```
INSERT INTO table1 (field1, field2, ...) VALUES (value1, value2, ...)
```

### Delete
```
DELETE FROM table1 / TRUNCATE table1
DELETE FROM table1 WHERE condition
DELETE FROM table1, table2 FROM table1, table2 WHERE table1.id1 =
  table2.id2 AND condition
```

### Conditions
```
field1 = value1
field1 <> value1
field1 LIKE 'value _ %'
field1 IS NULL
field1 IS NOT NULL
field1 IS IN (value1, value2)
field1 IS NOT IN (value1, value2)
condition1 AND condition2
condition1 OR condition2
```

### Update
```
UPDATE table1 SET field1=new_value1 WHERE condition
UPDATE table1, table2 SET field1=new_value1, field2=new_value2, ... WHERE
  table1.id1 = table2.id2 AND condition
```

### Main Data Types
```
TINYINT (1o: -217+128)
SMALLINT (2o: +-65 000)
MEDIUMINT (3o: +-16 000 000)
INT (4o: +- 2 000 000 000)
BIGINT (8o: +-9.10^18)
Precise interval: -(2^(8*N-1)) -> (2^8*N)-1
FLOAT(M,D)
DOUBLE(M,D)
FLOAT(D=0->53)
TIME (HH:MM)
YEAR (AAAA)
DATE (AAAA-MM-JJ)
DATETIME (AAAA-MM-JJ HH:MM; années 1000->9999)
TIMESTAMP (like DATETIME, but 1970->2038, compatible with Unix)
VARCHAR (single-line; explicit size)
TEXT (multi-lines; max size=65535)
BLOB (binary; max size=65535)
```

### Reset Root Password
```
$ /etc/init.d/mysql stop
$ mysqld_safe --skip-grant-tables
$ mysql # on another terminal
mysql> UPDATE mysql.user SET password=PASSWORD('new_pass') WHERE user='root';
```

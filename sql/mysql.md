start the cli
```sql
mysql-ctl cli;
```
## database
### list available databases
```sql
SHOW DATABASES;
```
### create a new database
```sql
CREATE DATABASE <name>;
```
### delete a database
```sql
DROP DATABASE <name>;
```
### switch to a specific database you want to work with
```sql
USE <database name>;
```
### show currently used database
```sql
SELECT database();
```
## table
### create a table
```sql
CREATE TABLE <tablename>
  (
    <column_name> datatype NOT NULL AUTO_INCREMENT,
    <column_name> datatype NOT NULL DEFAULT <default value>,
    PRIMARY KEY (column_name)
  );
```

### show tables
```sql
SHOW TABLES;
```
### show columns of a table
```sql
SHOW COLUMNS FROM <tablename>;
```
also   
```sql
DESC <tablename>;
```
### delete a table
```sql
DROP TABLE <tablename>;
```
## insert
### single insert
```sql
INSERT INTO <tablename>(<column1>, <cloumn2>)
VALUES (<value1>, <value2>);
```
### multiple insert
```sql
INSERT INTO <tablename>(columns)
VALUES (data1), (data2), (data3);
```
## show warnings
```sql
SHOW WARNINGS;
```
## read
## update
```sql
UPDATE <table_name> SET <column_name> = <new_value> WHERE <condition>;
```
## delete
```sql
DELETE FROM <table_name> WHERE <condition>;
```
following code will delete the whole table
```sql
DELETE FROM <table_name>;
```
## run sql files
```sql
SOURCE file_name.sql;
```
## concat
```sql
SELECT CONCAT(x,y,z) FROM <table_name>;
```
concat with separator
```sql
SELECT CONCAT_WS('<separator>', x, y, z) FROM <table_name>;
```
## substring
```sql
SELECT SUBSTRING(<string>/<column_name>, from_index, to_index) FROM <table_name>;
```
## replace
```sql
SELECT REPLACE(<string>/<column_name>, <text_to_be_replaced>, <substitute_text>) FROM <table_name>;
```
## reverse
```sql
SELECT REVERSE(<object>) from <table_name>;
```
## char length
```sql
CHAR_LENGTH()
```
## case of string
```sql
UPPER()
```
```sql
LOWER()
```
## distinct
```sql
SELECT DISTINCT <column_name> FROM <table_name>;
```
## sorting
```sql
SELECT <column_name> FROM <table_name> ORDER BY <column_name> DESC LIMIT 0,5;
```
## wildcards
```sql
SELECT <column_name> FROM <table_name> WHERE <column_name> LIKE '%haha%'
```

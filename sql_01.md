# Basics
## SQL is declarative
Unlike many other languages such as C, Java, Python, Visual Basic, etc. that are procedural in nature, SQL is a declarative language.   It is a non-procedural language.   
In a declarative language such as SQL, you write a single SQL declaration and hand it
to the DBMS.  The DBMS then interpret the code and figures out a way to execute it.  This is hidden from you.  The DBMS engine returns a set of data rows, which is a group of data that is dynamically selected to meet your request.
## Connecting to a db
The front end provides a means to construct the SQL statement, send those statements to the server-side program, and collect the returned data.  The front end can be a full featured client program, that helps you build the SQL commands, or can be a simple web page form that is executed in a browser.   
The connection provides a conduit to send the SQL statement to the back end and then to return results to the front end.  The connection could be across the internet, or within the same computer.   
The back end is a DBMS that accepts and acts on the SQL statements received.  Usually the back end has two parts, the database engine (or database server program) which executes the SQL commands, and the data store where the data physically resides.
## DDL - Data Definition Language
to define, create, and delete db and db objects   
primarily used by DBA   
example
```sql
CREATE DATABASE db_name, CREATE TABLE table_name, GRANT …,  
	ALTER table_name, DROP name, etc.
```
## DML - Data Manipulation Language   
to insert, modify and retrieve data from the db   
used by all db users   
example
```sql
INSERT INTO table, UPDATE table, DELETE FROM table, SELECT something FROM table
```
# Basic commands
## list all tables
MySql
```sql
SHOW TABLES
```
Oracle
```sql
SELECT table_name FROM user_tables
```
## list all columns within a table
```sql
DESC  your_table_name
```
## list all rows within a table
```sql
SELECT * FROM your_table_name
```
## list all keys/indexes, and table relationships
MySql
```sql
SELECT
    table_name,
    column_name,
    constraint_name,
    ordinal_position,
    referenced_table_name,
    referenced_column_name
FROM
    information_schema.key_column_usage
```
# SELECT
## syntax
```sql
SELECT [DISTINCT] [<qualifier>.]<column_name> | * | <expression>[ [AS] <column_alias>], …
FROM  <table_or_view_name> | <inline_view> [ [AS] <table_alias>]
[WHERE  <predicate>]
[GROUP BY  [<qualifier>.]<column_name>, …
	[HAVING <predicate>]
]
[ORDER BY <column_name> | <column_number> [ASC | DESC], … ];

```
## examples
```sql
SELECT lname, fname, sex FROM student;
```
the order of the columns retrieved is the same order as within the SELECT statement
```sql
SELECT  DISTINCT  state  FROM  address;
```
query all the unique values   
note: a null will be retuned as one of the distinct values.   
the null will not be counted if using a COUNT( )
```sql
SELECT COUNT(DISTINCT state) FROM address;
```
to retrieve the distinct values for a combination of two or more columns
```sql
SELECT DISTINCT state, city  FROM  address;
```
# WHERE
to retrieve the student whose student id is 9
```sql
SELECT * FROM student WHERE student_id = 9;
```
to retrieve all students with the first name of David
```sql
SELECT * FROM student
WHERE fname = 'David';
```
```sql
SELECT * FROM student
WHERE LOWER(fname) = 'david'
```
```sql
SELECT * FROM student
WHERE UPPER(fname)  = 'DAVID'
```
# comparison operators
SQL uses the following comparison operators:
```
=					        equal
<					        less than
>					        greater than
<=					        less than or equal
>=					        greater than or equal
<>  (or)  !=				not equal

[NOT] BETWEEN x AND y	  	inclusively
[NOT] IN (items, subquery)
IS [NOT] NULL			
[NOT] LIKE 'x'  [ESCAPE 'c']
[NOT] EXISTS (subquery)		exists [or not exist] in the correlated subquery
```
# LIKE
## wildcard
_ 	- the underscore character matches any 1 single character   
% 	- the percent sign matches any 0 or more characters   
```sql
SELECT * FROM student
WHERE lname LIKE 'M%';
```
```sql
SELECT * FROM student
WHERE UPPER(lname) LIKE 'M%';
```
```sql
SELECT * FROM student
WHERE lname LIKE '%m%';
```
```sql
SELECT * FROM  student
WHERE lname LIKE 'M_';
```
```sql
SELECT * FROM student
WHERE lname LIKE '__m%';
```
# derived columns
multiply
```sql
SELECT course_id, description, price,  price*1.05
FROM course;
```
concat in MySql
```sql
SELECT student_id, concat(fname, ' ', lname), sex
FROM student;
```
concat in Oracle
```sql
SELECT student_id, fname || ' ' || lname,  sex
FROM student;
```
another concat
```sql
SELECT student_id, 'hello', concat('Mr.', lname), 'male', 4*5
FROM student								
WHERE sex = 'M';
```
the name of the derived column is the expression that created the column
# Alias
```sql
SELECT student_id, student_id +1000 AS New_id, fname, lname, 'hello' AS Greeting
FROM student;
```
In most DBMS, the AS keyword is optional   
If the alias name is a multi-word, should enclose the alias in "double" quotes
```sql
SELECT student_id, student_id + 1000 New_Id, fname AS First, lname "Last Name"
FROM student;
```
# some DBA statements
## creat a user
MySql
```sql
CREATE DATABASE database_name
CREATE USER user_name identified by 'password_value'
```
Oracle
```sql
CREATE USER user_name identified by password_value
```
## grant privileges to some users
MySql
```sql
GRANT ALL ON database_name.* TO user_name
GRANT FILE ON *.* to user_name  
```
Oracle
```sql
GRANT CONNECT TO user_name  		      -- allow user to connect to the DB
GRANT RESOURCE TO user_name  		      -- allow insert, create, etc.
GRANT SELECT ANY DICTIONARY TO user_name  -- allow access to DB dictionary
GRANT CREATE VIEW TO user_name  		      -- allow the creation of views
GRANT CREATE MATERIALIZED VIEW TO user_name  -- and materialized views
GRANT CREATE PROCEDURE TO user_name  	      -- allow creation of stored proc
```

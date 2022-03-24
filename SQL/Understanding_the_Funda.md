# Understand the fundamentals:
RDBMS stands for Relational Database Management System. 
RDBMS is the basis for SQL, and for all modern database systems such as MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access.

The data in RDBMS is stored in database objects called tables. A table is a collection of related data entries and it consists of columns and rows.

 ## Points to be Conssidered
- SQL keywords are NOT case sensitive: `select` is the same as `SELECT`
- Some database systems require a semicolon at the end of each SQL statement.
Semicolon is the standard way to separate each SQL statement in database systems that allow more than one SQL statement to be executed in the same call to the server.

## Some popular Data types: 
 VARCHAR, INT, DATE, FLOAT, BOOLEAN
 
## Constraints: 
PRIMARY KEY, FOREIGN KEY, UNIQUE, CHECK and NOT NULL

## Commands
 - DDL commands : CREATE, ALTER, DROP, TRUNCATE
 - DML commands : INSERT, UPDATE, DELETE, MERGE
 - TCL commands : COMMIT, ROLLBACK, SAVEPOINT
 - DCL commands : GRANT and REVOKE
 - DQL commands : SELECT, FROM and WHERE clause is used for, also DISTINCT and LIMIT (or TOP) with GROUP BY and HAVING clause

## Few Usefull Links :
--- 
- For SQL Keywords : https://www.w3schools.com/sql/sql_ref_keywords.asp
- For MySQL Functions : MySQL has many built-in functions: https://www.w3schools.com/sql/sql_ref_mysql.asp
---

## Useful Notes:
Few useful important points to remember

---
|**Code** | **Note**|
|:--------|:--------|
|`NULL`   | missing value|
|`IS NULL` , `IS NOT NULL`| don't use `= NULL`|
|`count(*)`| total no of rows|
|`count(column_name)`   | number of non-NULL Rows|
|`count(DISTINCT column_name)` | number of unique non-NULL values|
|`SELECT DISTINCT column_name ...` | distinct values, including NULL|

---

- Foreign Key is a necessary to be unique value (in the another table) and can be `NULL`. also In ER(Enity Relationship Diagram)  with Arrow pointer as **Primary Key column_name : Ref Key column_name(Foreign Key)**

- **Coalesce Function** :
It operates **row by row**, it returns values of first non-`NULL` value is there is any non-`NULL` value.
e.g `SELECT coalesce(column_name1,column_name2) FROM table_name`
    - `coalesce(NULL, 1, 2)` = 1
    - `coalesce(NULL, NULL)` = NULL
    - `coalesce(2, 3, NULL)` = 2

- **Column Constrains:**
There are few important Column constraints.
    - Foreign Key : Values that are referenced from different table.
    - Primary Key : Unique, not `NULL`.
    - `UNIQUE` constraint implies all values must be different.
    - Conditions like `columnA > columnB` or `column1 > 0 `.
    - Each column can contain only 1 data type, common are `Numeric, Character, DateTime, Boolean`.
    - `CAST()` the data type can be converted to required data type e.g `SELECT CAST(cloumn_name or value **AS** data_Type)`
    or `SELECT column_name or value ::data_type`




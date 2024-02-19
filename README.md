This is a SQL tutorial which is based on Sumit Sir youtube playlist. I think this will be very helpful who wants to learn SQL genuinely and effective way.

## Getting started with SQL - Session 1
### What is database?
- a collection of data and holds this data in the form of tables.
### what is table?
- holds the data in form of rows and columns.

The database provides us the capability to access and manipulate this data.

There are two types of database. These are:
1. Relational Database
2. NoSQL Database

### Relational Database
----------------------
- consists of rows & columns
- have relations between tables
- examples are MySQL, SQL Server, PostgreSQL, SQLite, MariaDB, etc.

### NoSQL Database
----------------------
- consists of key, value pair or document basis or graph basis or etc.
- no relation between tables.
- examples are Hbase, MongoDB, Cassandra, etc.
- each database has own language to interact with NoSQL database.

### What is SQL?
- stands for Structured Query Language and is used to query a relational database.
- deals with Structured data which is formed with the combination of rows & columns.
- a way to interact with the databases such as MySQL, SQL Server, PostgreSQL, SQLite, MariaDB, etc.

### SQL vs Different Databases (MySQL, SQL Server, PostgreSQL, SQLite, MariaDB, etc.)
- By SQL you can interact, modified, update with different databases.
- Different databases provide different features & security. If you know SQL you will be able to interact or communicate with all kinds of relational databases.

Practice SQL query with MySQL Database:

`SHOW DATABASES;`
- this command gives you list of databases which are already present.
![show databases](images/session1/show_databases.png))

`CREATE DATABASE trendytech;`
- by this command you can create a new database, here database name `trendytech`.

`DROP DATABASE trendytech`
- by this command you can delete specific database, here I deleted `trendytech` database.

`USE trendytech;`
- by this command you will connect with certain database, here I used `trendytech` database.

`SELECT DATABASE();`
- by this command you will know in which database you are connected.

```
CREATE TABLE employee
(
  name VARCHAR(50),
  age INT,
  salary INT
);
```
- this command creates a new table inside a connected database. Here, table name is `employee` and database name is `trendytech`.
- `VARCHAR` and `INT` are two datatypes from many datatypes. `VARCHAR` is used for `string` and `INT` is used for `numeric`.

`SHOW TABLES;`
- this command is used for list of tables of connected database.

`DESCRIBE employee;` or `DESC employee;`
- this command is used for describing or showing a table structure.
![describe employee table](images/session1/describe_employee.png)

`DROP TABLE employee`
- this command will delete `employee` table.

**If you drop connected database and want to create a table, you will get a error because you are not connected to any database. This is expected becuse you should be connected to any database to create tables.**

**If you are not connected to any database and want to create tables you have to explicitely defined database name like below example.**

```
CREATE TABLE trendytech.employee
(
  name VARCHAR(50),
  age INT,
  salary INT
);
```
- here `trendytech` is database name and `employee` is table name.

# Learn SQL the right way - Session 2

**CRUD - Operations**
```
create - insert statements
read - select statements
create - update statements
create - delete statements

```

Let's start with fresh `employee` table by deleting previous one. Create `employee` table by this command.

```
CREATE TABLE employee
(
  firstname VARCHAR(20),
  middlename VARCHAR(20),
  lastname VARCHAR(20),
  age INT,
  salary INT,
  location VARCHAR(20)
);
```
To see the structure of this table. Please give below command.
`DESC employee;`
![employee table structure](images/session2/employee_table.png)

`SELECT * FROM employee;`
- this command is used for to show all data from `employee` table.
- here `*` means all data

Now, we want to insert some data inside this `employee` table. Let's use this command.

`INSERT INTO employee VALUES ('kapil', 'kumar', 'sharma', 30, 30000, 'bangalore');`
- by this command you can insert data.
But it is recommended. Recommended approach is always mention column name after table name. Otherwise, you will get error if column count and value does not match.

`INSERT INTO employee(firstname, middlename, lastname, age, salary, location) VALUES ('kapil', 'kumar', 'sharma', 30, 30000, 'bangalore');`

If you want to skip one column then you can give like this command.

`INSERT INTO employee(firstname, lastname, age, salary, location) VALUES ('rajesh', 'sharma', 32 , 30000, 'bangalore');`
- here `middlename` column we have skipped and so `middlename` value will be `NULL`.
- `NULL` value basically `undefined`.

If you skip any column then you should mention column name, otherwise you have to insert all column data. Look at this command:

`INSERT INTO employee VALUES ('rajesh', 'sharma', 32 , 30000, 'bangalore');`
- you will get error (column count doesn't match value count) because you skip `middlename` column but you don't mention column name.

If you want to insert value with single quote or double quote you have to give wrap quote with another quote. Or, you can use escape(\) character.
```
"rajesh's" or 'rajesh"s' or 'rajesh\'s'
```

For inserting multiple values you can give below command.
`INSERT INTO employee(firstname, lastname, age, salary, location) VALUES ('rajesh', 'sharma', 32 , 30000, 'bangalore'), ('rakesh', 'bala', 40 , 90000, 'bangalore') ;`
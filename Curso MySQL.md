# Introduction

## Workbench shortcuts

Execute queries:

> ctrl + enter

## Difference between MySQL and SQL

- MySQL: Database management system.

- SQL ('sequel'): Structured Query Languages. Not a programming language, but a data extraction language.


# First Steps

## Setup New Connection in Workbench

1. Click on '+'

<img src="images/im_01.png" width="200" style="float: left;">

2. Write a connection name

3. Click on 'Test connection'
   > A window with 'Please enter password' should appear

4. Enter password and click on 'Ok
   > Connection should have been added to the start page

**Note.**

> Troubles can appear here if XAMPP is installed, because it also uses 3306 port.

# Databases fundamentals

## Data types

- int
- float
- varchar

## Create a DB

1. Write:

```sql
create database holamundo;
```

2. Click on the **'lightning' symbol to execute**
	> In the bottom there's the 'terminal', known as 'Action output'. There we'll see a record of the actions performed.

## Find out existing databases managed by MySQL

1. Write and execute:

   ```sql
   show databases;
   ```

## Create a table

1. Write and execute:

   (1/2)

   ```sql
   use holamundo;
   ```

   (2/2)	

```sql
CREATE TABLE animales(
    /* Rows */
	id			int,
 -- id			int NOT NULL AUTO_INCREMENT		 -- (Optional) Give 'id' an auto-increase property  
	tipo		varchar(255),					-- varchar's argument indicates max size of string
    estado		varchar(255),
    PRIMARY KEY(id)								-- indicate which row is the PK
);
```

## Modify an existing table

**Give 'id' an auto-increase property**

1. Write and execute:

```sql
ALTER TABLE animales MODIFY COLUMN id int auto_increment;		-- table, column, var type
```

## Insert data inside a table

1. Write and execute:

```sql
INSERT INTO animales (tipo, estado) VALUES('caballo', 'feliz')		-- Fields, Values
```

## Get the  'creation query' of a table

This may be useful to see how our fields are defined, or maybe to create a replica table. 

1. Write and execute:

```sql
SHOW CREATE TABLE animales;
```

Note:

> For this statement to work, it needs to be executed as a standalone query. That is, if our 'script' window has any other code lines, it won't work. We need to comment or delete all other statements.

2. In 'result grid': 
   1. Right click on 'Create table'
   
   2. Click on 'Copy field (unquoted)'
   

After this, we are able to paste the Query and see how that table is defined. It should look like this: [Table creation query](#Introduction)

s.

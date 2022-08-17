**SQL is a standard language for accessing and manipulating databases.**

**What is SQL?**

SQL stands for Structured Query Language
SQL lets you access and manipulate databases
SQL became a standard of the American National Standards Institute (ANSI) in 1986, and of the International Organization for Standardization (ISO) in 1987

**What Can SQL do?**

SQL can execute queries against a database

SQL can retrieve data from a database

SQL can insert records in a database

SQL can update records in a database

SQL can delete records from a database

SQL can create new databases

SQL can create new tables in a database

SQL can create stored procedures in a database

SQL can create views in a database

SQL can set permissions on tables, procedures, and views


**SQL is a Standard - BUT....**

Although SQL is an ANSI/ISO standard, there are different versions of the SQL language. However, to be compliant with the ANSI standard, they all support at least the major commands (such as SELECT, UPDATE, DELETE, INSERT, WHERE) in a similar manner.

**Note:-** Most of the SQL database programs also have their own proprietary extensions in addition to the SQL standard!

**Using SQL in Your Web Site**

To build a web site that shows data from a database, you will need:

An RDBMS database program (i.e. MS Access, SQL Server, MySQL)

To use a server-side scripting language, like PHP or ASP

To use SQL to get the data you want

To use HTML / CSS to style the page

**RDBMS stands for Relational Database Management System.**

RDBMS is the basis for SQL, and for all modern database systems such as MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access. The data in RDBMS is stored in database objects called tables. A table is a collection of related data entries and it consists of columns and rows.


**Note:-** SQL keywords are NOT case sensitive: select is the same as SELECT


**Note:-** Some database systems require a semicolon at the end of each SQL statement

**Semicolon is the standard way to separate each SQL statement in database systems that allow more than one SQL statement to be executed in the same call to the server. **


**Most Important SQL Commands**

**SELECT** - extracts data from a database

**UPDATE** - updates data in a database

**DELETE** - deletes data from a database

**INSERT INTO** - inserts new data into a database

**CREATE DATABASE** - creates a new database

**ALTER DATABASE** - modifies a database

**CREATE TABLE** - creates a new table

**ALTER TABLE** - modifies a table

**DROP TABLE** - deletes a table

**CREATE INDEX** - creates an index (search key)

**DROP INDEX** - deletes an index





**THE SQL SELECT Statement**

The SELECT statement is used to select data from a database. The data returned is stored in a result table, called the result-set.

For calling all columns **SELECT * FROM table_name;**

For callinng respective columns **SELECT CustomerName, City FROM Customers;**




**THE SQL SELECT DISTINCT Statement**

The **SELECT DISTINCT** statement is used to return only distinct (different) values. Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values.

Using **count** keyword we can know the number of **different (distinct)** customer countries:

SELECT **COUNT(DISTINCT Country) FROM Customers;**

Keywords:- **COUNT, DISTINCT**




**The SQL WHERE Clause**

The **WHERE clause is used to filter records.** It is used to extract only those records that fulfill a specified condition.

**Note: The WHERE clause is not only used in SELECT statements, it is also used in UPDATE, DELETE, etc.!**

 Example:- **SELECT * FROM Customers WHERE Country='Mexico';**
 
**Text Fields vs. Numeric Fields**
SQL requires single quotes around text values (most database systems will also allow double quotes). However, numeric fields should not be enclosed in quotes.

**Operators in The WHERE Clause**

The following operators can be used in the WHERE clause:

Operator	Description	Example

**=**	 Equal	

**>**	Greater than	

**<**	Less than	

**>=**	Greater than or equal	

**<=**	Less than or equal	

**<>**	Not equal. Note: In some versions of SQL this operator may be written as !=	

**BETWEEN**	Between a certain range	

**LIKE**	Search for a pattern	

**IN**	To specify multiple possible values for a column

**The SQL AND, OR and NOT Operators**

The WHERE clause can be combined with AND, OR, and NOT operators.

The **AND** and **OR** operators are used to filter records based on more than one condition:

The **AND** operator displays a record if all the conditions separated by **AND are TRUE**.

The **OR** operator displays a record if any of the conditions separated by **OR is TRUE**.

The **NOT** operator displays a record if the condition(s) is **NOT TRUE**.





**THE SQL ORDER BY**

The **ORDER BY** keyword is used to sort the result-set in **ascending or descending** order.

The **ORDER BY** **keyword sorts the records in ascending order by default. To sort the records in descending order, use the DESC keyword**.
 
 Keywords:- **ORDER BY,ASC AND DESC**
  
 
  
  
**The SQL INSERT INTO Statement**

The INSERT INTO statement is used to insert new records in a table. It is possible to write the INSERT INTO statement in two ways:

1. Specify both the column names and the values to be inserted:
   **INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);**

2. If you are adding values for all the columns of the table, you do not need to specify the column names in the SQL query. However, make sure the order of the values is in the same order as the columns in the table. Here, the INSERT INTO syntax would be as follows:
 **INSERT INTO table_name VALUES (value1, value2, value3, ...);**
 
 **Did you notice that we did not insert any number into the CustomerID field?
The CustomerID column is an auto-increment field and will be generated automatically when a new record is inserted into the table.**

Keywords:- **INSERT INTO, VALUES**
 
 
 
 

 

**What is a NULL Value?**

A field with a NULL value is a field with no value. If a field in a table is optional, it is possible to insert a new record or update a record without adding a value to this field. Then, the field will be saved with a NULL value.

**Note: A NULL value is different from a zero value or a field that contains spaces. A field with a NULL value is one that has been left blank during record creation!**

**How to Test for NULL Values?**

It is not possible to test for NULL values with comparison operators, such as **=, <, or <>.**

We will have to use the **IS NULL** and **IS NOT NULL** operators instead.

The **IS NULL operator** is used to test for empty values (NULL values). The following SQL lists all customers with a NULL value in the "Address" field:

**SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NULL;
o/p:_ No result.**

**Tip:** Always use IS NULL to look for NULL values.

The **IS NOT NULL operator** is used to test for non-empty values (NOT NULL values). The following SQL lists all customers with a value in the "Address" field:

**SELECT CustomerName, ContactName, Address
FROM Customers
WHERE Address IS NOT NULL;
result:- 97 records**

Keywords:- **IS NULL, IS NOT NULL**


**UPDATE Multiple Records**

It is the WHERE clause that determines how many records will be updated. The following SQL statement will update the ContactName to "Juan" for all records where country is "Mexico"
**Note:-** Be careful when updating records. If you omit the WHERE clause, ALL records will be updated!

Keywords:- **Update and Set**



**The SQL DELETE Statement**

The **DELETE** statement is used to delete existing records in a table.
 
 **DELETE FROM table_name WHERE condition;**
 
 **Note:-** Be careful when deleting records in a table! Notice the WHERE clause in the DELETE statement. The WHERE clause specifies which record(s) should be deleted. If you omit the WHERE clause, all records in the table will be deleted!
 
 Ex:- **DELETE FROM **Customers WHERE CustomerName='Alfreds Futterkiste';**
 
 **Delete All Records** It is possible to delete all rows in a table without deleting the table. This means that the table structure, attributes, and indexes will be intact.
 
**DELETE FROM table_name;**

**DELETE FROM Customers WHERE Country = 'Norway**


**The SQL SELECT TOP Clause**

The **SELECT TOP** clause is used to specify the number of records to return. 

The **SELECT TOP** clause is useful on large tables with thousands of records. Returning a large number of records can impact performance.

**Note:-** Not all database systems support the **SELECT TOP** clause. MySQL supports the LIMIT clause to select a limited number of records, while Oracle uses FETCH FIRST n ROWS ONLY and ROWNUM.



**The SQL MIN() and MAX() Functions**

The **MIN()** function returns the smallest value of the selected column.

SELECT MIN(column_name)
FROM table_name
WHERE condition;

Example:- SELECT MIN(Price) AS SmallestPrice FROM Products;

The **MAX()** function returns the largest value of the selected column.

SELECT MAX(column_name)
FROM table_name
WHERE condition;

Example:- SELECT MAX(Price) AS LargestPrice FROM Products;


**The SQL COUNT(), AVG() and SUM() Functions**

The **COUNT()** function returns the number of rows that matches a specified criterion.

Ex:- SELECT **COUNT**(column_name) FROM table_name WHERE condition; 
     SELECT COUNT(ProductID) FROM Products;


The **AVG()** function returns the average value of a numeric column.

Ex:- SELECT **AVG**(column_name) FROM table_name WHERE condition;
     SELECT AVG(Price) FROM Products;


The **SUM()** function returns the total sum of a numeric column. 

 Ex:- SELECT SUM(column_name) FROM table_name WHERE condition;
      SELECT SUM(Quantity) FROM OrderDetails;





**The SQL LIKE Operator**

The **LIKE** operator is used in a **WHERE** clause to search for a specified pattern in a column.

There are two wildcards often used in conjunction with the LIKE operator:

 The **percent sign (%) **represents zero, one, or multiple characters
 The underscore sign (_) represents one, single character.
 
Note: MS Access uses an asterisk (*) instead of the percent sign

**Tip: You can also combine any number of conditions using AND or OR operators.**


Here are some examples showing different **LIKE** operators with **'%'** and **'_' wildcards:**

WHERE CustomerName LIKE **'a%'**	Finds any values that start with "a"

WHERE CustomerName LIKE **'%a'**	Finds any values that end with "a"

WHERE CustomerName LIKE **'%or%'**	Finds any values that have "or" in any position

WHERE CustomerName LIKE **'_r%'**	Finds any values that have "r" in the second position

WHERE CustomerName LIKE **'a_%'**	Finds any values that start with "a" and are at least 2 characters in length

WHERE CustomerName LIKE **'a__%'**	Finds any values that start with "a" and are at least 3 characters in length

WHERE ContactName LIKE **'a%o'**	Finds any values that start with "a" and ends with "o"

Keywords:- **LIKE, NOT, '%', '_'**

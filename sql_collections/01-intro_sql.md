# Intorduction to SQL
SQL is a standard language for accessing and manipulating databases.
* SQL stands for Structured Query Language
* SQL lets you access and manipulate databases
* SQL became a standard of the AMerican National Standard Institute (ANSI) in 1986, and of the International Organization for Standarization (ISO) in 1987

## What can SQL do?
* SQL can execute queries against a database
* SQL can retrienve data from the database
* SQL can insert records in a database
* SQL can update records in a database
* SQL can delete recorrds in a database
* SQL can create new databases
* SQL can create new tables in a database
* SQL can create stored procedures in a database
* SQL can create views in a database
* SQL can set permissions on tables, procedures, and views

## SQL is Standard - BUT ....
Although SQL is an ANSI/ISO standard, there are different version of the SQL language.
However, to be compliant with the ANSI standard, they all support at least the major command (such as SELECT, UPDATE, DELETE, INSERT, WHERE) in a similar manner.

Note: Most of the SQL database programs also have their own proprietary extensions in addition to the SQL standard!

## Uisng SQL in Your Web Site
To build a web site that shows data from a database, you will need:
* An RDBMS database program (i.e MS Access, SQL Server, MySQL)
* To use a server-side scripting language, like PHP or ASP
* To use SQL to get the data you want
* To use HTML/CSS to style the page

## RDBMS
RDBMS stands for Relational Database Management System.

RDBMS is the basic for SQL, and for all modern database systems such as MS SQL Server, IBM DB2, Oracle, MySQL, and Microsoft Access.

The data in RDBMS is stored in database objects called tables. A table is a collection of related data entries and it consists of columns and rows.

Look at the "Customers" table:

## Example:
```sql
SELECT * FROM Customers;
```
<img width="411" height="304" alt="image" src="https://github.com/user-attachments/assets/446642ba-8f5b-453e-8623-48d0b90d788a" />
<img width="2023" height="503" alt="image" src="https://github.com/user-attachments/assets/24861a45-1322-484c-bc12-e264f686dbed" />

The columns in the "Customers" table consist of CustomerID, CustomerName, ContactName, Address, City, PostalCode and Country. A column is a vertical entity in a table.
A record also called a row is each individual entry that exits in a table. For example, there are 91 records in the above Customers table. A record is a horizontal entity in a table.

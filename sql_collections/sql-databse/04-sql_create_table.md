# SQL CREATE TABLE Statement
The CREATE TABLE statement is used to create a new table in a database.

## Syntax
```sql
CREATE TABLE table_name (
  column1 datatype constraint,
  column2 datatype constraint,
  column3 datatype constraint,
  ....
);
```

The table_name parameter specifies the name of the new table.

The column1, column2... parameters specify the names of the columns within the table.

The datatype parameter specifies the data type of each column (e.g. varchar, int, date, etc.).

The constraint parameter is optional, and specifies rules for data integrity (e.g. primary key, not null, etc.).

## CREATE TABLE Example:
The following example creates a table named "Persons" with five columns:

## Example:
```sql
CREATE TABLE Persons (
  PersonID int PRIMARY KEY,
  LastName varchar(255) NOT NULL,
  FirstName varchar(255),
  Address varchar(255),
  City varchar(255)
);
```

## Example Explained:
* PersonID - This column is of type integer (int). This is also the PRIMARY KEY field, that uniquely identifies each row.
* LastName - This column is variable-length character string with a maximum length of 255 characters (varchar(255)). NOT NULL specifies that this column cannot be empty.
* FirstName, Address, City - These columns are also variable-length character strings with a maximum length of 255 characters (varchar(255)). These columns allo NULL values by default.

The empty "Persons" table will now look like this:
|PersonID|	LastName|	FirstName|	Address	City|
|--------|----------|----------|--------------|
|        |          |          |              |

Tip: The empty "Persons" table can now be filled with data, with the SQL INSERT INTO statement.

## Create New Table From Existing Table
The CREATE TABLE statement can also be used to create a new table that copies some/all data from an existing table.

## Syntax
```sql
CREATE TABLE new_table AS
SELECT column1, column2,...
FROM existing_table
WHERE ....;
```

The following SQL creates a new table called "GermanCustomers"(which is a copy of the "Customers" table):

## Example:
```sql
CREATE TABLE GermanCustomers AS
SELECT * FROM Customers
WHERE Country = 'Germany';
```

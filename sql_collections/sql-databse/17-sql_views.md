# SQL Views
An SQL view is a virtual table based on the result-set of an SQL statement. An SQL view contains rows and columns just like a real table. The fields in the view are fields from one or more real tables in the database.

You can add SQL statements and functions to a view and present the data as if it were coming from one single table.

A view is created with the CREATE VIEW statemenet.

## CREATE VIEW Syntax
```sql
CREATE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

Note: A view always shows real-time data! The database engine only stores the view's definition (the SELECT statement), not a copy of the data.

## CREATE VIEW Examples
The following SQL creates a view named "Brazil Customers", that shows all customers from Brazil:

## Example:
```sql
CREATE VIEW [Brazil Customers] AS
SELECT CustomerName, ContactName
FROM Customers
WHERE Country = 'Brazil';
```

To query the view above, use the following SQL syntax:

## Example:
```sql
SELECT * FROM [Brazil Customers];
```

The following SQL creates a view named "Products Above Average Price", that selects all products in the "Products" table with a Price higher than the average price:

## Example:
```sql
CREATE VIEW [Products Above Average Price] AS
SELECT ProductName, Price
FROM Products
WHERE Price > (SELECT AVG(Price) FROM Products);
```

To query the view above, use the following syntax:

## Example:
```sql
SELECT * FROM [Products Above Average Price];
```

## CREATE OR REPLACE VIEW Statement (MySQL and Oracle)
In MySQL and Oracle, a view can be updated with the CREATE OR REPLACE VIEW statement.

## CREATE OR REPLACE VIEW Syntax
```sql
CREATE OR REPLACE VIEW view_name AS
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

The following SQL adds the "City" column to the "Brazil Customers" view:

## Example:
```sql
CREATE OR REPLACE VIEW [Brazil Customers] AS
SELECT CustomerName, ContactName, City
FROM Customers
WHERE Country = 'Brazil';
```

## DROP VIEW Statement
A view is deleted with the DROP VIEW statement.
```sql
DROP VIEW view_name;
```

The following SQL deletes the "Brazil Customers" view:
## Example:
```sql
DROP VIEW [Brazil Customers];
```

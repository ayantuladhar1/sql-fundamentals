# SQL NOT NULL Constraint
The NOT NULL constraint enforces a column to NOT accept NULL values. This enforces a field to always contain a value, which means that you cannot insert a new reocrd, or update a record without adding a value to this field.

By default, a column can hold NULL values.

## NOT NULL on CREATE TABLE
To define a NOT NULL constraint when creating a table, add NOT NULL after the data type of the column name.

The following SQL creates a "Persons" table, and ensures that the "ID", ""LastName", and "FirstName" columns cannot accept NULL values:

## Example:
```sql
CREATE TABLE Persons (
    ID int NOT NULL,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255) NOT NULL,
    Age int
);
```

## NOT NULL on ALTER TABLE
To define a NOT NULL constraint on an existing table, use ALTER TABLE and add NOT NULL after the data type of the column name.

The following SQL adds a NOT NULL constraint on the "Age" column, after the "Persons" table is already created:

## Syntax for MySQL:
```sql
ALTER TABLE Persons
MODIFY COLUMN Age int NOT NULL;
```

## Remove a NOT NULL Constraint
To remove a NOT NULL constraint from a column (to let the column accept NULL values again), use the following syntax:

## Syntax for MySQL:
```sql
ALTER TABLE Persons
MODIFY COLUMN Age int NULL;
```
The following SQL adds a NOT NULL 

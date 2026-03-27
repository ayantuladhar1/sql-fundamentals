# SQL ALTER TABLE Statement
The ALTER TABLE statement is used to add, delete or modify columns in an existing table.

The ALTER TABLE statement is also used to add or drop various constraints on an existing table.

Common ALTER TABLE operations are:
* Add column - Adds a new column to a table
* Drop column - Deletes a cokumn in a table
* Rename column - Renames a column
* Modify column - Changes the data type, size or constraints of a column
* Add constraint - Adds a new constraint
* Rename table - Renames a table

## ALTER TABLE - ADD Column
To add a column in a table, use the following syntax:

## Syntax
```sql
ALTER TABLE table_name
ADD column_name datatype;
```

The following SQL adds an "Email" column to the "Customers" table:

## Example:
```sql
ALTER TABLE Customers
ADD Email varchar(255);
```

## ALTER TABLE - DROP COLUMN
To delete a column in a table, use the following syntax (notice that some database systems don't allow deleting a column):

## Syntax
```sql
ALTER TABLE table_name
DROP COLUMN column_name;
```

The following SQL deletes the "Email" column from the "Customers" table:

## Example:
```sql
ALTER TABLE Customers
DROP COLUMN Email;
```

## ALTER TABLE -RENAME COLUMN
To rename a column in a table, use the following syntax:

## Syntax
```sql
ALTER TABLE table_name
RENAME COLUMN old_name to new_name;
```

To rename a column in a table in SQL Server, use the following syntax:

## Syntax for SQL Server:
```sql
EXEC sp_rename 'table_name.old_name', 'new_name', 'COLUMN';
```

## ALTER TABLE - MODIFY Datatype
To modify the data type, size or constraints of a column in a table, use the following syntax:

## Syntax for SQL Server / MS Access:
```sql
ALTER TABLE table_name
ALTER COLUMN column_name new_datatype constraint;
```

## Syntax for MYSQL/Oracle:
```sql
ALTER TABLE table_name
MODIFY column_name new_datatype constraint;
```

The following SQL modifies the size of the "Email" column to varchar(100), and we also add a NOT NULL constraint:

## Example:
```sql
ALTER TABLE Customers
MODIFY Email varchar(100) NOT NULL;
```

## ALTER TABLE - ADD CONSTRAINT
To add a constraint to an existing table, use the following syntax:

## Syntax:
```sql
ALTER TABLE table_name
ADD CONSTRAINT constraint_name constraint_definition;
```

The following SQL adds a constraint named "CHK_Age" that is a CHECK constraint that ensures that the "Age" column has a value of 18 and above:

## Example:
```sql
ALTER TABLE Members
ADD CONSTRAINT CHK_Age CHECK (Age >= 18);
```

## ALTER TABLE - Rename Table
To rename a table, use the following syntax:

## Syntax
```sql
ALTER TABLE table_name
RENAME TO new_table_name;
```
 
The following SQL renames the "Customers" table to "Clients":

## Example:
```sql
ALTER TABLE Customers
RENAME TO Clients;
```

## SQL ALTER TABLE Example
Assume we have a "Persons" table, that look like this:

| ID | LastName  | FirstName | Address      | City      |
| -- | --------- | --------- | ------------ | --------- |
| 1  | Hansen    | Ola       | Timoteivn 10 | Sandnes   |
| 2  | Svendson  | Tove      | Borgvn 23    | Sandnes   |
| 3  | Pettersen | Kari      | Storgt 20    | Stavanger |

Now we want to add a column named "DateOfBirth" in the "Persons" table.

We use the following SQL statement:

## Example:
```sql
ALTER TABLE Persons
ADD DateOfBirth date;
```

Notice that the new column "DateOfBirth," is of type date and isgoing to hold a date. The data type specifies what type of data the column can hold. FOr a complete reference of all data types available in MS Access, MySQL and SQL Server, go to our Data Types reference.

The "Persons" table will now look like this:

| ID | LastName  | FirstName | Address      | City      | DateOfBirth |
| -- | --------- | --------- | ------------ | --------- | ----------- |
| 1  | Hansen    | Ola       | Timoteivn 10 | Sandnes   |             |
| 2  | Svendson  | Tove      | Borgvn 23    | Sandnes   |             |
| 3  | Pettersen | Kari      | Storgt 20    | Stavanger |             |

## Change Data Type Example:
Now we want to change the dat type of the column named "DateOfBirth" in the "Persons" table.

We usethe following SQL statement:

## Example:
```sql
ALTER TABLE Persons
ALTER COLUMN DateOfBirth year;
```

Notice that the "DateOfBirth" column is now of type year and is going to hold a year in a two- or four - digit format.

## DROP COLUMN Example:
Next, we want to delete the column named "DateOfBirth" in the "Persons" table.

We use the following SQL statement:

## Example:
```sql
ALTER TABLE Persons
DROP COLUMN DateOfBirth;
```

The "Persons" table will now look like this:

| ID | LastName  | FirstName | Address      | City      |
| -- | --------- | --------- | ------------ | --------- |
| 1  | Hansen    | Ola       | Timoteivn 10 | Sandnes   |
| 2  | Svendson  | Tove      | Borgvn 23    | Sandnes   |
| 3  | Pettersen | Kari      | Storgt 20    | Stavanger |


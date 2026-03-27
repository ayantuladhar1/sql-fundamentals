# SQL AUTO INCREMENT Field
An auto-increment field is a numeric column that automatically generates a unique number, when a new record is inserted into a table.

The auto-increment field is typically the PRIMARY KEY field that we want to automatically be assigned a unique number, every time a new record is inserted.

## Syntax for MySQL
MySQL uses the AUTO_INCREMENT keyword to perform an auto-increment feature.

The following SQL defines the "Personid" column to be an auto-increment primary key field in the "Persons" table:
```sql
CREATE TABLE Persons (
    Personid int AUTO_INCREMENT PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

The default starting value for AUTO_INCREMENT is 1, and it will increment by 1 for each new record.

To let AUTO_INCREMENT start with another value, use the following SQL statement:
```sql
ALTER TABLE Persons AUTO_INCREMENT = 100;
```

When we insert a new record into the "Persons" table, we will NOT have to specify a value for the "Personid" column (a unique value will be added automatically):
```sql
INSERT INTO Persons (FirstName, LastName)
VALUES ('Lars', 'Monsen');
```

The SQL above inserts a new record into the "Persons" table, and the "Personid" column will automatically be assigned the next unique number.

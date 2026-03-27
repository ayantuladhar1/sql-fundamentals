# SQL PRIMARY KEY Constraint
The PRIMARY KEY constraint uniquely identifies each record in a database table.

A PRIMARY KEY constraint ensures unique values, and cannot contain NULL values (it is a combination of both UNIQUE constraint and a NOT NULL constraint).

A table can have only ONE PRIMARY KEY constraint. The primary key can either be a single column, or a combination of columns.

Tip: The primary key is the target for FOREIGN KEY constraints in other tables (which enforces referential intgrity between data in two tables).

## PRIMARY KEY on CREATE TABLE
The following SQL creates a PRIMARY KEY on the "ID" column upon creation of the "Persons" table:
```sql
CREATE TABLE Persons (
    ID int PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int
);
```

## PRIMARY KEY on Multiple Columns
To define an un-named PRIMARY KEY constraint on multiple columns, use the following SQL syntax:
```sql
CREATE TABLE Persons (
    ID int,
    LastName varchar(255),
    FirstName varchar(255),
    Age int,
    PRIMARY KEY (ID, LastName)
);
```

Note: In the example above, the PRIMARY KEY value is made up of two columns (ID + LastName).

To define a named PRIMARY KEY constraint on multiple columns, use the following SQL syntax:
```sql
CREATE TABLE Persons (
    ID int,
    LastName varchar(255),
    FirstName varchar(255),
    Age int,
    CONSTRAINT PK_Person PRIMARY KEY (ID, LastName)
);
```

Note: In the example above, the PRIMARY KEY is named "PK_PERSON", and the value is made up of two columns (ID + LatName).

## PRIMARY KEY on ALTER TABLE
To create a PRIMARY KEY constraint on the "ID" column when the table already has been created, use the foloowing SQL:
```sql
ALTER TABLE Persons
ADD PRIMARY KEY (ID);
```

## PRIMARY KEY on Multiple Columns
To define a named PRIMARY KEY constraint on mutiple column, use the following SQL syntax:
```sql
ALTER TABLE Persons
ADD CONSTRAINT PK_Person PRIMARY KEY (ID, LastName);
```

Note: When using ALTER TABLE to add a primary key, the primary key columns must have been decalred with NOT NULL upon creation of the table.

## Drop a PRIMARY KEY Constraint
To drop a PRIMARY KEY constraint, use the following SQL:

## MySQL:
```sql
ALTER TABLE Persons
DROP PRIMARY KEY;
```

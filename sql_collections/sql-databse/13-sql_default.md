# SQL DEFAULT Constraint
The DEFAULT constraint is ised to automatically insert a default value for a column, if no value is specified.

The default value will be added to all new records (if no other value is specified).

## DEFAULT Constraint on CREATE TABLE
The following SQL sets a DEFAULT value for the "City" column upon creation of the "Persons" table:
```sql
CREATE TABLE Persons (
    ID int PRIMARY KEY,
    LastName varchar(255) NOT NULL,
    FirstName varchar(255),
    Age int,
    City varchar(255) DEFAULT 'Sandnes'
);
```

The DEFAULT constraint can also be used to insert system values, by using functions like CURRENT_DATE() to insert the current date:

## MySQL:
```sql
CREATE TABLE Orders (
    ID int PRIMARY KEY,
    OrderNumber int NOT NULL,
    OrderDate date DEFAULT CURRENT_DATE()
);
```

## DEFAULT Constraint on ALTER TABLE
To define a DEFAULT constraint on the "City" column when the table is already created, use the following SQL:

## MySQL:
```sql
ALTER TABLE Persons
ALTER City SET DEFAULT 'Sandnes';
```

## Drop a DEFAULT Constraint
To drop a DEFAULT constraint, use the following SQL:

## MySQL:
```sql
ALTER TABLE Persons
ALTER City DROP DEFAULT;
```

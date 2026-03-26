# SQL DROP DATABASE Statement
The DROP DATABASE Statement is used to permanently delete an existing SQL database.

Note: Be careful before dropping a database! Dropping a database deletes the database and all its content (tables, views, stored procedures, and data)!

## Syntax
```sql
DROP DATABASE databasename;
```

Tip: You need administrative privileges to drop a database.

## DROP DATABASE Example:
The following SQL statement drops an existing database named "testDB":

## Example:
```sql
DROP DATABASE testDB;
```

Tip: Once a database is dropped, you can check that it is removed from the list of databases with: SHOW DATABASES

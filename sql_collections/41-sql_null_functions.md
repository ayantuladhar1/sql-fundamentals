# SQL NULL Functions
## SQL COALESCE(), IFNULL(), ISNULL(), and NVL() Functions

Operations involving NULL values can sometimes lead to unexpected results.

SQL has some built-in functions to handle NULL values, and the most common functions are:
* COALESCE() - The preferred standard (Works in MySQL, SQL Server and Oracle)
* IFNULL() - (MySQL)
* ISNULL() - (SQL Server)
* NVL() - (Oracle)
* IsNull() - (MSAccess)

Note: A NULL value represents an unknown or missing data in a database field. It is not a value itself, but a placeholder to indicate the absence of data.

## Demo Database
Assume we have the following "Products" table:

| PId | ProductName | Price | InStock | InOrder |
| --- | ----------- | ----- | ------- | ------- |
| 1   | Jarlsberg   | 10.45 | 16      | 15      |
| 2   | Mascarpone  | 32.56 | 23      | _null_  |
| 3   | Gorgonzola  | 15.67 | 9       | 20      |

The "InOrder" column is optional, and may contain NULL values.

Now look at the following SQL statement:
```sql
SELECT ProductName, Price * (InStock + InOrder)
FROM Products;
```

Note: In the SQL above, if any of the "InOrder" values are NULL, the result will be NULL!

## The COALESCE() Function
The COALESCE() function is the preferred standard for handling potential NULL values.

The COALESCE() function returns the first non-NULL value in a list of values.

The COALESCE() function works in MySQL, SQL Server and Oracle (not in MS Access).

## Syntax
```sql
COALESCE(val1, val2, ...., val_n)
```

Here we use the COALESCE() function to replace NULL values with 0:
```sql
SELECT ProductName, Price * (InStock + COALESCE(InOrder, 0))
FROM Products;
```

## The IFNULL() Function (MySQL)
The MySQL IFNULL() function replaces NULL with a specified value.

## Syntax
```sql
IFNULL(expr, alt)
```

Here we replace NULL values with 0:
```sql
SELECT ProductName, Price * (InStock + IFNULL(InOrder, 0))
FROM Products;
```

## The ISNULL() Function (SQL Server)
The SQL Server ISNULL() function replaces NULL with a specified value.

## Syntax
```sql
ISNULL(expr, alt)
```

Here we replace NULL values with 0:
```sql
SELECT ProductName, Price * (InStock + ISNULL(InOrder, 0))
FROM Products;
```

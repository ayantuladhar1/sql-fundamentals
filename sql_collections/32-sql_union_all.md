# SQL UNION ALL Operator
The UNION ALL operator is used to combine the result-set of two or more SELECT statements.

The UNION ALL operator includes all rows from each statement, including any duplicates.

Requirements for UNION ALL:
* Every SELECT statement within UNION ALL must have the same number of columns
* The columns must also have similar data types
* The columns in every SELECT statement must also be in the same order

## UNION ALL Syntax
```sql
SELECT column_name(s) FROM table1
UNION ALL
SELECT column_name(s) FROM table2;
```

Note: The column names in the result-set are usually equal to the column names in the first SELECT statement.

## Demo Database

Below is a selection from the "Customers" table:

| CustomerID | CustomerName                       | ContactName    | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | -------------- | ----------------------------- | ----------- | ---------- | ------- |
| 1          | Alfreds Futterkiste                | Maria Anders   | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo   | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno | Mataderos 2312                | México D.F. | 05023      | Mexico  |

And a selection from the "Suppliers" table:

| SupplierID | SupplierName               | ContactName      | Address        | City        | PostalCode | Country |
| ---------- | -------------------------- | ---------------- | -------------- | ----------- | ---------- | ------- |
| 1          | Exotic Liquid              | Charlotte Cooper | 49 Gilbert St. | London      | EC1 4SD    | UK      |
| 2          | New Orleans Cajun Delights | Shelley Burke    | P.O. Box 78934 | New Orleans | 70117      | USA     |
| 3          | Grandma Kelly's Homestead  | Regina Murphy    | 707 Oxford Rd. | Ann Arbor   | 48104      | USA     |

## SQL UNION ALL Example:
The following SQL returns all the countries (also duplicate values) from both the "Customers" and the "Suppliers" table:

## Example:
```sql
SELECT Country FROM Customers
UNION ALL
SELECT Country FROM Suppliers
ORDER BY Country;
```

| Country     |
| ----------- |
| Argentina   |
| Argentina   |
| Argentina   |
| Australia   |
| Australia   |
| Austria     |
| Austria     |
| Belgium     |
| Belgium     |
| Brazil      |
| Brazil      |
| Brazil      |
| Brazil      |
| Brazil      |
| Brazil      |
| Brazil      |
| Brazil      |
| Brazil      |
| Brazil      |
| Canada      |
| Canada      |
| Canada      |
| Canada      |
| Canada      |
| Denmark     |
| Denmark     |
| Denmark     |
| Finland     |
| Finland     |
| Finland     |
| France      |
| France      |
| France      |
| France      |
| France      |
| France      |
| France      |
| France      |
| France      |
| France      |
| France      |
| France      |
| France      |
| France      |
| Germany     |
| Germany     |
| Germany     |
| Germany     |
| Germany     |
| Germany     |
| Germany     |
| Germany     |
| Germany     |
| Germany     |
| Germany     |
| Germany     |
| Germany     |
| Germany     |
| Ireland     |
| Italy       |
| Italy       |
| Italy       |
| Italy       |
| Italy       |
| Japan       |
| Japan       |
| Mexico      |
| Mexico      |
| Mexico      |
| Mexico      |
| Mexico      |
| Netherlands |
| Norway      |
| Norway      |
| Poland      |
| Portugal    |
| Portugal    |
| Singapore   |
| Spain       |
| Spain       |
| Spain       |
| Spain       |
| Spain       |
| Spain       |
| Sweden      |
| Sweden      |
| Sweden      |
| Sweden      |
| Switzerland |
| Switzerland |
| UK          |
| UK          |
| UK          |
| UK          |
| UK          |
| UK          |
| UK          |
| UK          |
| UK          |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| USA         |
| Venezuela   |
| Venezuela   |
| Venezuela   |
| Venezuela   |

## SQL UNION ALL With WHERE
Here we add a WHERE clause to return all the German cities from both the "Customers" and the "Suppliers" table:

## Example:
```sql
SELECT City, Country FROM Customers
WHERE Country='Germany'
UNION ALL
SELECT City, Country FROM Suppliers
WHERE Country='Germany'
ORDER BY City;
```

| City           | Country |
| -------------- | ------- |
| Aachen         | Germany |
| Berlin         | Germany |
| Berlin         | Germany |
| Brandenburg    | Germany |
| Cunewalde      | Germany |
| Cuxhaven       | Germany |
| Frankfurt      | Germany |
| Frankfurt a.M. | Germany |
| Köln           | Germany |
| Leipzig        | Germany |
| Mannheim       | Germany |
| München        | Germany |
| Münster        | Germany |
| Stuttgart      | Germany |


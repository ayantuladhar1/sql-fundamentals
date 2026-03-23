# SQL GROUP BY Statement
The GROUP BY statement is used to group rows that have the same values into summary rows, like "Find the number of customers in each country".

The GROUP BY statement is almost always used in conjunction with aggregate functions, like COUNT(), MAX(), MIN(), SUM(), AVG(), to perform calculations on each group.

## GROUP BY Syntax
```sql
SELECT column1, aggregate_function(column2), column3, ...
FROM table_name
WHERE condition
GROUP BY column1, column3
ORDER BY column_name;
```

## Demo Database
Below is a selction from the "Customers" table in the Northwind sample database:

| CustomerID | CustomerName                       | ContactName        | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | ------------------ | ----------------------------- | ----------- | ---------- | ------- |
| 1          | Alfreds Futterkiste                | Maria Anders       | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo       | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno     | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 4          | Around the Horn                    | Thomas Hardy       | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                 | Christina Berglund | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |

## SQL GROUP BY Examples:
The following SQL returns the number of customers in each country:

## Example:
```sql
SELECT Country, COUNT(CustomerID) AS [Number of Customers]
FROM Customers
GROUP BY Country;
```

| Country     | Number of Customers |
| ----------- | ------------------- |
| Argentina   | 3                   |
| Austria     | 2                   |
| Belgium     | 2                   |
| Brazil      | 9                   |
| Canada      | 3                   |
| Denmark     | 2                   |
| Finland     | 2                   |
| France      | 11                  |
| Germany     | 11                  |
| Ireland     | 1                   |
| Italy       | 3                   |
| Mexico      | 5                   |
| Norway      | 1                   |
| Poland      | 1                   |
| Portugal    | 2                   |
| Spain       | 5                   |
| Sweden      | 2                   |
| Switzerland | 2                   |
| UK          | 7                   |
| USA         | 13                  |
| Venezuela   | 4                   |

The following SQL returns the number of customers in each country, sorted from high to low:

## Example:
```sql
SELECT Country, COUNT(CustomerID) AS [Number of Customers]
FROM Customers
GROUP BY Country
ORDER BY COUNT(CustomerID) DESC;
```

| Country     | Number of Customers |
| ----------- | ------------------- |
| USA         | 13                  |
| France      | 11                  |
| Germany     | 11                  |
| Brazil      | 9                   |
| UK          | 7                   |
| Spain       | 5                   |
| Mexico      | 5                   |
| Venezuela   | 4                   |
| Italy       | 3                   |
| Canada      | 3                   |
| Argentina   | 3                   |
| Austria     | 2                   |
| Belgium     | 2                   |
| Denmark     | 2                   |
| Finland     | 2                   |
| Portugal    | 2                   |
| Sweden      | 2                   |
| Switzerland | 2                   |
| Norway      | 1                   |
| Poland      | 1                   |
| Ireland     | 1                   |

## Demo Database
Below is a selection from the "Orders" table in the Northwind sample database:

| OrderID | CustomerID | EmployeeID | OrderDate  | ShipperID |
| ------- | ---------- | ---------- | ---------- | --------- |
| 10248   | 90         | 5          | 1996-07-04 | 3         |
| 10249   | 81         | 6          | 1996-07-05 | 1         |
| 10250   | 34         | 4          | 1996-07-08 | 2         |

And a selection from the "Shippers" table:

| ShipperID | ShipperName      |
| --------- | ---------------- |
| 1         | Speedy Express   |
| 2         | United Package   |
| 3         | Federal Shipping |

## GROUP BY With JOIN Example
The following SQL returns the number of orders sent by each shipper:

## Example:
```sql
SELECT Shippers.ShipperName, COUNT(Orders.OrderID) AS NumberOfOrders
FROM Orders
LEFT JOIN Shippers
ON Orders.ShipperID = Shippers.ShipperID
GROUP BY ShipperName;
```

| ShipperName      | NumberOfOrders |
| ---------------- | -------------- |
| Federal Shipping | 68             |
| Speedy Express   | 54             |
| United Package   | 74             |


# SQL HAVING Clause
The HAVING clause is used to filter the results of a GROUP BY query based on aggregate functions. Unlike the WHERE clause, which filters individual rows before grouping, HAVING filters groups after the aggregation has been performed.

## HAVING Syntax
```sql
SELECT column1, aggregate_function(column2), column3, ...
FROM table_name
WHERE condition
GROUP BY column1, column3
HAVING condition -- The condition on grouped data
ORDER BY column_name;
```

## Demo Database
Below is a selection from the "Customers" table in the Northwind sample database:

| CustomerID | CustomerName                       | ContactName        | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | ------------------ | ----------------------------- | ----------- | ---------- | ------- |
| 1          | Alfreds Futterkiste                | Maria Anders       | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo       | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno     | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 4          | Around the Horn                    | Thomas Hardy       | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                 | Christina Berglund | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |

## SQL HAVING Examples
The following SQL returns the number of customers in each country - but only include countries with more than 5 customers:

## Example:
```sql
SELECT Country, COUNT(CustomerID) AS [Number of Customers]
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5;
```

| Country | Number of Customers |
| ------- | ------------------- |
| Brazil  | 9                   |
| France  | 11                  |
| Germany | 11                  |
| UK      | 7                   |
| USA     | 13                  |

The following SQL returns the number of customers in each country, sorted from high to low (and only include countries with more than 5 customers):

## Example:
```sql
SELECT Country, COUNT(CustomerID) AS [Number of Customers]
FROM Customers
GROUP BY Country
HAVING COUNT(CustomerID) > 5
ORDER BY COUNT(CustomerID) DESC;
```

| Country | Number of Customers |
| ------- | ------------------- |
| USA     | 13                  |
| France  | 11                  |
| Germany | 11                  |
| Brazil  | 9                   |
| UK      | 7                   |

## Demo Database
Below is a selection from the "Orders" table in the Northwind sample database:

| OrderID | CustomerID | EmployeeID | OrderDate  | ShipperID |
| ------- | ---------- | ---------- | ---------- | --------- |
| 10248   | 90         | 5          | 1996-07-04 | 3         |
| 10249   | 81         | 6          | 1996-07-05 | 1         |
| 10250   | 34         | 4          | 1996-07-08 | 2         |

And a selection from the "Employees" table:

| OrderID | CustomerID | EmployeeID | OrderDate  | ShipperID |
| ------- | ---------- | ---------- | ---------- | --------- |
| 10248   | 90         | 5          | 1996-07-04 | 3         |
| 10249   | 81         | 6          | 1996-07-05 | 1         |
| 10250   | 34         | 4          | 1996-07-08 | 2         |

## More HAVING Examples:
The following SQL returns the employees that have registered more than 10 orders:

## Example:
```sql
SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders
FROM Orders
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
GROUP BY LastName
HAVING COUNT(Orders.OrderID) > 10;
```

| LastName  | NumberOfOrders |
| --------- | -------------- |
| Buchanan  | 11             |
| Callahan  | 27             |
| Davolio   | 29             |
| Fuller    | 20             |
| King      | 14             |
| Leverling | 31             |
| Peacock   | 40             |
| Suyama    | 18             |

The following SQL returns if the employees "Davolio" or "Fuller" have registered more than 25 orders:

## Example:
```sql
SELECT Employees.LastName, COUNT(Orders.OrderID) AS NumberOfOrders
FROM Orders
INNER JOIN Employees ON Orders.EmployeeID = Employees.EmployeeID
WHERE LastName = 'Davolio' OR LastName = 'Fuller'
GROUP BY LastName
HAVING COUNT(Orders.OrderID) > 25;
```

| LastName | NumberOfOrders |
| -------- | -------------- |
| Davolio  | 29             |


# SQL AND Operator
The WHERE clause can contain one or many AND operators.

The AND operator is used to filter records based on more than one condition.

Note: The AND operator displays a record if all the conditions are TRUE.

The following SQL selects all customers from Spain that starts with the letter 'G':

## Example:
Select all customers where Country is "Spain" AND CustomerName starts with the letter 'G':
```sql
SELECT * FROM Customers
WHERE Country = 'Spain' AND CustomerName LIKE 'G%';
```

| CustomerID | CustomerName           | ContactName       | Address                | City      | PostalCode | Country |
| ---------- | ---------------------- | ----------------- | ---------------------- | --------- | ---------- | ------- |
| 29         | Galería del gastrónomo | Eduardo Saavedra  | Rambla de Cataluña, 23 | Barcelona | 08022      | Spain   |
| 30         | Godos Cocina Típica    | José Pedro Freyre | C/ Romero, 33          | Sevilla   | 41101      | Spain   |

## Syntax
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;
```

## Demo Database
Below is a selection from the Customers table used in the examples:

| CustomerID | CustomerName                       | ContactName        | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | ------------------ | ----------------------------- | ----------- | ---------- | ------- |
| 1 | Alfreds Futterkiste                | Maria Anders       | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo       | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno     | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 4  | Around the Horn                    | Thomas Hardy       | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                 | Christina Berglund | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |


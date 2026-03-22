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

## All Conditions Must be True
The following SQL selects all customers where Country is "Brazil" AND City is "Rio de Janeiro" AND CustomerID is higher than 50:

## Example:
```sql
SELECT * FROM Customers
WHERE Country = 'Brazil'
AND City = 'Rio de Janeiro'
AND CustomerID > 50;
```

| CustomerID | CustomerName       | ContactName      | Address                 | City           | PostalCode | Country |
| ---------- | ------------------ | ---------------- | ----------------------- | -------------- | ---------- | ------- |
| 61         | Que Delícia        | Bernardo Batista | Rua da Panificadora, 12 | Rio de Janeiro | 02389-673  | Brazil  |
| 67         | Ricardo Adocicados | Janete Limeira   | Av. Copacabana, 267     | Rio de Janeiro | 02389-890  | Brazil  |

## AND vs OR
The AND operator displays a record if all the conditions are TRUE.
The OR operator displays a record if any of the conditions are TRUE.

## Combining AND and OR
You can also combine AND and OR operators.
The following SQL selects all customers from Spain that starts with a "G" or an "R" (make sure to use paranthesis to get the correct result):

## Example:
Select all Spanish customers that starts with either "G" or "R":
```sql
SELECT * FROM Customers
WHERE Country = 'Spain'
AND (CustomerName LIKE 'G%' OR CustomerName LIKE 'R%');
```

| CustomerID | CustomerName           | ContactName       | Address                | City      | PostalCode | Country |
| ---------- | ---------------------- | ----------------- | ---------------------- | --------- | ---------- | ------- |
| 29         | Galería del gastrónomo | Eduardo Saavedra  | Rambla de Cataluña, 23 | Barcelona | 08022      | Spain   |
| 30         | Godos Cocina Típica    | José Pedro Freyre | C/ Romero, 33          | Sevilla   | 41101      | Spain   |
| 69         | Romero y tomillo       | Alejandra Camino  | Gran Vía, 1            | Madrid    | 28001      | Spain   |

Without paranthesis, the SQL above will return all customers from Spain that starts with a "G", plus all customers that starts with an "R" regardless of the country value:

## Example:
```sql
SELECT * FROM Customers
WHERE Country = 'Spain'
AND CustomerName LIKE 'G%' OR CustomerName LIKE 'R%';
```

| CustomerID | CustomerName               | ContactName       | Address                | City           | PostalCode | Country     |
| ---------- | -------------------------- | ----------------- | ---------------------- | -------------- | ---------- | ----------- |
| 29         | Galería del gastrónomo     | Eduardo Saavedra  | Rambla de Cataluña, 23 | Barcelona      | 08022      | Spain       |
| 30         | Godos Cocina Típica        | José Pedro Freyre | C/ Romero, 33          | Sevilla        | 41101      | Spain       |
| 64         | Rancho grande              | Sergio Gutiérrez  | Av. del Libertador 900 | Buenos Aires   | 1010       | Argentina   |
| 65         | Rattlesnake Canyon Grocery | Paula Wilson      | 2817 Milton Dr.        | Albuquerque    | 87110      | USA         |
| 66         | Reggiani Caseifici         | Maurizio Moroni   | Strada Provinciale 124 | Reggio Emilia  | 42100      | Italy       |
| 67         | Ricardo Adocicados         | Janete Limeira    | Av. Copacabana, 267    | Rio de Janeiro | 02389-890  | Brazil      |
| 68         | Richter Supermarkt         | Michael Holz      | Grenzacherweg 237      | Genève         | 1203       | Switzerland |
| 69         | Romero y tomillo           | Alejandra Camino  | Gran Vía, 1            | Madrid         | 28001      | Spain       |


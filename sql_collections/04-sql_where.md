# SQL WHERE Clause
The WHERE clause is used to filter records.
The WHERE clause is used to extract only those records that fulfill a specific condition.

## Example:
Here we select all customers from Mexico:
```sql
SELECT * FROM Customers
WHERE Country='Mexico';
```

| CustomerID | CustomerName                       | ContactName          | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | -------------------- | ----------------------------- | ----------- | ---------- | ------- |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo         | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno       | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 13         | Centro comercial Moctezuma         | Francisco Chang      | Sierras de Granada 9993       | México D.F. | 05022      | Mexico  |
| 58         | Pericles Comidas clásicas          | Guillermo Fernández  | Calle Dr. Jorge Cash 321      | México D.F. | 05033      | Mexico  |
| 80         | Tortuga Restaurante                | Miguel Angel Paolino | Avda. Azteca 123              | México D.F. | 05033      | Mexico  |

## Syntax
```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition;
```

Note: The WHERE clause is not only used in SELECT statements, it is also used in UPDATE, DELETE etc.

## Demo Database
Below is a selection from the Customers table used in the examples:

| CustomerID | CustomerName                       | ContactName        | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | ------------------ | ----------------------------- | ----------- | ---------- | ------- |
| 1<br><br>  | Alfreds Futterkiste                | Maria Anders       | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo       | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno     | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 4<br><br>  | Around the Horn                    | Thomas Hardy       | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                 | Christina Berglund | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |

## Text Fields vs Numeric Fields
SQL requires single quotes around text values (most database systems will also follow double quotes).
However, numeric fields should not be enclosed in quotes:

## Example:
```sql
SELECT * FROM Customers
WHERE CustomerID=1;
```

| CustomerID | CustomerName        | ContactName  | Address       | City   | PostalCode | Country |
| ---------- | ------------------- | ------------ | ------------- | ------ | ---------- | ------- |
| 1          | Alfreds Futterkiste | Maria Anders | Obere Str. 57 | Berlin | 12209      | Germany |

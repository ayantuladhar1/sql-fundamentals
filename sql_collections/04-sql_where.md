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

## Operators in the WHERE Clause
You can use other operators than the = operator to filter the search.

## Example:
Select all customers with a CustomerID greater than 80:
```sql
SELECT * FROM Customers
WHERE CustomerID > 80;
```

| CustomerID | CustomerName                     | ContactName       | Address                     | City      | PostalCode | Country |
| ---------- | -------------------------------- | ----------------- | --------------------------- | --------- | ---------- | ------- |
| 81         | Tradição Hipermercados           | Anabela Domingues | Av. Inês de Castro, 414     | São Paulo | 05634-030  | Brazil  |
| 82         | Trails Head Gourmet Provisioners | Helvetius Nagy    | 722 DaVinci Blvd.           | Kirkland  | 98034      | USA     |
| 83         | Vaffeljernet                     | Palle Ibsen       | Smagsløget 45               | Århus     | 8200       | Denmark |
| 84         | Victuailles en stock             | Mary Saveley      | 2, rue du Commerce          | Lyon      | 69004      | France  |
| 85         | Vins et alcools Chevalier        | Paul Henriot      | 59 rue de lAbbaye           | Reims     | 51100      | France  |
| 86         | Die Wandernde Kuh                | Rita Müller       | Adenauerallee 900           | Stuttgart | 70563      | Germany |
| 87         | Wartian Herkku                   | Pirkko Koskitalo  | Torikatu 38                 | Oulu      | 90110      | Finland |
| 88         | Wellington Importadora           | Paula Parente     | Rua do Mercado, 12          | Resende   | 08737-363  | Brazil  |
| 89         | White Clover Markets             | Karl Jablonski    | 305 - 14th Ave. S. Suite 3B | Seattle   | 98128      | USA     |
| 90         | Wilman Kala                      | Matti Karttunen   | Keskuskatu 45               | Helsinki  | 21240      | Finland |
| 91         | Wolski                           | Zbyszek           | ul. Filtrowa 68             | Walla     | 01-012     | Poland  |

The following operators can be used in the WHERE clause:

|Operator | Description                                                                 |
| ------- | --------------------------------------------------------------------------- | 
| \=      | Equal                                                                       | 
| \>      | Greater than                                                                | 
| <       | Less than                                                                   | 
| \>=     | Greater than or equal                                                       | 
| <=      | Less than or equal                                                          | 
| <>      | Not equal. Note: In some versions of SQL this operator may be written as != | 
| BETWEEN | Between a certain range                                                     | 
| LIKE    | Search for a pattern                                                        | 
| IN      | To specify multiple possible values for a column                            |


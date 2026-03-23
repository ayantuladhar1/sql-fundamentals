# SQL Aliases
SQL aliases are used to give a column or a table a temporary name.
Aliases are used to make column names more readable.
An alias only exists for the duration of that query.
An alias is created with the AS keyword.

## Alias for Columns
The following SQL creates two aliases, one for the CustomerID column and one for the CustomerName column:

## Example:
```sql
SELECT CustomerID AS ID, CustomerName AS Customer
FROM Customers;
```

| ID | Customer                             |
| -- | ------------------------------------ |
| 1  | Alfreds Futterkiste                  |
| 2  | Ana Trujillo Emparedados y helados   |
| 3  | Antonio Moreno Taquería              |
| 4  | Around the Horn                      |
| 5  | Berglunds snabbköp                   |
| 6  | Blauer See Delikatessen              |
| 7  | Blondel père et fils                 |
| 8  | Bólido Comidas preparadas            |
| 9  | Bon app                              |
| 10 | Bottom-Dollar Marketse               |
| 11 | Bs Beverages                         |
| 12 | Cactus Comidas para llevar           |
| 13 | Centro comercial Moctezuma           |
| 14 | Chop-suey Chinese                    |
| 15 | Comércio Mineiro                     |
| 16 | Consolidated Holdings                |
| 17 | Drachenblut Delikatessend            |
| 18 | Du monde entier                      |
| 19 | Eastern Connection                   |
| 20 | Ernst Handel                         |
| 21 | Familia Arquibaldo                   |
| 22 | FISSA Fabrica Inter. Salchichas S.A. |
| 23 | Folies gourmandes                    |
| 24 | Folk och fä HB                       |
| 25 | Frankenversand                       |
| 26 | France restauration                  |
| 27 | Franchi S.p.A.                       |
| 28 | Furia Bacalhau e Frutos do Mar       |
| 29 | Galería del gastrónomo               |
| 30 | Godos Cocina Típica                  |
| 31 | Gourmet Lanchonetes                  |
| 32 | Great Lakes Food Market              |
| 33 | GROSELLA-Restaurante                 |
| 34 | Hanari Carnes                        |
| 35 | HILARIÓN-Abastos                     |
| 36 | Hungry Coyote Import Store           |
| 37 | Hungry Owl All-Night Grocers         |
| 38 | Island Trading                       |
| 39 | Königlich Essen                      |
| 40 | La corne dabondance                  |
| 41 | La maison dAsie                      |
| 42 | Laughing Bacchus Wine Cellars        |
| 43 | Lazy K Kountry Store                 |
| 44 | Lehmanns Marktstand                  |
| 45 | Lets Stop N Shop                     |
| 46 | LILA-Supermercado                    |
| 47 | LINO-Delicateses                     |
| 48 | Lonesome Pine Restaurant             |
| 49 | Magazzini Alimentari Riuniti         |
| 50 | Maison Dewey                         |
| 51 | Mère Paillarde                       |
| 52 | Morgenstern Gesundkost               |
| 53 | North/South                          |
| 54 | Océano Atlántico Ltda.               |
| 55 | Old World Delicatessen               |
| 56 | Ottilies Käseladen                   |
| 57 | Paris spécialités                    |
| 58 | Pericles Comidas clásicas            |
| 59 | Piccolo und mehr                     |
| 60 | Princesa Isabel Vinhoss              |
| 61 | Que Delícia                          |
| 62 | Queen Cozinha                        |
| 63 | QUICK-Stop                           |
| 64 | Rancho grande                        |
| 65 | Rattlesnake Canyon Grocery           |
| 66 | Reggiani Caseifici                   |
| 67 | Ricardo Adocicados                   |
| 68 | Richter Supermarkt                   |
| 69 | Romero y tomillo                     |
| 70 | Santé Gourmet                        |
| 71 | Save-a-lot Markets                   |
| 72 | Seven Seas Imports                   |
| 73 | Simons bistro                        |
| 74 | Spécialités du monde                 |
| 75 | Split Rail Beer & Ale                |
| 76 | Suprêmes délices                     |
| 77 | The Big Cheese                       |
| 78 | The Cracker Box                      |
| 79 | Toms Spezialitäten                   |
| 80 | Tortuga Restaurante                  |
| 81 | Tradição Hipermercados               |
| 82 | Trails Head Gourmet Provisioners     |
| 83 | Vaffeljernet                         |
| 84 | Victuailles en stock                 |
| 85 | Vins et alcools Chevalier            |
| 86 | Die Wandernde Kuh                    |
| 87 | Wartian Herkku                       |
| 88 | Wellington Importadora               |
| 89 | White Clover Markets                 |
| 90 | Wilman Kala                          |
| 91 | Wolski                               |

## Syntax
Alias for column:
```sql
SELECT column_name AS alias_name
FROM table_name;
```

Alias for table:
```sql
SELECT column_name(s)
FROM table_name AS alias_name;
```

## Demo Database
Below is a selection from the Customers and Orders tables used in the examples:

## Customers
| CustomerID | CustomerName                       | ContactName    | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | -------------- | ----------------------------- | ----------- | ---------- | ------- |
| 1          | Alfreds Futterkiste                | Maria Anders   | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo   | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno | Mataderos 2312                | México D.F. | 05023      | Mexico  |

## Orders
| OrderID | CustomerID | EmployeeID | OrderDate  | ShipperID |
| ------- | ---------- | ---------- | ---------- | --------- |
| 10248   | 90         | 5          | 1996-07-04 | 3         |
| 10249   | 81         | 6          | 1996-07-05 | 1         |
| 10250   | 34         | 4          | 1996-07-08 | 2         |

## Aliases with Spaces
If you want your alias to contain one or more spaces, like "My Great Prducts", surround the aliasname with square brackets or double quotes:

## Example:
Using [square brackets] for aliases with space characters:
```sql
SELECT ProductName AS [My Great Products]
FROM Products;
```

| My Great Products                |
| -------------------------------- |
| Chais                            |
| Chang                            |
| Aniseed Syrup                    |
| Chef Antons Cajun Seasoning      |
| Chef Antons Gumbo Mix            |
| Grandmas Boysenberry Spread      |
| Uncle Bobs Organic Dried Pears   |
| Northwoods Cranberry Sauce       |
| Mishi Kobe Niku                  |
| Ikura                            |
| Queso Cabrales                   |
| Queso Manchego La Pastora        |
| Konbu                            |
| Tofu                             |
| Genen Shouyu                     |
| Pavlova                          |
| Alice Mutton                     |
| Carnarvon Tigers                 |
| Teatime Chocolate Biscuits       |
| Sir Rodneys Marmalade            |
| Sir Rodneys Scones               |
| Gustafs Knäckebröd               |
| Tunnbröd                         |
| Guaraná Fantástica               |
| NuNuCa Nuß-Nougat-Creme          |
| Gumbär Gummibärchen              |
| Schoggi Schokolade               |
| Rössle Sauerkraut                |
| Thüringer Rostbratwurst          |
| Nord-Ost Matjeshering            |
| Gorgonzola Telino                |
| Mascarpone Fabioli               |
| Geitost                          |
| Sasquatch Ale                    |
| Steeleye Stout                   |
| Inlagd Sill                      |
| Gravad lax                       |
| Côte de Blaye                    |
| Chartreuse verte                 |
| Boston Crab Meat                 |
| Jacks New England Clam Chowder   |
| Singaporean Hokkien Fried Mee    |
| Ipoh Coffee                      |
| Gula Malacca                     |
| Røgede sild                      |
| Spegesild                        |
| Zaanse koeken                    |
| Chocolade                        |
| Maxilaku                         |
| Valkoinen suklaa                 |
| Manjimup Dried Apples            |
| Filo Mix                         |
| Perth Pasties                    |
| Tourtière                        |
| Pâté chinois                     |
| Gnocchi di nonna Alice           |
| Ravioli Angelo                   |
| Escargots de Bourgogne           |
| Raclette Courdavault             |
| Camembert Pierrot                |
| Sirop dérable                    |
| Tarte au sucre                   |
| Vegie-spread                     |
| Wimmers gute Semmelknödel        |
| Louisiana Fiery Hot Pepper Sauce |
| Louisiana Hot Spiced Okra        |
| Laughing Lumberjack Lager        |
| Scottish Longbreads              |
| Gudbrandsdalsost                 |
| Outback Lager                    |
| Fløtemysost                      |
| Mozzarella di Giovanni           |
| Röd Kaviar                       |
| Longlife Tofu                    |
| Rhönbräu Klosterbier             |
| Lakkalikööri                     |
| Original Frankfurter grüne Soße  |

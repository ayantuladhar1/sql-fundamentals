# SQL BETWEEN Operator
The BETWEEN operator is used in the WHERE clause to select values within a specified range.

The range is inclusive - the beginning and end values of the range are included in the results.

The values can be numbers, text or dates.

## Example:
Select all products with a price between 10 and 20:
```sql
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20;
```

| ProductID | ProductName                     | SupplierID | CategoryID | Unit                | Price |
| --------- | ------------------------------- | ---------- | ---------- | ------------------- | ----- |
| 1         | Chais                           | 1          | 1          | 10 boxes x 20 bags  | 18.00 |
| 2         | Chang                           | 1          | 1          | 24 - 12 oz bottles  | 19.00 |
| 3         | Aniseed Syrup                   | 1          | 2          | 12 - 550 ml bottles | 10.00 |
| 15        | Genen Shouyu                    | 6          | 2          | 24 - 250 ml bottles | 15.50 |
| 16        | Pavlova                         | 7          | 3          | 32 - 500 g boxes    | 17.45 |
| 21        | Sir Rodneys Scones              | 8          | 3          | 24 pkgs. x 4 pieces | 10.00 |
| 25        | NuNuCa Nuß-Nougat-Creme         | 11         | 3          | 20 - 450 g glasses  | 14.00 |
| 31        | Gorgonzola Telino               | 14         | 4          | 12 - 100 g pkgs     | 12.50 |
| 34        | Sasquatch Ale                   | 16         | 1          | 24 - 12 oz bottles  | 14.00 |
| 35        | Steeleye Stout                  | 16         | 1          | 24 - 12 oz bottles  | 18.00 |
| 36        | Inlagd Sill                     | 17         | 8          | 24 - 250 g jars     | 19.00 |
| 39        | Chartreuse verte                | 18         | 1          | 750 cc per bottle   | 18.00 |
| 40        | Boston Crab Meat                | 19         | 8          | 24 - 4 oz tins      | 18.40 |
| 42        | Singaporean Hokkien Fried Mee   | 20         | 5          | 32 - 1 kg pkgs.     | 14.00 |
| 44        | Gula Malacca                    | 20         | 2          | 20 - 2 kg bags      | 19.45 |
| 46        | Spegesild                       | 21         | 8          | 4 - 450 g glasses   | 12.00 |
| 48        | Chocolade                       | 22         | 3          | 10 pkgs.            | 12.75 |
| 49        | Maxilaku                        | 23         | 3          | 24 - 50 g pkgs.     | 20.00 |
| 50        | Valkoinen suklaa                | 23         | 3          | 12 - 100 g bars     | 16.25 |
| 57        | Ravioli Angelo                  | 26         | 5          | 24 - 250 g pkgs.    | 19.50 |
| 58        | Escargots de Bourgogne          | 27         | 8          | 24 pieces           | 13.25 |
| 66        | Louisiana Hot Spiced Okra       | 2          | 2          | 24 - 8 oz jars      | 17.00 |
| 67        | Laughing Lumberjack Lager       | 16         | 1          | 24 - 12 oz bottles  | 14.00 |
| 68        | Scottish Longbreads             | 8          | 3          | 10 boxes x 8 pieces | 12.50 |
| 70        | Outback Lager                   | 7          | 1          | 24 - 355 ml bottles | 15.00 |
| 73        | Röd Kaviar                      | 17         | 8          | 24 - 150 g jars     | 15.00 |
| 74        | Longlife Tofu                   | 4          | 7          | 5 kg pkg.           | 10.00 |
| 76        | Lakkalikööri                    | 23         | 1          | 500 ml              | 18.00 |
| 77        | Original Frankfurter grüne Soße | 12         | 2          | 12 boxes            | 13.00 |

## Syntax
```sql
SELECT column_name(s)
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

## Demo Database
Below is a selection from the Products table used in the examples:

| ProductID | ProductName                  | SupplierID | CategoryID | Unit                | Price |
| --------- | ---------------------------- | ---------- | ---------- | ------------------- | ----- |
| 1         | Chais                        | 1          | 1          | 10 boxes x 20 bags  | 18.00 |
| 2         | Chang                        | 1          | 1          | 24 - 12 oz bottles  | 19.00 |
| 3         | Aniseed Syrup                | 1          | 2          | 12 - 550 ml bottles | 10.00 |
| 4         | Chef Anton's Cajun Seasoning | 2          | 2          | 48 - 6 oz jars      | 22.00 |
| 5         | Chef Anton's Gumbo Mix       | 2          | 2          | 36 boxes            | 21.35 |

## NOT BETWEEN
The NOT BETWEEN operator is used in the WHERE clause to select values outside a specified range.

The following SQL returns all products with a price NOT between 10 and 20:

## Example:
```sql
SELECT * FROM Products
WHERE Price NOT BETWEEN 10 AND 20;
```

| ProductID | ProductName                      | SupplierID | CategoryID | Unit                 | Price  |
| --------- | -------------------------------- | ---------- | ---------- | -------------------- | ------ |
| 4         | Chef Antons Cajun Seasoning      | 2          | 2          | 48 - 6 oz jars       | 22.00  |
| 5         | Chef Antons Gumbo Mix            | 2          | 2          | 36 boxes             | 21.35  |
| 6         | Grandmas Boysenberry Spread      | 3          | 2          | 12 - 8 oz jars       | 25.00  |
| 7         | Uncle Bobs Organic Dried Pears   | 3          | 7          | 12 - 1 lb pkgs.      | 30.00  |
| 8         | Northwoods Cranberry Sauce       | 3          | 2          | 12 - 12 oz jars      | 40.00  |
| 9         | Mishi Kobe Niku                  | 4          | 6          | 18 - 500 g pkgs.     | 97.00  |
| 10        | Ikura                            | 4          | 8          | 12 - 200 ml jars     | 31.00  |
| 11        | Queso Cabrales                   | 5          | 4          | 1 kg pkg.            | 21.00  |
| 12        | Queso Manchego La Pastora        | 5          | 4          | 10 - 500 g pkgs.     | 38.00  |
| 13        | Konbu                            | 6          | 8          | 2 kg box             | 6.00   |
| 14        | Tofu                             | 6          | 7          | 40 - 100 g pkgs.     | 23.25  |
| 17        | Alice Mutton                     | 7          | 6          | 20 - 1 kg tins       | 39.00  |
| 18        | Carnarvon Tigers                 | 7          | 8          | 16 kg pkg.           | 62.50  |
| 19        | Teatime Chocolate Biscuits       | 8          | 3          | 10 boxes x 12 pieces | 9.20   |
| 20        | Sir Rodneys Marmalade            | 8          | 3          | 30 gift boxes        | 81.00  |
| 22        | Gustafs Knäckebröd               | 9          | 5          | 24 - 500 g pkgs.     | 21.00  |
| 23        | Tunnbröd                         | 9          | 5          | 12 - 250 g pkgs.     | 9.00   |
| 24        | Guaraná Fantástica               | 10         | 1          | 12 - 355 ml cans     | 4.50   |
| 26        | Gumbär Gummibärchen              | 11         | 3          | 100 - 250 g bags     | 31.23  |
| 27        | Schoggi Schokolade               | 11         | 3          | 100 - 100 g pieces   | 43.90  |
| 28        | Rössle Sauerkraut                | 12         | 7          | 25 - 825 g cans      | 45.60  |
| 29        | Thüringer Rostbratwurst          | 12         | 6          | 50 bags x 30 sausgs. | 123.79 |
| 30        | Nord-Ost Matjeshering            | 13         | 8          | 10 - 200 g glasses   | 25.89  |
| 32        | Mascarpone Fabioli               | 14         | 4          | 24 - 200 g pkgs.     | 32.00  |
| 33        | Geitost                          | 15         | 4          | 500 g                | 2.50   |
| 37        | Gravad lax                       | 17         | 8          | 12 - 500 g pkgs.     | 26.00  |
| 38        | Côte de Blaye                    | 18         | 1          | 12 - 75 cl bottles   | 263.50 |
| 41        | Jacks New England Clam Chowder   | 19         | 8          | 12 - 12 oz cans      | 9.65   |
| 43        | Ipoh Coffee                      | 20         | 1          | 16 - 500 g tins      | 46.00  |
| 45        | Røgede sild                      | 21         | 8          | 1k pkg.              | 9.50   |
| 47        | Zaanse koeken                    | 22         | 3          | 10 - 4 oz boxes      | 9.50   |
| 51        | Manjimup Dried Apples            | 24         | 7          | 50 - 300 g pkgs.     | 53.00  |
| 52        | Filo Mix                         | 24         | 5          | 16 - 2 kg boxes      | 7.00   |
| 53        | Perth Pasties                    | 24         | 6          | 48 pieces            | 32.80  |
| 54        | Tourtière                        | 25         | 6          | 16 pies              | 7.45   |
| 55        | Pâté chinois                     | 25         | 6          | 24 boxes x 2 pies    | 24.00  |
| 56        | Gnocchi di nonna Alice           | 26         | 5          | 24 - 250 g pkgs.     | 38.00  |
| 59        | Raclette Courdavault             | 28         | 4          | 5 kg pkg.            | 55.00  |
| 60        | Camembert Pierrot                | 28         | 4          | 15 - 300 g rounds    | 34.00  |
| 61        | Sirop dérable                    | 29         | 2          | 24 - 500 ml bottles  | 28.50  |
| 62        | Tarte au sucre                   | 29         | 3          | 48 pies              | 49.30  |
| 63        | Vegie-spread                     | 7          | 2          | 15 - 625 g jars      | 43.90  |
| 64        | Wimmers gute Semmelknödel        | 12         | 5          | 20 bags x 4 pieces   | 33.25  |
| 65        | Louisiana Fiery Hot Pepper Sauce | 2          | 2          | 32 - 8 oz bottles    | 21.05  |
| 69        | Gudbrandsdalsost                 | 15         | 4          | 10 kg pkg.           | 36.00  |
| 71        | Fløtemysost                      | 15         | 4          | 10 - 500 g pkgs.     | 21.50  |
| 72        | Mozzarella di Giovanni           | 14         | 4          | 24 - 200 g pkgs.     | 34.80  |
| 75        | Rhönbräu Klosterbier             | 12         | 1          | 24 - 0.5 l bottles   | 7.75   |

## BETWEEN with IN
The following SQL returns all products with a price between 10 and 20. In addition, the CategoryID must be either 1,2 or 3:

## Example:
```sql
SELECT * FROM Products
WHERE Price BETWEEN 10 AND 20
AND CategoryID IN (1,2,3);
```

| ProductID | ProductName                     | SupplierID | CategoryID | Unit                | Price |
| --------- | ------------------------------- | ---------- | ---------- | ------------------- | ----- |
| 1         | Chais                           | 1          | 1          | 10 boxes x 20 bags  | 18.00 |
| 2         | Chang                           | 1          | 1          | 24 - 12 oz bottles  | 19.00 |
| 3         | Aniseed Syrup                   | 1          | 2          | 12 - 550 ml bottles | 10.00 |
| 15        | Genen Shouyu                    | 6          | 2          | 24 - 250 ml bottles | 15.50 |
| 16        | Pavlova                         | 7          | 3          | 32 - 500 g boxes    | 17.45 |
| 21        | Sir Rodneys Scones              | 8          | 3          | 24 pkgs. x 4 pieces | 10.00 |
| 25        | NuNuCa Nuß-Nougat-Creme         | 11         | 3          | 20 - 450 g glasses  | 14.00 |
| 34        | Sasquatch Ale                   | 16         | 1          | 24 - 12 oz bottles  | 14.00 |
| 35        | Steeleye Stout                  | 16         | 1          | 24 - 12 oz bottles  | 18.00 |
| 39        | Chartreuse verte                | 18         | 1          | 750 cc per bottle   | 18.00 |
| 44        | Gula Malacca                    | 20         | 2          | 20 - 2 kg bags      | 19.45 |
| 48        | Chocolade                       | 22         | 3          | 10 pkgs.            | 12.75 |
| 49        | Maxilaku                        | 23         | 3          | 24 - 50 g pkgs.     | 20.00 |
| 50        | Valkoinen suklaa                | 23         | 3          | 12 - 100 g bars     | 16.25 |
| 66        | Louisiana Hot Spiced Okra       | 2          | 2          | 24 - 8 oz jars      | 17.00 |
| 67        | Laughing Lumberjack Lager       | 16         | 1          | 24 - 12 oz bottles  | 14.00 |
| 68        | Scottish Longbreads             | 8          | 3          | 10 boxes x 8 pieces | 12.50 |
| 70        | Outback Lager                   | 7          | 1          | 24 - 355 ml bottles | 15.00 |
| 76        | Lakkalikööri                    | 23         | 1          | 500 ml              | 18.00 |
| 77        | Original Frankfurter grüne Soße | 12         | 2          | 12 boxes            | 13.00 |

## BETWEEN Text Values
The following SQL selects all products with a ProductName alphabetically between 'Geitost' and 'Louisiana Hot Spiced Okra':

## Example:
```sql
SELECT * FROM Products
WHERE ProductName BETWEEN 'Geitost' AND 'Louisiana Hot Spiced Okra'
ORDER BY ProductName;
```

| ProductID | ProductName                      | SupplierID | CategoryID | Unit                | Price |
| --------- | -------------------------------- | ---------- | ---------- | ------------------- | ----- |
| 33        | Geitost                          | 15         | 4          | 500 g               | 2.50  |
| 15        | Genen Shouyu                     | 6          | 2          | 24 - 250 ml bottles | 15.50 |
| 56        | Gnocchi di nonna Alice           | 26         | 5          | 24 - 250 g pkgs.    | 38.00 |
| 31        | Gorgonzola Telino                | 14         | 4          | 12 - 100 g pkgs     | 12.50 |
| 6         | Grandmas Boysenberry Spread      | 3          | 2          | 12 - 8 oz jars      | 25.00 |
| 37        | Gravad lax                       | 17         | 8          | 12 - 500 g pkgs.    | 26.00 |
| 24        | Guaraná Fantástica               | 10         | 1          | 12 - 355 ml cans    | 4.50  |
| 69        | Gudbrandsdalsost                 | 15         | 4          | 10 kg pkg.          | 36.00 |
| 44        | Gula Malacca                     | 20         | 2          | 20 - 2 kg bags      | 19.45 |
| 26        | Gumbär Gummibärchen              | 11         | 3          | 100 - 250 g bags    | 31.23 |
| 22        | Gustafs Knäckebröd               | 9          | 5          | 24 - 500 g pkgs.    | 21.00 |
| 10        | Ikura                            | 4          | 8          | 12 - 200 ml jars    | 31.00 |
| 36        | Inlagd Sill                      | 17         | 8          | 24 - 250 g jars     | 19.00 |
| 43        | Ipoh Coffee                      | 20         | 1          | 16 - 500 g tins     | 46.00 |
| 41        | Jacks New England Clam Chowder   | 19         | 8          | 12 - 12 oz cans     | 9.65  |
| 13        | Konbu                            | 6          | 8          | 2 kg box            | 6.00  |
| 76        | Lakkalikööri                     | 23         | 1          | 500 ml              | 18.00 |
| 67        | Laughing Lumberjack Lager        | 16         | 1          | 24 - 12 oz bottles  | 14.00 |
| 74        | Longlife Tofu                    | 4          | 7          | 5 kg pkg.           | 10.00 |
| 65        | Louisiana Fiery Hot Pepper Sauce | 2          | 2          | 32 - 8 oz bottles   | 21.05 |
| 66        | Louisiana Hot Spiced Okra        | 2          | 2          | 24 - 8 oz jars      | 17.00 |

## NOT BETWEEN Text Values
The following SQL selects all products with a ProductName NOT between 'Geitost' and 'Louisiana Hot Spiced Okra':

## Example:
```sql
SELECT * FROM Products
WHERE ProductName NOT BETWEEN 'Geitost' AND 'Louisiana Hot Spiced Okra'
ORDER BY ProductName;
```

| ProductID | ProductName                     | SupplierID | CategoryID | Unit                 | Price  |
| --------- | ------------------------------- | ---------- | ---------- | -------------------- | ------ |
| 17        | Alice Mutton                    | 7          | 6          | 20 - 1 kg tins       | 39.00  |
| 3         | Aniseed Syrup                   | 1          | 2          | 12 - 550 ml bottles  | 10.00  |
| 40        | Boston Crab Meat                | 19         | 8          | 24 - 4 oz tins       | 18.40  |
| 60        | Camembert Pierrot               | 28         | 4          | 15 - 300 g rounds    | 34.00  |
| 18        | Carnarvon Tigers                | 7          | 8          | 16 kg pkg.           | 62.50  |
| 1         | Chais                           | 1          | 1          | 10 boxes x 20 bags   | 18.00  |
| 2         | Chang                           | 1          | 1          | 24 - 12 oz bottles   | 19.00  |
| 39        | Chartreuse verte                | 18         | 1          | 750 cc per bottle    | 18.00  |
| 4         | Chef Antons Cajun Seasoning     | 2          | 2          | 48 - 6 oz jars       | 22.00  |
| 5         | Chef Antons Gumbo Mix           | 2          | 2          | 36 boxes             | 21.35  |
| 48        | Chocolade                       | 22         | 3          | 10 pkgs.             | 12.75  |
| 38        | Côte de Blaye                   | 18         | 1          | 12 - 75 cl bottles   | 263.50 |
| 58        | Escargots de Bourgogne          | 27         | 8          | 24 pieces            | 13.25  |
| 52        | Filo Mix                        | 24         | 5          | 16 - 2 kg boxes      | 7.00   |
| 71        | Fløtemysost                     | 15         | 4          | 10 - 500 g pkgs.     | 21.50  |
| 51        | Manjimup Dried Apples           | 24         | 7          | 50 - 300 g pkgs.     | 53.00  |
| 32        | Mascarpone Fabioli              | 14         | 4          | 24 - 200 g pkgs.     | 32.00  |
| 49        | Maxilaku                        | 23         | 3          | 24 - 50 g pkgs.      | 20.00  |
| 9         | Mishi Kobe Niku                 | 4          | 6          | 18 - 500 g pkgs.     | 97.00  |
| 72        | Mozzarella di Giovanni          | 14         | 4          | 24 - 200 g pkgs.     | 34.80  |
| 30        | Nord-Ost Matjeshering           | 13         | 8          | 10 - 200 g glasses   | 25.89  |
| 8         | Northwoods Cranberry Sauce      | 3          | 2          | 12 - 12 oz jars      | 40.00  |
| 25        | NuNuCa Nuß-Nougat-Creme         | 11         | 3          | 20 - 450 g glasses   | 14.00  |
| 77        | Original Frankfurter grüne Soße | 12         | 2          | 12 boxes             | 13.00  |
| 70        | Outback Lager                   | 7          | 1          | 24 - 355 ml bottles  | 15.00  |
| 55        | Pâté chinois                    | 25         | 6          | 24 boxes x 2 pies    | 24.00  |
| 16        | Pavlova                         | 7          | 3          | 32 - 500 g boxes     | 17.45  |
| 53        | Perth Pasties                   | 24         | 6          | 48 pieces            | 32.80  |
| 11        | Queso Cabrales                  | 5          | 4          | 1 kg pkg.            | 21.00  |
| 12        | Queso Manchego La Pastora       | 5          | 4          | 10 - 500 g pkgs.     | 38.00  |
| 59        | Raclette Courdavault            | 28         | 4          | 5 kg pkg.            | 55.00  |
| 57        | Ravioli Angelo                  | 26         | 5          | 24 - 250 g pkgs.     | 19.50  |
| 75        | Rhönbräu Klosterbier            | 12         | 1          | 24 - 0.5 l bottles   | 7.75   |
| 73        | Röd Kaviar                      | 17         | 8          | 24 - 150 g jars      | 15.00  |
| 45        | Røgede sild                     | 21         | 8          | 1k pkg.              | 9.50   |
| 28        | Rössle Sauerkraut               | 12         | 7          | 25 - 825 g cans      | 45.60  |
| 34        | Sasquatch Ale                   | 16         | 1          | 24 - 12 oz bottles   | 14.00  |
| 27        | Schoggi Schokolade              | 11         | 3          | 100 - 100 g pieces   | 43.90  |
| 68        | Scottish Longbreads             | 8          | 3          | 10 boxes x 8 pieces  | 12.50  |
| 42        | Singaporean Hokkien Fried Mee   | 20         | 5          | 32 - 1 kg pkgs.      | 14.00  |
| 20        | Sir Rodneys Marmalade           | 8          | 3          | 30 gift boxes        | 81.00  |
| 21        | Sir Rodneys Scones              | 8          | 3          | 24 pkgs. x 4 pieces  | 10.00  |
| 61        | Sirop dérable                   | 29         | 2          | 24 - 500 ml bottles  | 28.50  |
| 46        | Spegesild                       | 21         | 8          | 4 - 450 g glasses    | 12.00  |
| 35        | Steeleye Stout                  | 16         | 1          | 24 - 12 oz bottles   | 18.00  |
| 62        | Tarte au sucre                  | 29         | 3          | 48 pies              | 49.30  |
| 19        | Teatime Chocolate Biscuits      | 8          | 3          | 10 boxes x 12 pieces | 9.20   |
| 29        | Thüringer Rostbratwurst         | 12         | 6          | 50 bags x 30 sausgs. | 123.79 |
| 14        | Tofu                            | 6          | 7          | 40 - 100 g pkgs.     | 23.25  |
| 54        | Tourtière                       | 25         | 6          | 16 pies              | 7.45   |
| 23        | Tunnbröd                        | 9          | 5          | 12 - 250 g pkgs.     | 9.00   |
| 7         | Uncle Bobs Organic Dried Pears  | 3          | 7          | 12 - 1 lb pkgs.      | 30.00  |
| 50        | Valkoinen suklaa                | 23         | 3          | 12 - 100 g bars      | 16.25  |
| 63        | Vegie-spread                    | 7          | 2          | 15 - 625 g jars      | 43.90  |
| 64        | Wimmers gute Semmelknödel       | 12         | 5          | 20 bags x 4 pieces   | 33.25  |
| 47        | Zaanse koeken                   | 22         | 3          | 10 - 4 oz boxes      | 9.50   |

## NOT BETWEEN Text Values
The following SQL selects all products with a ProdcuctName NOT between 'Geitost' and 'Louisiana Hot Spiced Okra':

## Example:
```sql
SELECT * FROM Products
WHERE ProductName NOT BETWEEN 'Geitost' AND 'Louisiana Hot Spiced Okra'
ORDER BY ProductName;
```

| ProductID | ProductName                     | SupplierID | CategoryID | Unit                 | Price  |
| --------- | ------------------------------- | ---------- | ---------- | -------------------- | ------ |
| 17        | Alice Mutton                    | 7          | 6          | 20 - 1 kg tins       | 39.00  |
| 3         | Aniseed Syrup                   | 1          | 2          | 12 - 550 ml bottles  | 10.00  |
| 40        | Boston Crab Meat                | 19         | 8          | 24 - 4 oz tins       | 18.40  |
| 60        | Camembert Pierrot               | 28         | 4          | 15 - 300 g rounds    | 34.00  |
| 18        | Carnarvon Tigers                | 7          | 8          | 16 kg pkg.           | 62.50  |
| 1         | Chais                           | 1          | 1          | 10 boxes x 20 bags   | 18.00  |
| 2         | Chang                           | 1          | 1          | 24 - 12 oz bottles   | 19.00  |
| 39        | Chartreuse verte                | 18         | 1          | 750 cc per bottle    | 18.00  |
| 4         | Chef Antons Cajun Seasoning     | 2          | 2          | 48 - 6 oz jars       | 22.00  |
| 5         | Chef Antons Gumbo Mix           | 2          | 2          | 36 boxes             | 21.35  |
| 48        | Chocolade                       | 22         | 3          | 10 pkgs.             | 12.75  |
| 38        | Côte de Blaye                   | 18         | 1          | 12 - 75 cl bottles   | 263.50 |
| 58        | Escargots de Bourgogne          | 27         | 8          | 24 pieces            | 13.25  |
| 52        | Filo Mix                        | 24         | 5          | 16 - 2 kg boxes      | 7.00   |
| 71        | Fløtemysost                     | 15         | 4          | 10 - 500 g pkgs.     | 21.50  |
| 51        | Manjimup Dried Apples           | 24         | 7          | 50 - 300 g pkgs.     | 53.00  |
| 32        | Mascarpone Fabioli              | 14         | 4          | 24 - 200 g pkgs.     | 32.00  |
| 49        | Maxilaku                        | 23         | 3          | 24 - 50 g pkgs.      | 20.00  |
| 9         | Mishi Kobe Niku                 | 4          | 6          | 18 - 500 g pkgs.     | 97.00  |
| 72        | Mozzarella di Giovanni          | 14         | 4          | 24 - 200 g pkgs.     | 34.80  |
| 30        | Nord-Ost Matjeshering           | 13         | 8          | 10 - 200 g glasses   | 25.89  |
| 8         | Northwoods Cranberry Sauce      | 3          | 2          | 12 - 12 oz jars      | 40.00  |
| 25        | NuNuCa Nuß-Nougat-Creme         | 11         | 3          | 20 - 450 g glasses   | 14.00  |
| 77        | Original Frankfurter grüne Soße | 12         | 2          | 12 boxes             | 13.00  |
| 70        | Outback Lager                   | 7          | 1          | 24 - 355 ml bottles  | 15.00  |
| 55        | Pâté chinois                    | 25         | 6          | 24 boxes x 2 pies    | 24.00  |
| 16        | Pavlova                         | 7          | 3          | 32 - 500 g boxes     | 17.45  |
| 53        | Perth Pasties                   | 24         | 6          | 48 pieces            | 32.80  |
| 11        | Queso Cabrales                  | 5          | 4          | 1 kg pkg.            | 21.00  |
| 12        | Queso Manchego La Pastora       | 5          | 4          | 10 - 500 g pkgs.     | 38.00  |
| 59        | Raclette Courdavault            | 28         | 4          | 5 kg pkg.            | 55.00  |
| 57        | Ravioli Angelo                  | 26         | 5          | 24 - 250 g pkgs.     | 19.50  |
| 75        | Rhönbräu Klosterbier            | 12         | 1          | 24 - 0.5 l bottles   | 7.75   |
| 73        | Röd Kaviar                      | 17         | 8          | 24 - 150 g jars      | 15.00  |
| 45        | Røgede sild                     | 21         | 8          | 1k pkg.              | 9.50   |
| 28        | Rössle Sauerkraut               | 12         | 7          | 25 - 825 g cans      | 45.60  |
| 34        | Sasquatch Ale                   | 16         | 1          | 24 - 12 oz bottles   | 14.00  |
| 27        | Schoggi Schokolade              | 11         | 3          | 100 - 100 g pieces   | 43.90  |
| 68        | Scottish Longbreads             | 8          | 3          | 10 boxes x 8 pieces  | 12.50  |
| 42        | Singaporean Hokkien Fried Mee   | 20         | 5          | 32 - 1 kg pkgs.      | 14.00  |
| 20        | Sir Rodneys Marmalade           | 8          | 3          | 30 gift boxes        | 81.00  |
| 21        | Sir Rodneys Scones              | 8          | 3          | 24 pkgs. x 4 pieces  | 10.00  |
| 61        | Sirop dérable                   | 29         | 2          | 24 - 500 ml bottles  | 28.50  |
| 46        | Spegesild                       | 21         | 8          | 4 - 450 g glasses    | 12.00  |
| 35        | Steeleye Stout                  | 16         | 1          | 24 - 12 oz bottles   | 18.00  |
| 62        | Tarte au sucre                  | 29         | 3          | 48 pies              | 49.30  |
| 19        | Teatime Chocolate Biscuits      | 8          | 3          | 10 boxes x 12 pieces | 9.20   |
| 29        | Thüringer Rostbratwurst         | 12         | 6          | 50 bags x 30 sausgs. | 123.79 |
| 14        | Tofu                            | 6          | 7          | 40 - 100 g pkgs.     | 23.25  |
| 54        | Tourtière                       | 25         | 6          | 16 pies              | 7.45   |
| 23        | Tunnbröd                        | 9          | 5          | 12 - 250 g pkgs.     | 9.00   |
| 7         | Uncle Bobs Organic Dried Pears  | 3          | 7          | 12 - 1 lb pkgs.      | 30.00  |
| 50        | Valkoinen suklaa                | 23         | 3          | 12 - 100 g bars      | 16.25  |
| 63        | Vegie-spread                    | 7          | 2          | 15 - 625 g jars      | 43.90  |
| 64        | Wimmers gute Semmelknödel       | 12         | 5          | 20 bags x 4 pieces   | 33.25  |
| 47        | Zaanse koeken                   | 22         | 3          | 10 - 4 oz boxes      | 9.50   |

## BETWEEN Dates
The BETWEEN operator is useful for filtering records within a specific date or time period. Ensure the date format matches the database (e.g. 'YYYY-MM-DD').

The following SQL selects all orders placed in July, 1996:

## Example:
```sql
SELECT * FROM Orders
WHERE OrderDate BETWEEN '1996-07-01' AND '1996-07-31';
```

| OrderID | CustomerID | EmployeeID | OrderDate  | ShipperID |
| ------- | ---------- | ---------- | ---------- | --------- |
| 10248   | 90         | 5          | 1996-07-04 | 3         |
| 10249   | 81         | 6          | 1996-07-05 | 1         |
| 10250   | 34         | 4          | 1996-07-08 | 2         |
| 10251   | 84         | 3          | 1996-07-08 | 1         |
| 10252   | 76         | 4          | 1996-07-09 | 2         |
| 10253   | 34         | 3          | 1996-07-10 | 2         |
| 10254   | 14         | 5          | 1996-07-11 | 2         |
| 10255   | 68         | 9          | 1996-07-12 | 3         |
| 10256   | 88         | 3          | 1996-07-15 | 2         |
| 10257   | 35         | 4          | 1996-07-16 | 3         |
| 10258   | 20         | 1          | 1996-07-17 | 1         |
| 10259   | 13         | 4          | 1996-07-18 | 3         |
| 10260   | 55         | 4          | 1996-07-19 | 1         |
| 10261   | 61         | 4          | 1996-07-19 | 2         |
| 10262   | 65         | 8          | 1996-07-22 | 3         |
| 10263   | 20         | 9          | 1996-07-23 | 3         |
| 10264   | 24         | 6          | 1996-07-24 | 3         |
| 10265   | 7          | 2          | 1996-07-25 | 1         |
| 10266   | 87         | 3          | 1996-07-26 | 3         |
| 10267   | 25         | 4          | 1996-07-29 | 1         |
| 10268   | 33         | 8          | 1996-07-30 | 3         |
| 10269   | 89         | 5          | 1996-07-31 | 1         |

## Sample Table
Below is a selection from the Orders table used in the example above:

| OrderID | CustomerID | EmployeeID | OrderDate  | ShipperID |
| ------- | ---------- | ---------- | ---------- | --------- |
| 10248   | 90         | 5          | 1996-07-04 | 3         |
| 10249   | 81         | 6          | 1996-07-05 | 1         |
| 10250   | 34         | 4          | 1996-07-08 | 2         |
| 10251   | 84         | 3          | 1996-07-08 | 1         |
| 10252   | 76         | 4          | 1996-07-09 | 2         |

# SQL INNER JOIN
The INNER JOIN returns only rows that have matching values in both tables.

Tip: You can use just JOIN instead of INNER JOIN, as INNER is the default join type.
<img width="265" height="180" alt="image" src="https://github.com/user-attachments/assets/6680b96f-1477-4d1b-a4df-bce3bf20a7fb" />

## INNER JOIN Syntax
```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name;
```

## INNER JOIN Example:
Look at a product in the Products table:

| ProductID | ProductName   | CategoryID | Price |
| --------- | ------------- | ---------- | ----- |
| 3         | Aniseed Syrup | 2          | 10.00 |

And look at a row in the Categories table:

| CategoryID | CategoryName | Description                                                |
| ---------- | ------------ | ---------------------------------------------------------- |
| 2          | Condiments   | Sweet and savory sauces, relishes, spreads, and seasonings |

Here we see that the relationship between the two tables above is the "CategoryID" column.

Now we create an INNER JOIN on the "Products" table and the "Categories" table, via the CategoryID field:

## Example:
Join Products and Categories with the INNER JOIN keyword:
```sql
SELECT ProductID, ProductName, CategoryName
FROM Products
INNER JOIN Categories ON Products.CategoryID = Categories.CategoryID;
```

| ProductID | ProductName                      | CategoryName   |
| --------- | -------------------------------- | -------------- |
| 1         | Chais                            | Beverages      |
| 2         | Chang                            | Beverages      |
| 3         | Aniseed Syrup                    | Condiments     |
| 4         | Chef Antons Cajun Seasoning      | Condiments     |
| 5         | Chef Antons Gumbo Mix            | Condiments     |
| 6         | Grandmas Boysenberry Spread      | Condiments     |
| 7         | Uncle Bobs Organic Dried Pears   | Produce        |
| 8         | Northwoods Cranberry Sauce       | Condiments     |
| 9         | Mishi Kobe Niku                  | Meat/Poultry   |
| 10        | Ikura                            | Seafood        |
| 11        | Queso Cabrales                   | Dairy Products |
| 12        | Queso Manchego La Pastora        | Dairy Products |
| 13        | Konbu                            | Seafood        |
| 14        | Tofu                             | Produce        |
| 15        | Genen Shouyu                     | Condiments     |
| 16        | Pavlova                          | Confections    |
| 17        | Alice Mutton                     | Meat/Poultry   |
| 18        | Carnarvon Tigers                 | Seafood        |
| 19        | Teatime Chocolate Biscuits       | Confections    |
| 20        | Sir Rodneys Marmalade            | Confections    |
| 21        | Sir Rodneys Scones               | Confections    |
| 22        | Gustafs Knäckebröd               | Grains/Cereals |
| 23        | Tunnbröd                         | Grains/Cereals |
| 24        | Guaraná Fantástica               | Beverages      |
| 25        | NuNuCa Nuß-Nougat-Creme          | Confections    |
| 26        | Gumbär Gummibärchen              | Confections    |
| 27        | Schoggi Schokolade               | Confections    |
| 28        | Rössle Sauerkraut                | Produce        |
| 29        | Thüringer Rostbratwurst          | Meat/Poultry   |
| 30        | Nord-Ost Matjeshering            | Seafood        |
| 31        | Gorgonzola Telino                | Dairy Products |
| 32        | Mascarpone Fabioli               | Dairy Products |
| 33        | Geitost                          | Dairy Products |
| 34        | Sasquatch Ale                    | Beverages      |
| 35        | Steeleye Stout                   | Beverages      |
| 36        | Inlagd Sill                      | Seafood        |
| 37        | Gravad lax                       | Seafood        |
| 38        | Côte de Blaye                    | Beverages      |
| 39        | Chartreuse verte                 | Beverages      |
| 40        | Boston Crab Meat                 | Seafood        |
| 41        | Jacks New England Clam Chowder   | Seafood        |
| 42        | Singaporean Hokkien Fried Mee    | Grains/Cereals |
| 43        | Ipoh Coffee                      | Beverages      |
| 44        | Gula Malacca                     | Condiments     |
| 45        | Røgede sild                      | Seafood        |
| 46        | Spegesild                        | Seafood        |
| 47        | Zaanse koeken                    | Confections    |
| 48        | Chocolade                        | Confections    |
| 49        | Maxilaku                         | Confections    |
| 50        | Valkoinen suklaa                 | Confections    |
| 51        | Manjimup Dried Apples            | Produce        |
| 52        | Filo Mix                         | Grains/Cereals |
| 53        | Perth Pasties                    | Meat/Poultry   |
| 54        | Tourtière                        | Meat/Poultry   |
| 55        | Pâté chinois                     | Meat/Poultry   |
| 56        | Gnocchi di nonna Alice           | Grains/Cereals |
| 57        | Ravioli Angelo                   | Grains/Cereals |
| 58        | Escargots de Bourgogne           | Seafood        |
| 59        | Raclette Courdavault             | Dairy Products |
| 60        | Camembert Pierrot                | Dairy Products |
| 61        | Sirop dérable                    | Condiments     |
| 62        | Tarte au sucre                   | Confections    |
| 63        | Vegie-spread                     | Condiments     |
| 64        | Wimmers gute Semmelknödel        | Grains/Cereals |
| 65        | Louisiana Fiery Hot Pepper Sauce | Condiments     |
| 66        | Louisiana Hot Spiced Okra        | Condiments     |
| 67        | Laughing Lumberjack Lager        | Beverages      |
| 68        | Scottish Longbreads              | Confections    |
| 69        | Gudbrandsdalsost                 | Dairy Products |
| 70        | Outback Lager                    | Beverages      |
| 71        | Fløtemysost                      | Dairy Products |
| 72        | Mozzarella di Giovanni           | Dairy Products |
| 73        | Röd Kaviar                       | Seafood        |
| 74        | Longlife Tofu                    | Produce        |
| 75        | Rhönbräu Klosterbier             | Beverages      |
| 76        | Lakkalikööri                     | Beverages      |
| 77        | Original Frankfurter grüne Soße  | Condiments     |

Note: INNER JOIN returns only rows with a match in both tables. This means that if there is a product with no CategoryID, or with a CategoryID not present in the Categories table, that row will not be returned in the result.

## Naming the Columns
It is a good practice to also include the table name when specifying columns in SQL joins:

## Example:
Add table name in front of column names:
```sql
SELECT Products.ProductID, Products.ProductName, Categories.CategoryName
FROM Products
INNER JOIN Categories ON Products.CategoryID = Categories.CategoryID;
```

| ProductID | ProductName                      | CategoryName   |
| --------- | -------------------------------- | -------------- |
| 1         | Chais                            | Beverages      |
| 2         | Chang                            | Beverages      |
| 3         | Aniseed Syrup                    | Condiments     |
| 4         | Chef Antons Cajun Seasoning      | Condiments     |
| 5         | Chef Antons Gumbo Mix            | Condiments     |
| 6         | Grandmas Boysenberry Spread      | Condiments     |
| 7         | Uncle Bobs Organic Dried Pears   | Produce        |
| 8         | Northwoods Cranberry Sauce       | Condiments     |
| 9         | Mishi Kobe Niku                  | Meat/Poultry   |
| 10        | Ikura                            | Seafood        |
| 11        | Queso Cabrales                   | Dairy Products |
| 12        | Queso Manchego La Pastora        | Dairy Products |
| 13        | Konbu                            | Seafood        |
| 14        | Tofu                             | Produce        |
| 15        | Genen Shouyu                     | Condiments     |
| 16        | Pavlova                          | Confections    |
| 17        | Alice Mutton                     | Meat/Poultry   |
| 18        | Carnarvon Tigers                 | Seafood        |
| 19        | Teatime Chocolate Biscuits       | Confections    |
| 20        | Sir Rodneys Marmalade            | Confections    |
| 21        | Sir Rodneys Scones               | Confections    |
| 22        | Gustafs Knäckebröd               | Grains/Cereals |
| 23        | Tunnbröd                         | Grains/Cereals |
| 24        | Guaraná Fantástica               | Beverages      |
| 25        | NuNuCa Nuß-Nougat-Creme          | Confections    |
| 26        | Gumbär Gummibärchen              | Confections    |
| 27        | Schoggi Schokolade               | Confections    |
| 28        | Rössle Sauerkraut                | Produce        |
| 29        | Thüringer Rostbratwurst          | Meat/Poultry   |
| 30        | Nord-Ost Matjeshering            | Seafood        |
| 31        | Gorgonzola Telino                | Dairy Products |
| 32        | Mascarpone Fabioli               | Dairy Products |
| 33        | Geitost                          | Dairy Products |
| 34        | Sasquatch Ale                    | Beverages      |
| 35        | Steeleye Stout                   | Beverages      |
| 36        | Inlagd Sill                      | Seafood        |
| 37        | Gravad lax                       | Seafood        |
| 38        | Côte de Blaye                    | Beverages      |
| 39        | Chartreuse verte                 | Beverages      |
| 40        | Boston Crab Meat                 | Seafood        |
| 41        | Jacks New England Clam Chowder   | Seafood        |
| 42        | Singaporean Hokkien Fried Mee    | Grains/Cereals |
| 43        | Ipoh Coffee                      | Beverages      |
| 44        | Gula Malacca                     | Condiments     |
| 45        | Røgede sild                      | Seafood        |
| 46        | Spegesild                        | Seafood        |
| 47        | Zaanse koeken                    | Confections    |
| 48        | Chocolade                        | Confections    |
| 49        | Maxilaku                         | Confections    |
| 50        | Valkoinen suklaa                 | Confections    |
| 51        | Manjimup Dried Apples            | Produce        |
| 52        | Filo Mix                         | Grains/Cereals |
| 53        | Perth Pasties                    | Meat/Poultry   |
| 54        | Tourtière                        | Meat/Poultry   |
| 55        | Pâté chinois                     | Meat/Poultry   |
| 56        | Gnocchi di nonna Alice           | Grains/Cereals |
| 57        | Ravioli Angelo                   | Grains/Cereals |
| 58        | Escargots de Bourgogne           | Seafood        |
| 59        | Raclette Courdavault             | Dairy Products |
| 60        | Camembert Pierrot                | Dairy Products |
| 61        | Sirop dérable                    | Condiments     |
| 62        | Tarte au sucre                   | Confections    |
| 63        | Vegie-spread                     | Condiments     |
| 64        | Wimmers gute Semmelknödel        | Grains/Cereals |
| 65        | Louisiana Fiery Hot Pepper Sauce | Condiments     |
| 66        | Louisiana Hot Spiced Okra        | Condiments     |
| 67        | Laughing Lumberjack Lager        | Beverages      |
| 68        | Scottish Longbreads              | Confections    |
| 69        | Gudbrandsdalsost                 | Dairy Products |
| 70        | Outback Lager                    | Beverages      |
| 71        | Fløtemysost                      | Dairy Products |
| 72        | Mozzarella di Giovanni           | Dairy Products |
| 73        | Röd Kaviar                       | Seafood        |
| 74        | Longlife Tofu                    | Produce        |
| 75        | Rhönbräu Klosterbier             | Beverages      |
| 76        | Lakkalikööri                     | Beverages      |
| 77        | Original Frankfurter grüne Soße  | Condiments     |

The example above works without specifying table names, because none of the specified column names are present in both tables. However, if you add the CategoryID column in the SELECT statement, an error occurs, if you do not specify the table name. This is becuase the CategoryID column is present in both tables.

## JOIN or INNER JOIN
JOIN and INNER JOIN will return the same result.

INNER is the default join type of JOIN, so when you write JOIN the parser actually writes INNER JOIN.

## Example:
JOIN is the same as INNER JOIN:
```sql
SELECT Products.ProductID, Products.ProductName, Categories.CategoryName
FROM Products
JOIN Categories ON Products.CategoryID = Categories.CategoryID;
```

| ProductID | ProductName                      | CategoryName   |
| --------- | -------------------------------- | -------------- |
| 1         | Chais                            | Beverages      |
| 2         | Chang                            | Beverages      |
| 3         | Aniseed Syrup                    | Condiments     |
| 4         | Chef Anton's Cajun Seasoning     | Condiments     |
| 5         | Chef Anton's Gumbo Mix           | Condiments     |
| 6         | Grandma's Boysenberry Spread     | Condiments     |
| 7         | Uncle Bob's Organic Dried Pears  | Produce        |
| 8         | Northwoods Cranberry Sauce       | Condiments     |
| 9         | Mishi Kobe Niku                  | Meat/Poultry   |
| 10        | Ikura                            | Seafood        |
| 11        | Queso Cabrales                   | Dairy Products |
| 12        | Queso Manchego La Pastora        | Dairy Products |
| 13        | Konbu                            | Seafood        |
| 14        | Tofu                             | Produce        |
| 15        | Genen Shouyu                     | Condiments     |
| 16        | Pavlova                          | Confections    |
| 17        | Alice Mutton                     | Meat/Poultry   |
| 18        | Carnarvon Tigers                 | Seafood        |
| 19        | Teatime Chocolate Biscuits       | Confections    |
| 20        | Sir Rodney's Marmalade           | Confections    |
| 21        | Sir Rodney's Scones              | Confections    |
| 22        | Gustaf's Knäckebröd              | Grains/Cereals |
| 23        | Tunnbröd                         | Grains/Cereals |
| 24        | Guaraná Fantástica               | Beverages      |
| 25        | NuNuCa Nuß-Nougat-Creme          | Confections    |
| 26        | Gumbär Gummibärchen              | Confections    |
| 27        | Schoggi Schokolade               | Confections    |
| 28        | Rössle Sauerkraut                | Produce        |
| 29        | Thüringer Rostbratwurst          | Meat/Poultry   |
| 30        | Nord-Ost Matjeshering            | Seafood        |
| 31        | Gorgonzola Telino                | Dairy Products |
| 32        | Mascarpone Fabioli               | Dairy Products |
| 33        | Geitost                          | Dairy Products |
| 34        | Sasquatch Ale                    | Beverages      |
| 35        | Steeleye Stout                   | Beverages      |
| 36        | Inlagd Sill                      | Seafood        |
| 37        | Gravad lax                       | Seafood        |
| 38        | Côte de Blaye                    | Beverages      |
| 39        | Chartreuse verte                 | Beverages      |
| 40        | Boston Crab Meat                 | Seafood        |
| 41        | Jack's New England Clam Chowder  | Seafood        |
| 42        | Singaporean Hokkien Fried Mee    | Grains/Cereals |
| 43        | Ipoh Coffee                      | Beverages      |
| 44        | Gula Malacca                     | Condiments     |
| 45        | Røgede sild                      | Seafood        |
| 46        | Spegesild                        | Seafood        |
| 47        | Zaanse koeken                    | Confections    |
| 48        | Chocolade                        | Confections    |
| 49        | Maxilaku                         | Confections    |
| 50        | Valkoinen suklaa                 | Confections    |
| 51        | Manjimup Dried Apples            | Produce        |
| 52        | Filo Mix                         | Grains/Cereals |
| 53        | Perth Pasties                    | Meat/Poultry   |
| 54        | Tourtière                        | Meat/Poultry   |
| 55        | Pâté chinois                     | Meat/Poultry   |
| 56        | Gnocchi di nonna Alice           | Grains/Cereals |
| 57        | Ravioli Angelo                   | Grains/Cereals |
| 58        | Escargots de Bourgogne           | Seafood        |
| 59        | Raclette Courdavault             | Dairy Products |
| 60        | Camembert Pierrot                | Dairy Products |
| 61        | Sirop d'érable                   | Condiments     |
| 62        | Tarte au sucre                   | Confections    |
| 63        | Vegie-spread                     | Condiments     |
| 64        | Wimmers gute Semmelknödel        | Grains/Cereals |
| 65        | Louisiana Fiery Hot Pepper Sauce | Condiments     |
| 66        | Louisiana Hot Spiced Okra        | Condiments     |
| 67        | Laughing Lumberjack Lager        | Beverages      |
| 68        | Scottish Longbreads              | Confections    |
| 69        | Gudbrandsdalsost                 | Dairy Products |
| 70        | Outback Lager                    | Beverages      |
| 71        | Fløtemysost                      | Dairy Products |
| 72        | Mozzarella di Giovanni           | Dairy Products |
| 73        | Röd Kaviar                       | Seafood        |
| 74        | Longlife Tofu                    | Produce        |
| 75        | Rhönbräu Klosterbier             | Beverages      |
| 76        | Lakkalikööri                     | Beverages      |
| 77        | Original Frankfurter grüne Soße  | Condiments     |

## JOIN Multiple Tables
You can join more than two tables by adding multiple INNER JOIN clauses in your query.

The following SQL selects all orders with customer and shipper information:

## Example:
```sql
SELECT Orders.OrderID, Customers.CustomerName, Shippers.ShipperName
FROM Orders
INNER JOIN Customers ON Orders.CustomerID = Customers.CustomerID
INNER JOIN Shippers ON Orders.ShipperID = Shippers.ShipperID;
```

| OrderID | CustomerName                       | ShipperName      |
| ------- | ---------------------------------- | ---------------- |
| 10248   | Wilman Kala                        | Federal Shipping |
| 10249   | Tradição Hipermercados             | Speedy Express   |
| 10250   | Hanari Carnes                      | United Package   |
| 10251   | Victuailles en stock               | Speedy Express   |
| 10252   | Suprêmes délices                   | United Package   |
| 10253   | Hanari Carnes                      | United Package   |
| 10254   | Chop-suey Chinese                  | United Package   |
| 10255   | Richter Supermarkt                 | Federal Shipping |
| 10256   | Wellington Importadora             | United Package   |
| 10257   | HILARIÓN-Abastos                   | Federal Shipping |
| 10258   | Ernst Handel                       | Speedy Express   |
| 10259   | Centro comercial Moctezuma         | Federal Shipping |
| 10260   | Old World Delicatessen             | Speedy Express   |
| 10261   | Que Delícia                        | United Package   |
| 10262   | Rattlesnake Canyon Grocery         | Federal Shipping |
| 10263   | Ernst Handel                       | Federal Shipping |
| 10264   | Folk och fä HB                     | Federal Shipping |
| 10265   | Blondel père et fils               | Speedy Express   |
| 10266   | Wartian Herkku                     | Federal Shipping |
| 10267   | Frankenversand                     | Speedy Express   |
| 10268   | GROSELLA-Restaurante               | Federal Shipping |
| 10269   | White Clover Markets               | Speedy Express   |
| 10270   | Wartian Herkku                     | Speedy Express   |
| 10271   | Split Rail Beer & Ale              | United Package   |
| 10272   | Rattlesnake Canyon Grocery         | United Package   |
| 10273   | QUICK-Stop                         | Federal Shipping |
| 10274   | Vins et alcools Chevalier          | Speedy Express   |
| 10275   | Magazzini Alimentari Riuniti       | Speedy Express   |
| 10276   | Tortuga Restaurante                | Federal Shipping |
| 10277   | Morgenstern Gesundkost             | Federal Shipping |
| 10278   | Berglunds snabbköp                 | United Package   |
| 10279   | Lehmanns Marktstand                | United Package   |
| 10280   | Berglunds snabbköp                 | Speedy Express   |
| 10281   | Romero y tomillo                   | Speedy Express   |
| 10282   | Romero y tomillo                   | Speedy Express   |
| 10283   | LILA-Supermercado                  | Federal Shipping |
| 10284   | Lehmanns Marktstand                | Speedy Express   |
| 10285   | QUICK-Stop                         | United Package   |
| 10286   | QUICK-Stop                         | Federal Shipping |
| 10287   | Ricardo Adocicados                 | Federal Shipping |
| 10288   | Reggiani Caseifici                 | Speedy Express   |
| 10289   | Bs Beverages                       | Federal Shipping |
| 10290   | Comércio Mineiro                   | Speedy Express   |
| 10291   | Que Delícia                        | United Package   |
| 10292   | Tradição Hipermercados             | United Package   |
| 10293   | Tortuga Restaurante                | Federal Shipping |
| 10294   | Rattlesnake Canyon Grocery         | United Package   |
| 10295   | Vins et alcools Chevalier          | United Package   |
| 10296   | LILA-Supermercado                  | Speedy Express   |
| 10297   | Blondel père et fils               | United Package   |
| 10298   | Hungry Owl All-Night Grocers       | United Package   |
| 10299   | Ricardo Adocicados                 | United Package   |
| 10300   | Magazzini Alimentari Riuniti       | United Package   |
| 10301   | Die Wandernde Kuh                  | United Package   |
| 10302   | Suprêmes délices                   | United Package   |
| 10303   | Godos Cocina Típica                | United Package   |
| 10304   | Tortuga Restaurante                | United Package   |
| 10305   | Old World Delicatessen             | Federal Shipping |
| 10306   | Romero y tomillo                   | Federal Shipping |
| 10307   | Lonesome Pine Restaurant           | United Package   |
| 10308   | Ana Trujillo Emparedados y helados | Federal Shipping |
| 10309   | Hungry Owl All-Night Grocers       | Speedy Express   |
| 10310   | The Big Cheese                     | United Package   |
| 10311   | Du monde entier                    | Federal Shipping |
| 10312   | Die Wandernde Kuh                  | United Package   |
| 10313   | QUICK-Stop                         | United Package   |
| 10314   | Rattlesnake Canyon Grocery         | United Package   |
| 10315   | Island Trading                     | United Package   |
| 10316   | Rattlesnake Canyon Grocery         | Federal Shipping |
| 10317   | Lonesome Pine Restaurant           | Speedy Express   |
| 10318   | Island Trading                     | United Package   |
| 10319   | Tortuga Restaurante                | Federal Shipping |
| 10320   | Wartian Herkku                     | Federal Shipping |
| 10321   | Island Trading                     | United Package   |
| 10322   | Pericles Comidas clásicas          | Federal Shipping |
| 10323   | Königlich Essen                    | Speedy Express   |
| 10324   | Save-a-lot Markets                 | Speedy Express   |
| 10325   | Königlich Essen                    | Federal Shipping |
| 10326   | Bólido Comidas preparadas          | United Package   |
| 10327   | Folk och fä HB                     | Speedy Express   |
| 10328   | Furia Bacalhau e Frutos do Mar     | Federal Shipping |
| 10329   | Split Rail Beer & Ale              | United Package   |
| 10330   | LILA-Supermercado                  | Speedy Express   |
| 10331   | Bon app                            | Speedy Express   |
| 10332   | Mère Paillarde                     | United Package   |
| 10333   | Wartian Herkku                     | Federal Shipping |
| 10334   | Victuailles en stock               | United Package   |
| 10335   | Hungry Owl All-Night Grocers       | United Package   |
| 10336   | Princesa Isabel Vinhoss            | United Package   |
| 10337   | Frankenversand                     | Federal Shipping |
| 10338   | Old World Delicatessen             | Federal Shipping |
| 10339   | Mère Paillarde                     | United Package   |
| 10340   | Bon app                            | Federal Shipping |
| 10341   | Simons bistro                      | Federal Shipping |
| 10342   | Frankenversand                     | United Package   |
| 10343   | Lehmanns Marktstand                | Speedy Express   |
| 10344   | White Clover Markets               | United Package   |
| 10345   | QUICK-Stop                         | United Package   |
| 10346   | Rattlesnake Canyon Grocery         | Federal Shipping |
| 10347   | Familia Arquibaldo                 | Federal Shipping |
| 10348   | Die Wandernde Kuh                  | United Package   |
| 10349   | Split Rail Beer & Ale              | Speedy Express   |
| 10350   | La maison dAsie                    | United Package   |
| 10351   | Ernst Handel                       | Speedy Express   |
| 10352   | Furia Bacalhau e Frutos do Mar     | Federal Shipping |
| 10353   | Piccolo und mehr                   | Federal Shipping |
| 10354   | Pericles Comidas clásicas          | Federal Shipping |
| 10355   | Around the Horn                    | Speedy Express   |
| 10356   | Die Wandernde Kuh                  | United Package   |
| 10357   | LILA-Supermercado                  | Federal Shipping |
| 10358   | La maison dAsie                    | Speedy Express   |
| 10359   | Seven Seas Imports                 | Federal Shipping |
| 10360   | Blondel père et fils               | Federal Shipping |
| 10361   | QUICK-Stop                         | United Package   |
| 10362   | Bon app                            | Speedy Express   |
| 10363   | Drachenblut Delikatessend          | Federal Shipping |
| 10364   | Eastern Connection                 | Speedy Express   |
| 10365   | Antonio Moreno Taquería            | United Package   |
| 10366   | Galería del gastrónomo             | United Package   |
| 10367   | Vaffeljernet                       | Federal Shipping |
| 10368   | Ernst Handel                       | United Package   |
| 10369   | Split Rail Beer & Ale              | United Package   |
| 10370   | Chop-suey Chinese                  | United Package   |
| 10371   | La maison dAsie                    | Speedy Express   |
| 10372   | Queen Cozinha                      | United Package   |
| 10373   | Hungry Owl All-Night Grocers       | Federal Shipping |
| 10374   | Wolski                             | Federal Shipping |
| 10375   | Hungry Coyote Import Store         | United Package   |
| 10376   | Mère Paillarde                     | United Package   |
| 10377   | Seven Seas Imports                 | Federal Shipping |
| 10378   | Folk och fä HB                     | Federal Shipping |
| 10379   | Que Delícia                        | Speedy Express   |
| 10380   | Hungry Owl All-Night Grocers       | Federal Shipping |
| 10381   | LILA-Supermercado                  | Federal Shipping |
| 10382   | Ernst Handel                       | Speedy Express   |
| 10383   | Around the Horn                    | Federal Shipping |
| 10384   | Berglunds snabbköp                 | Federal Shipping |
| 10385   | Split Rail Beer & Ale              | United Package   |
| 10386   | Familia Arquibaldo                 | Federal Shipping |
| 10387   | Santé Gourmet                      | United Package   |
| 10388   | Seven Seas Imports                 | Speedy Express   |
| 10389   | Bottom-Dollar Marketse             | United Package   |
| 10390   | Ernst Handel                       | Speedy Express   |
| 10391   | Drachenblut Delikatessend          | Federal Shipping |
| 10392   | Piccolo und mehr                   | Federal Shipping |
| 10393   | Save-a-lot Markets                 | Federal Shipping |
| 10394   | Hungry Coyote Import Store         | Federal Shipping |
| 10395   | HILARIÓN-Abastos                   | Speedy Express   |
| 10396   | Frankenversand                     | Federal Shipping |
| 10397   | Princesa Isabel Vinhoss            | Speedy Express   |
| 10398   | Save-a-lot Markets                 | Federal Shipping |
| 10399   | Vaffeljernet                       | Federal Shipping |
| 10400   | Eastern Connection                 | Federal Shipping |
| 10401   | Rattlesnake Canyon Grocery         | Speedy Express   |
| 10402   | Ernst Handel                       | United Package   |
| 10403   | Ernst Handel                       | Federal Shipping |
| 10404   | Magazzini Alimentari Riuniti       | Speedy Express   |
| 10405   | LINO-Delicateses                   | Speedy Express   |
| 10406   | Queen Cozinha                      | Speedy Express   |
| 10407   | Ottilies Käseladen                 | United Package   |
| 10408   | Folies gourmandes                  | Speedy Express   |
| 10409   | Océano Atlántico Ltda.             | Speedy Express   |
| 10410   | Bottom-Dollar Marketse             | Federal Shipping |
| 10411   | Bottom-Dollar Marketse             | Federal Shipping |
| 10412   | Wartian Herkku                     | United Package   |
| 10413   | La maison dAsie                    | United Package   |
| 10414   | Familia Arquibaldo                 | Federal Shipping |
| 10415   | Hungry Coyote Import Store         | Speedy Express   |
| 10416   | Wartian Herkku                     | Federal Shipping |
| 10417   | Simons bistro                      | Federal Shipping |
| 10418   | QUICK-Stop                         | Speedy Express   |
| 10419   | Richter Supermarkt                 | United Package   |
| 10420   | Wellington Importadora             | Speedy Express   |
| 10421   | Que Delícia                        | Speedy Express   |
| 10422   | Franchi S.p.A.                     | Speedy Express   |
| 10423   | Gourmet Lanchonetes                | Federal Shipping |
| 10424   | Mère Paillarde                     | United Package   |
| 10425   | La maison dAsie                    | United Package   |
| 10426   | Galería del gastrónomo             | Speedy Express   |
| 10427   | Piccolo und mehr                   | United Package   |
| 10428   | Reggiani Caseifici                 | Speedy Express   |
| 10429   | Hungry Owl All-Night Grocers       | United Package   |
| 10430   | Ernst Handel                       | Speedy Express   |
| 10431   | Bottom-Dollar Marketse             | United Package   |
| 10432   | Split Rail Beer & Ale              | United Package   |
| 10433   | Princesa Isabel Vinhoss            | Federal Shipping |
| 10434   | Folk och fä HB                     | United Package   |
| 10435   | Consolidated Holdings              | United Package   |
| 10436   | Blondel père et fils               | United Package   |
| 10437   | Wartian Herkku                     | Speedy Express   |
| 10438   | Toms Spezialitäten                 | United Package   |
| 10439   | Mère Paillarde                     | Federal Shipping |
| 10440   | Save-a-lot Markets                 | United Package   |
| 10441   | Old World Delicatessen             | United Package   |
| 10442   | Ernst Handel                       | United Package   |
| 10443   | Reggiani Caseifici                 | Speedy Express   |

Here is the Shippers table:

| ShipperID | ShipperName      | Phone          |
| --------- | ---------------- | -------------- |
| 1         | Speedy Express   | (503) 555-9831 |
| 2         | United Package   | (503) 555-3199 |
| 3         | Federal Shipping | (503) 555-9931 |



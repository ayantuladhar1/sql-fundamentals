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

OR:

## Example:
Using "double quotes" for aliases with space characters:
```sql
SELECT ProductName AS "My Great Products"
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

Note: Some database systems allows both [] and "", and some only allows one of them.

## Concatenate Columns
The following SQL creates an alias named "Address" that combine four columns (Address, PostalCode, City and Country):

## Example:
```sql
SELECT CustomerName, Address + ', ' + PostalCode + ' ' + City + ', ' + Country AS Address
FROM Customers;
```

| CustomerName                         | Address                                                                      |
| ------------------------------------ | ---------------------------------------------------------------------------- |
| Alfreds Futterkiste                  | Obere Str. 57, 12209 Berlin, Germany                                         |
| Ana Trujillo Emparedados y helados   | Avda. de la Constitución 2222, 05021 México D.F., Mexico                     |
| Antonio Moreno Taquería              | Mataderos 2312, 05023 México D.F., Mexico                                    |
| Around the Horn                      | 120 Hanover Sq., WA1 1DP London, UK                                          |
| Berglunds snabbköp                   | Berguvsvägen 8, S-958 22 Luleå, Sweden                                       |
| Blauer See Delikatessen              | Forsterstr. 57, 68306 Mannheim, Germany                                      |
| Blondel père et fils                 | 24, place Kléber, 67000 Strasbourg, France                                   |
| Bólido Comidas preparadas            | C/ Araquil, 67, 28023 Madrid, Spain                                          |
| Bon app                              | 12, rue des Bouchers, 13008 Marseille, France                                |
| Bottom-Dollar Marketse               | 23 Tsawassen Blvd., T2F 8M4 Tsawassen, Canada                                |
| Bs Beverages                         | Fauntleroy Circus, EC2 5NT London, UK                                        |
| Cactus Comidas para llevar           | Cerrito 333, 1010 Buenos Aires, Argentina                                    |
| Centro comercial Moctezuma           | Sierras de Granada 9993, 05022 México D.F., Mexico                           |
| Chop-suey Chinese                    | Hauptstr. 29, 3012 Bern, Switzerland                                         |
| Comércio Mineiro                     | Av. dos Lusíadas, 23, 05432-043 São Paulo, Brazil                            |
| Consolidated Holdings                | Berkeley Gardens 12 Brewery , WX1 6LT London, UK                             |
| Drachenblut Delikatessend            | Walserweg 21, 52066 Aachen, Germany                                          |
| Du monde entier                      | 67, rue des Cinquante Otages, 44000 Nantes, France                           |
| Eastern Connection                   | 35 King George, WX3 6FW London, UK                                           |
| Ernst Handel                         | Kirchgasse 6, 8010 Graz, Austria                                             |
| Familia Arquibaldo                   | Rua Orós, 92, 05442-030 São Paulo, Brazil                                    |
| FISSA Fabrica Inter. Salchichas S.A. | C/ Moralzarzal, 86, 28034 Madrid, Spain                                      |
| Folies gourmandes                    | 184, chaussée de Tournai, 59000 Lille, France                                |
| Folk och fä HB                       | Åkergatan 24, S-844 67 Bräcke, Sweden                                        |
| Frankenversand                       | Berliner Platz 43, 80805 München, Germany                                    |
| France restauration                  | 54, rue Royale, 44000 Nantes, France                                         |
| Franchi S.p.A.                       | Via Monte Bianco 34, 10100 Torino, Italy                                     |
| Furia Bacalhau e Frutos do Mar       | Jardim das rosas n. 32, 1675 Lisboa, Portugal                                |
| Galería del gastrónomo               | Rambla de Cataluña, 23, 08022 Barcelona, Spain                               |
| Godos Cocina Típica                  | C/ Romero, 33, 41101 Sevilla, Spain                                          |
| Gourmet Lanchonetes                  | Av. Brasil, 442, 04876-786 Campinas, Brazil                                  |
| Great Lakes Food Market              | 2732 Baker Blvd., 97403 Eugene, USA                                          |
| GROSELLA-Restaurante                 | 5ª Ave. Los Palos Grandes, 1081 Caracas, Venezuela                           |
| Hanari Carnes                        | Rua do Paço, 67, 05454-876 Rio de Janeiro, Brazil                            |
| HILARIÓN-Abastos                     | Carrera 22 con Ave. Carlos Soublette #8-35, 5022 San Cristóbal, Venezuela    |
| Hungry Coyote Import Store           | City Center Plaza 516 Main St., 97827 Elgin, USA                             |
| Hungry Owl All-Night Grocers         | 8 Johnstown Road, Cork, Ireland                                              |
| Island Trading                       | Garden House Crowther Way, PO31 7PJ Cowes, UK                                |
| Königlich Essen                      | Maubelstr. 90, 14776 Brandenburg, Germany                                    |
| La corne dabondance                  | 67, avenue de lEurope, 78000 Versailles, France                              |
| La maison dAsie                      | 1 rue Alsace-Lorraine, 31000 Toulouse, France                                |
| Laughing Bacchus Wine Cellars        | 1900 Oak St., V3F 2K1 Vancouver, Canada                                      |
| Lazy K Kountry Store                 | 12 Orchestra Terrace, 99362 Walla Walla, USA                                 |
| Lehmanns Marktstand                  | Magazinweg 7, 60528 Frankfurt a.M. , Germany                                 |
| Lets Stop N Shop                     | 87 Polk St. Suite 5, 94117 San Francisco, USA                                |
| LILA-Supermercado                    | Carrera 52 con Ave. Bolívar #65-98 Llano Largo, 3508 Barquisimeto, Venezuela |
| LINO-Delicateses                     | Ave. 5 de Mayo Porlamar, 4980 I. de Margarita, Venezuela                     |
| Lonesome Pine Restaurant             | 89 Chiaroscuro Rd., 97219 Portland, USA                                      |
| Magazzini Alimentari Riuniti         | Via Ludovico il Moro 22, 24100 Bergamo, Italy                                |
| Maison Dewey                         | Rue Joseph-Bens 532, B-1180 Bruxelles, Belgium                               |
| Mère Paillarde                       | 43 rue St. Laurent, H1J 1C3 Montréal, Canada                                 |
| Morgenstern Gesundkost               | Heerstr. 22, 04179 Leipzig, Germany                                          |
| North/South                          | South House 300 Queensbridge, SW7 1RZ London, UK                             |
| Océano Atlántico Ltda.               | Ing. Gustavo Moncada 8585 Piso 20-A, 1010 Buenos Aires, Argentina            |
| Old World Delicatessen               | 2743 Bering St., 99508 Anchorage, USA                                        |
| Ottilies Käseladen                   | Mehrheimerstr. 369, 50739 Köln, Germany                                      |
| Paris spécialités                    | 265, boulevard Charonne, 75012 Paris, France                                 |
| Pericles Comidas clásicas            | Calle Dr. Jorge Cash 321, 05033 México D.F., Mexico                          |
| Piccolo und mehr                     | Geislweg 14, 5020 Salzburg, Austria                                          |
| Princesa Isabel Vinhoss              | Estrada da saúde n. 58, 1756 Lisboa, Portugal                                |
| Que Delícia                          | Rua da Panificadora, 12, 02389-673 Rio de Janeiro, Brazil                    |
| Queen Cozinha                        | Alameda dos Canàrios, 891, 05487-020 São Paulo, Brazil                       |
| QUICK-Stop                           | Taucherstraße 10, 01307 Cunewalde, Germany                                   |
| Rancho grande                        | Av. del Libertador 900, 1010 Buenos Aires, Argentina                         |
| Rattlesnake Canyon Grocery           | 2817 Milton Dr., 87110 Albuquerque, USA                                      |
| Reggiani Caseifici                   | Strada Provinciale 124, 42100 Reggio Emilia, Italy                           |
| Ricardo Adocicados                   | Av. Copacabana, 267, 02389-890 Rio de Janeiro, Brazil                        |
| Richter Supermarkt                   | Grenzacherweg 237, 1203 Genève, Switzerland                                  |
| Romero y tomillo                     | Gran Vía, 1, 28001 Madrid, Spain                                             |
| Santé Gourmet                        | Erling Skakkes gate 78, 4110 Stavern, Norway                                 |
| Save-a-lot Markets                   | 187 Suffolk Ln., 83720 Boise, USA                                            |
| Seven Seas Imports                   | 90 Wadhurst Rd., OX15 4NB London, UK                                         |
| Simons bistro                        | Vinbæltet 34, 1734 København, Denmark                                        |
| Spécialités du monde                 | 25, rue Lauriston, 75016 Paris, France                                       |
| Split Rail Beer & Ale                | P.O. Box 555, 82520 Lander, USA                                              |
| Suprêmes délices                     | Boulevard Tirou, 255, B-6000 Charleroi, Belgium                              |
| The Big Cheese                       | 89 Jefferson Way Suite 2, 97201 Portland, USA                                |
| The Cracker Box                      | 55 Grizzly Peak Rd., 59801 Butte, USA                                        |
| Toms Spezialitäten                   | Luisenstr. 48, 44087 Münster, Germany                                        |
| Tortuga Restaurante                  | Avda. Azteca 123, 05033 México D.F., Mexico                                  |
| Tradição Hipermercados               | Av. Inês de Castro, 414, 05634-030 São Paulo, Brazil                         |
| Trails Head Gourmet Provisioners     | 722 DaVinci Blvd., 98034 Kirkland, USA                                       |
| Vaffeljernet                         | Smagsløget 45, 8200 Århus, Denmark                                           |
| Victuailles en stock                 | 2, rue du Commerce, 69004 Lyon, France                                       |
| Vins et alcools Chevalier            | 59 rue de lAbbaye, 51100 Reims, France                                       |
| Die Wandernde Kuh                    | Adenauerallee 900, 70563 Stuttgart, Germany                                  |
| Wartian Herkku                       | Torikatu 38, 90110 Oulu, Finland                                             |
| Wellington Importadora               | Rua do Mercado, 12, 08737-363 Resende, Brazil                                |
| White Clover Markets                 | 305 - 14th Ave. S. Suite 3B, 98128 Seattle, USA                              |
| Wilman Kala                          | Keskuskatu 45, 21240 Helsinki, Finland                                       |
| Wolski                               | ul. Filtrowa 68, 01-012 Walla, Poland                                        |

Note: To get the SQL statement above to work in MySQL use the following:

## MySQL Example
```sql
SELECT CustomerName, CONCAT(Address,', ',PostalCode,', ',City,', ',Country) AS Address
FROM Customers;
```

Note: To get the SQL statement above to work in Oracle use the following:

## Oracle Example:
```sql
SELECT CustomerName, (Address || ', ' || PostalCode || ' ' || City || ', ' || Country) AS Address
FROM Customers;
```

## Alias for Tables
The same rules applies when you want to use an alias for a table.

## Example:
Refer to the Customers table as Persons instead:
```sql
SELECT * FROM Customers AS Persons;
```

| CustomerID | CustomerName                         | ContactName          | Address                                        | City            | PostalCode | Country     |
| ---------- | ------------------------------------ | -------------------- | ---------------------------------------------- | --------------- | ---------- | ----------- |
| 1          | Alfreds Futterkiste                  | Maria Anders         | Obere Str. 57                                  | Berlin          | 12209      | Germany     |
| 2          | Ana Trujillo Emparedados y helados   | Ana Trujillo         | Avda. de la Constitución 2222                  | México D.F.     | 05021      | Mexico      |
| 3          | Antonio Moreno Taquería              | Antonio Moreno       | Mataderos 2312                                 | México D.F.     | 05023      | Mexico      |
| 4          | Around the Horn                      | Thomas Hardy         | 120 Hanover Sq.                                | London          | WA1 1DP    | UK          |
| 5          | Berglunds snabbköp                   | Christina Berglund   | Berguvsvägen 8                                 | Luleå           | S-958 22   | Sweden      |
| 6          | Blauer See Delikatessen              | Hanna Moos           | Forsterstr. 57                                 | Mannheim        | 68306      | Germany     |
| 7          | Blondel père et fils                 | Frédérique Citeaux   | 24, place Kléber                               | Strasbourg      | 67000      | France      |
| 8          | Bólido Comidas preparadas            | Martín Sommer        | C/ Araquil, 67                                 | Madrid          | 28023      | Spain       |
| 9          | Bon app                              | Laurence Lebihans    | 12, rue des Bouchers                           | Marseille       | 13008      | France      |
| 10         | Bottom-Dollar Marketse               | Elizabeth Lincoln    | 23 Tsawassen Blvd.                             | Tsawassen       | T2F 8M4    | Canada      |
| 11         | Bs Beverages                         | Victoria Ashworth    | Fauntleroy Circus                              | London          | EC2 5NT    | UK          |
| 12         | Cactus Comidas para llevar           | Patricio Simpson     | Cerrito 333                                    | Buenos Aires    | 1010       | Argentina   |
| 13         | Centro comercial Moctezuma           | Francisco Chang      | Sierras de Granada 9993                        | México D.F.     | 05022      | Mexico      |
| 14         | Chop-suey Chinese                    | Yang Wang            | Hauptstr. 29                                   | Bern            | 3012       | Switzerland |
| 15         | Comércio Mineiro                     | Pedro Afonso         | Av. dos Lusíadas, 23                           | São Paulo       | 05432-043  | Brazil      |
| 16         | Consolidated Holdings                | Elizabeth Brown      | Berkeley Gardens 12 Brewery                    | London          | WX1 6LT    | UK          |
| 17         | Drachenblut Delikatessend            | Sven Ottlieb         | Walserweg 21                                   | Aachen          | 52066      | Germany     |
| 18         | Du monde entier                      | Janine Labrune       | 67, rue des Cinquante Otages                   | Nantes          | 44000      | France      |
| 19         | Eastern Connection                   | Ann Devon            | 35 King George                                 | London          | WX3 6FW    | UK          |
| 20         | Ernst Handel                         | Roland Mendel        | Kirchgasse 6                                   | Graz            | 8010       | Austria     |
| 21         | Familia Arquibaldo                   | Aria Cruz            | Rua Orós, 92                                   | São Paulo       | 05442-030  | Brazil      |
| 22         | FISSA Fabrica Inter. Salchichas S.A. | Diego Roel           | C/ Moralzarzal, 86                             | Madrid          | 28034      | Spain       |
| 23         | Folies gourmandes                    | Martine Rancé        | 184, chaussée de Tournai                       | Lille           | 59000      | France      |
| 24         | Folk och fä HB                       | Maria Larsson        | Åkergatan 24                                   | Bräcke          | S-844 67   | Sweden      |
| 25         | Frankenversand                       | Peter Franken        | Berliner Platz 43                              | München         | 80805      | Germany     |
| 26         | France restauration                  | Carine Schmitt       | 54, rue Royale                                 | Nantes          | 44000      | France      |
| 27         | Franchi S.p.A.                       | Paolo Accorti        | Via Monte Bianco 34                            | Torino          | 10100      | Italy       |
| 28         | Furia Bacalhau e Frutos do Mar       | Lino Rodriguez       | Jardim das rosas n. 32                         | Lisboa          | 1675       | Portugal    |
| 29         | Galería del gastrónomo               | Eduardo Saavedra     | Rambla de Cataluña, 23                         | Barcelona       | 08022      | Spain       |
| 30         | Godos Cocina Típica                  | José Pedro Freyre    | C/ Romero, 33                                  | Sevilla         | 41101      | Spain       |
| 31         | Gourmet Lanchonetes                  | André Fonseca        | Av. Brasil, 442                                | Campinas        | 04876-786  | Brazil      |
| 32         | Great Lakes Food Market              | Howard Snyder        | 2732 Baker Blvd.                               | Eugene          | 97403      | USA         |
| 33         | GROSELLA-Restaurante                 | Manuel Pereira       | 5ª Ave. Los Palos Grandes                      | Caracas         | 1081       | Venezuela   |
| 34         | Hanari Carnes                        | Mario Pontes         | Rua do Paço, 67                                | Rio de Janeiro  | 05454-876  | Brazil      |
| 35         | HILARIÓN-Abastos                     | Carlos Hernández     | Carrera 22 con Ave. Carlos Soublette #8-35     | San Cristóbal   | 5022       | Venezuela   |
| 36         | Hungry Coyote Import Store           | Yoshi Latimer        | City Center Plaza 516 Main St.                 | Elgin           | 97827      | USA         |
| 37         | Hungry Owl All-Night Grocers         | Patricia McKenna     | 8 Johnstown Road                               | Cork            |            | Ireland     |
| 38         | Island Trading                       | Helen Bennett        | Garden House Crowther Way                      | Cowes           | PO31 7PJ   | UK          |
| 39         | Königlich Essen                      | Philip Cramer        | Maubelstr. 90                                  | Brandenburg     | 14776      | Germany     |
| 40         | La corne dabondance                  | Daniel Tonini        | 67, avenue de lEurope                          | Versailles      | 78000      | France      |
| 41         | La maison dAsie                      | Annette Roulet       | 1 rue Alsace-Lorraine                          | Toulouse        | 31000      | France      |
| 42         | Laughing Bacchus Wine Cellars        | Yoshi Tannamuri      | 1900 Oak St.                                   | Vancouver       | V3F 2K1    | Canada      |
| 43         | Lazy K Kountry Store                 | John Steel           | 12 Orchestra Terrace                           | Walla Walla     | 99362      | USA         |
| 44         | Lehmanns Marktstand                  | Renate Messner       | Magazinweg 7                                   | Frankfurt a.M.  | 60528      | Germany     |
| 45         | Lets Stop N Shop                     | Jaime Yorres         | 87 Polk St. Suite 5                            | San Francisco   | 94117      | USA         |
| 46         | LILA-Supermercado                    | Carlos González      | Carrera 52 con Ave. Bolívar #65-98 Llano Largo | Barquisimeto    | 3508       | Venezuela   |
| 47         | LINO-Delicateses                     | Felipe Izquierdo     | Ave. 5 de Mayo Porlamar                        | I. de Margarita | 4980       | Venezuela   |
| 48         | Lonesome Pine Restaurant             | Fran Wilson          | 89 Chiaroscuro Rd.                             | Portland        | 97219      | USA         |
| 49         | Magazzini Alimentari Riuniti         | Giovanni Rovelli     | Via Ludovico il Moro 22                        | Bergamo         | 24100      | Italy       |
| 50         | Maison Dewey                         | Catherine Dewey      | Rue Joseph-Bens 532                            | Bruxelles       | B-1180     | Belgium     |
| 51         | Mère Paillarde                       | Jean Fresnière       | 43 rue St. Laurent                             | Montréal        | H1J 1C3    | Canada      |
| 52         | Morgenstern Gesundkost               | Alexander Feuer      | Heerstr. 22                                    | Leipzig         | 04179      | Germany     |
| 53         | North/South                          | Simon Crowther       | South House 300 Queensbridge                   | London          | SW7 1RZ    | UK          |
| 54         | Océano Atlántico Ltda.               | Yvonne Moncada       | Ing. Gustavo Moncada 8585 Piso 20-A            | Buenos Aires    | 1010       | Argentina   |
| 55         | Old World Delicatessen               | Rene Phillips        | 2743 Bering St.                                | Anchorage       | 99508      | USA         |
| 56         | Ottilies Käseladen                   | Henriette Pfalzheim  | Mehrheimerstr. 369                             | Köln            | 50739      | Germany     |
| 57         | Paris spécialités                    | Marie Bertrand       | 265, boulevard Charonne                        | Paris           | 75012      | France      |
| 58         | Pericles Comidas clásicas            | Guillermo Fernández  | Calle Dr. Jorge Cash 321                       | México D.F.     | 05033      | Mexico      |
| 59         | Piccolo und mehr                     | Georg Pipps          | Geislweg 14                                    | Salzburg        | 5020       | Austria     |
| 60         | Princesa Isabel Vinhoss              | Isabel de Castro     | Estrada da saúde n. 58                         | Lisboa          | 1756       | Portugal    |
| 61         | Que Delícia                          | Bernardo Batista     | Rua da Panificadora, 12                        | Rio de Janeiro  | 02389-673  | Brazil      |
| 62         | Queen Cozinha                        | Lúcia Carvalho       | Alameda dos Canàrios, 891                      | São Paulo       | 05487-020  | Brazil      |
| 63         | QUICK-Stop                           | Horst Kloss          | Taucherstraße 10                               | Cunewalde       | 01307      | Germany     |
| 64         | Rancho grande                        | Sergio Gutiérrez     | Av. del Libertador 900                         | Buenos Aires    | 1010       | Argentina   |
| 65         | Rattlesnake Canyon Grocery           | Paula Wilson         | 2817 Milton Dr.                                | Albuquerque     | 87110      | USA         |
| 66         | Reggiani Caseifici                   | Maurizio Moroni      | Strada Provinciale 124                         | Reggio Emilia   | 42100      | Italy       |
| 67         | Ricardo Adocicados                   | Janete Limeira       | Av. Copacabana, 267                            | Rio de Janeiro  | 02389-890  | Brazil      |
| 68         | Richter Supermarkt                   | Michael Holz         | Grenzacherweg 237                              | Genève          | 1203       | Switzerland |
| 69         | Romero y tomillo                     | Alejandra Camino     | Gran Vía, 1                                    | Madrid          | 28001      | Spain       |
| 70         | Santé Gourmet                        | Jonas Bergulfsen     | Erling Skakkes gate 78                         | Stavern         | 4110       | Norway      |
| 71         | Save-a-lot Markets                   | Jose Pavarotti       | 187 Suffolk Ln.                                | Boise           | 83720      | USA         |
| 72         | Seven Seas Imports                   | Hari Kumar           | 90 Wadhurst Rd.                                | London          | OX15 4NB   | UK          |
| 73         | Simons bistro                        | Jytte Petersen       | Vinbæltet 34                                   | København       | 1734       | Denmark     |
| 74         | Spécialités du monde                 | Dominique Perrier    | 25, rue Lauriston                              | Paris           | 75016      | France      |
| 75         | Split Rail Beer & Ale                | Art Braunschweiger   | P.O. Box 555                                   | Lander          | 82520      | USA         |
| 76         | Suprêmes délices                     | Pascale Cartrain     | Boulevard Tirou, 255                           | Charleroi       | B-6000     | Belgium     |
| 77         | The Big Cheese                       | Liz Nixon            | 89 Jefferson Way Suite 2                       | Portland        | 97201      | USA         |
| 78         | The Cracker Box                      | Liu Wong             | 55 Grizzly Peak Rd.                            | Butte           | 59801      | USA         |
| 79         | Toms Spezialitäten                   | Karin Josephs        | Luisenstr. 48                                  | Münster         | 44087      | Germany     |
| 80         | Tortuga Restaurante                  | Miguel Angel Paolino | Avda. Azteca 123                               | México D.F.     | 05033      | Mexico      |
| 81         | Tradição Hipermercados               | Anabela Domingues    | Av. Inês de Castro, 414                        | São Paulo       | 05634-030  | Brazil      |
| 82         | Trails Head Gourmet Provisioners     | Helvetius Nagy       | 722 DaVinci Blvd.                              | Kirkland        | 98034      | USA         |
| 83         | Vaffeljernet                         | Palle Ibsen          | Smagsløget 45                                  | Århus           | 8200       | Denmark     |
| 84         | Victuailles en stock                 | Mary Saveley         | 2, rue du Commerce                             | Lyon            | 69004      | France      |
| 85         | Vins et alcools Chevalier            | Paul Henriot         | 59 rue de lAbbaye                              | Reims           | 51100      | France      |
| 86         | Die Wandernde Kuh                    | Rita Müller          | Adenauerallee 900                              | Stuttgart       | 70563      | Germany     |
| 87         | Wartian Herkku                       | Pirkko Koskitalo     | Torikatu 38                                    | Oulu            | 90110      | Finland     |
| 88         | Wellington Importadora               | Paula Parente        | Rua do Mercado, 12                             | Resende         | 08737-363  | Brazil      |
| 89         | White Clover Markets                 | Karl Jablonski       | 305 - 14th Ave. S. Suite 3B                    | Seattle         | 98128      | USA         |
| 90         | Wilman Kala                          | Matti Karttunen      | Keskuskatu 45                                  | Helsinki        | 21240      | Finland     |
| 91         | Wolski                               | Zbyszek              | ul. Filtrowa 68                                | Walla           | 01-012     | Poland      |

It might seem useless to use aliases on tables, but when you are joining tables, it makes sense.

In the following example, c is the alias for customers and o is for orders, making the query shorter and easier to read:

## Example:
```sql
SELECT c.CustomerName, o.OrderID
FROM customers AS c
JOIN orders AS o ON c.customerID = o.customerID;
```

| CustomerName                       | OrderID |
| ---------------------------------- | ------- |
| Ana Trujillo Emparedados y helados | 10308   |
| Antonio Moreno Taquería            | 10365   |
| Around the Horn                    | 10355   |
| Around the Horn                    | 10383   |
| Berglunds snabbköp                 | 10384   |
| Berglunds snabbköp                 | 10278   |
| Berglunds snabbköp                 | 10280   |
| Blondel père et fils               | 10265   |
| Blondel père et fils               | 10297   |
| Blondel père et fils               | 10360   |
| Blondel père et fils               | 10436   |
| Bólido Comidas preparadas          | 10326   |
| Bon app                            | 10331   |
| Bon app                            | 10340   |
| Bon app                            | 10362   |
| Bottom-Dollar Marketse             | 10389   |
| Bottom-Dollar Marketse             | 10431   |
| Bottom-Dollar Marketse             | 10410   |
| Bottom-Dollar Marketse             | 10411   |
| Bs Beverages                       | 10289   |
| Centro comercial Moctezuma         | 10259   |
| Chop-suey Chinese                  | 10254   |
| Chop-suey Chinese                  | 10370   |
| Comércio Mineiro                   | 10290   |
| Consolidated Holdings              | 10435   |
| Drachenblut Delikatessend          | 10391   |
| Drachenblut Delikatessend          | 10363   |
| Du monde entier                    | 10311   |
| Eastern Connection                 | 10364   |
| Eastern Connection                 | 10400   |
| Ernst Handel                       | 10402   |
| Ernst Handel                       | 10403   |
| Ernst Handel                       | 10430   |
| Ernst Handel                       | 10442   |
| Ernst Handel                       | 10368   |
| Ernst Handel                       | 10390   |
| Ernst Handel                       | 10382   |
| Ernst Handel                       | 10351   |
| Ernst Handel                       | 10258   |
| Ernst Handel                       | 10263   |
| Familia Arquibaldo                 | 10347   |
| Familia Arquibaldo                 | 10386   |
| Familia Arquibaldo                 | 10414   |
| Folies gourmandes                  | 10408   |
| Folk och fä HB                     | 10434   |
| Folk och fä HB                     | 10378   |
| Folk och fä HB                     | 10327   |
| Folk och fä HB                     | 10264   |
| Frankenversand                     | 10267   |
| Frankenversand                     | 10342   |
| Frankenversand                     | 10337   |
| Frankenversand                     | 10396   |
| Franchi S.p.A.                     | 10422   |
| Furia Bacalhau e Frutos do Mar     | 10352   |
| Furia Bacalhau e Frutos do Mar     | 10328   |
| Galería del gastrónomo             | 10366   |
| Galería del gastrónomo             | 10426   |
| Godos Cocina Típica                | 10303   |
| Gourmet Lanchonetes                | 10423   |
| GROSELLA-Restaurante               | 10268   |
| Hanari Carnes                      | 10253   |
| Hanari Carnes                      | 10250   |
| HILARIÓN-Abastos                   | 10257   |
| HILARIÓN-Abastos                   | 10395   |
| Hungry Coyote Import Store         | 10394   |
| Hungry Coyote Import Store         | 10415   |
| Hungry Coyote Import Store         | 10375   |
| Hungry Owl All-Night Grocers       | 10373   |
| Hungry Owl All-Night Grocers       | 10380   |
| Hungry Owl All-Night Grocers       | 10335   |
| Hungry Owl All-Night Grocers       | 10309   |
| Hungry Owl All-Night Grocers       | 10298   |
| Hungry Owl All-Night Grocers       | 10429   |
| Island Trading                     | 10315   |
| Island Trading                     | 10318   |
| Island Trading                     | 10321   |
| Königlich Essen                    | 10323   |
| Königlich Essen                    | 10325   |
| La maison dAsie                    | 10371   |
| La maison dAsie                    | 10358   |
| La maison dAsie                    | 10350   |
| La maison dAsie                    | 10425   |
| La maison dAsie                    | 10413   |
| Lehmanns Marktstand                | 10343   |
| Lehmanns Marktstand                | 10284   |
| Lehmanns Marktstand                | 10279   |
| LILA-Supermercado                  | 10296   |
| LILA-Supermercado                  | 10283   |
| LILA-Supermercado                  | 10330   |
| LILA-Supermercado                  | 10381   |
| LILA-Supermercado                  | 10357   |
| LINO-Delicateses                   | 10405   |
| Lonesome Pine Restaurant           | 10317   |
| Lonesome Pine Restaurant           | 10307   |
| Magazzini Alimentari Riuniti       | 10300   |
| Magazzini Alimentari Riuniti       | 10275   |
| Magazzini Alimentari Riuniti       | 10404   |
| Mère Paillarde                     | 10424   |
| Mère Paillarde                     | 10439   |
| Mère Paillarde                     | 10332   |
| Mère Paillarde                     | 10339   |
| Mère Paillarde                     | 10376   |
| Morgenstern Gesundkost             | 10277   |
| Océano Atlántico Ltda.             | 10409   |
| Old World Delicatessen             | 10441   |
| Old World Delicatessen             | 10260   |
| Old World Delicatessen             | 10305   |
| Old World Delicatessen             | 10338   |
| Ottilies Käseladen                 | 10407   |
| Pericles Comidas clásicas          | 10322   |
| Pericles Comidas clásicas          | 10354   |
| Piccolo und mehr                   | 10353   |
| Piccolo und mehr                   | 10427   |
| Piccolo und mehr                   | 10392   |
| Princesa Isabel Vinhoss            | 10397   |
| Princesa Isabel Vinhoss            | 10433   |
| Princesa Isabel Vinhoss            | 10336   |
| Que Delícia                        | 10379   |
| Que Delícia                        | 10291   |
| Que Delícia                        | 10261   |
| Que Delícia                        | 10421   |
| Queen Cozinha                      | 10406   |
| Queen Cozinha                      | 10372   |
| QUICK-Stop                         | 10361   |
| QUICK-Stop                         | 10345   |
| QUICK-Stop                         | 10273   |
| QUICK-Stop                         | 10285   |
| QUICK-Stop                         | 10286   |
| QUICK-Stop                         | 10313   |
| QUICK-Stop                         | 10418   |
| Rattlesnake Canyon Grocery         | 10401   |
| Rattlesnake Canyon Grocery         | 10314   |
| Rattlesnake Canyon Grocery         | 10316   |
| Rattlesnake Canyon Grocery         | 10294   |
| Rattlesnake Canyon Grocery         | 10272   |
| Rattlesnake Canyon Grocery         | 10262   |
| Rattlesnake Canyon Grocery         | 10346   |
| Reggiani Caseifici                 | 10288   |
| Reggiani Caseifici                 | 10428   |
| Reggiani Caseifici                 | 10443   |
| Ricardo Adocicados                 | 10299   |
| Ricardo Adocicados                 | 10287   |
| Richter Supermarkt                 | 10255   |
| Richter Supermarkt                 | 10419   |
| Romero y tomillo                   | 10281   |
| Romero y tomillo                   | 10282   |
| Romero y tomillo                   | 10306   |
| Santé Gourmet                      | 10387   |
| Save-a-lot Markets                 | 10324   |
| Save-a-lot Markets                 | 10398   |
| Save-a-lot Markets                 | 10393   |
| Save-a-lot Markets                 | 10440   |
| Seven Seas Imports                 | 10388   |
| Seven Seas Imports                 | 10377   |
| Seven Seas Imports                 | 10359   |
| Simons bistro                      | 10341   |
| Simons bistro                      | 10417   |
| Split Rail Beer & Ale              | 10432   |
| Split Rail Beer & Ale              | 10349   |
| Split Rail Beer & Ale              | 10329   |
| Split Rail Beer & Ale              | 10369   |
| Split Rail Beer & Ale              | 10385   |
| Split Rail Beer & Ale              | 10271   |
| Suprêmes délices                   | 10252   |
| Suprêmes délices                   | 10302   |
| The Big Cheese                     | 10310   |
| Toms Spezialitäten                 | 10438   |
| Tortuga Restaurante                | 10304   |
| Tortuga Restaurante                | 10293   |
| Tortuga Restaurante                | 10276   |
| Tortuga Restaurante                | 10319   |
| Tradição Hipermercados             | 10249   |
| Tradição Hipermercados             | 10292   |
| Vaffeljernet                       | 10367   |
| Vaffeljernet                       | 10399   |
| Victuailles en stock               | 10334   |
| Victuailles en stock               | 10251   |
| Vins et alcools Chevalier          | 10274   |
| Vins et alcools Chevalier          | 10295   |
| Die Wandernde Kuh                  | 10301   |
| Die Wandernde Kuh                  | 10312   |
| Die Wandernde Kuh                  | 10348   |
| Die Wandernde Kuh                  | 10356   |
| Wartian Herkku                     | 10333   |
| Wartian Herkku                     | 10320   |
| Wartian Herkku                     | 10270   |
| Wartian Herkku                     | 10266   |
| Wartian Herkku                     | 10416   |
| Wartian Herkku                     | 10412   |
| Wartian Herkku                     | 10437   |
| Wellington Importadora             | 10420   |
| Wellington Importadora             | 10256   |
| White Clover Markets               | 10269   |
| White Clover Markets               | 10344   |
| Wilman Kala                        | 10248   |
| Wolski                             | 10374   |

Aliases are useful when:
* There are more than one table involved in a query
* Functions are used in the query
* Column names are long or not very readable
* Two or more columns are combined together

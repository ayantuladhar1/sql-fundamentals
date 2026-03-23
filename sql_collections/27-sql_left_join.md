# SQL LEFT JOIN
The LEFT JOIN returns all rows from the left table (table1), and only the matched rows from the right table(table2).

If there is no match in the right table, the result for the columns from the right table will be NULL.

The LEFT JOIN and LEFT OUTER JOIN keywords are equal - the OUTER keyword is optional.

<img width="284" height="177" alt="image" src="https://github.com/user-attachments/assets/e6df15b2-f6f9-41fc-8536-232da7cf7c2c" />

## LEFT JOIN Syntax
```sql
SELECT column_name(s)
FROM table1
LEFT JOIN table2
ON table1.column_name = table2.column_name;
```

## Demo Database
Below is a selection from the "Customers" table:

| CustomerID | CustomerName                       | ContactName    | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | -------------- | ----------------------------- | ----------- | ---------- | ------- |
| 1          | Alfreds Futterkiste                | Maria Anders   | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo   | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno | Mataderos 2312                | México D.F. | 05023      | Mexico  |

And a selection from the "Orders" table:

| OrderID | CustomerID | EmployeeID | OrderDate  | ShipperID |
| ------- | ---------- | ---------- | ---------- | --------- |
| 10308   | 2          | 7          | 1996-09-18 | 3         |
| 10309   | 37         | 3          | 1996-09-19 | 1         |
| 10310   | 77         | 8          | 1996-09-20 | 2         |

## SQL LEFT JOIN Example:
The following SQL returns all customers and their orders, including customers who have not placed any orders:

## Example:
```sql
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders
ON Customers.CustomerID=Orders.CustomerID
ORDER BY Customers.CustomerName;
```

| CustomerName                         | OrderID |
| ------------------------------------ | ------- |
| Alfreds Futterkiste                  |         |
| Ana Trujillo Emparedados y helados   | 10308   |
| Antonio Moreno Taquería              | 10365   |
| Around the Horn                      | 10355   |
| Around the Horn                      | 10383   |
| Berglunds snabbköp                   | 10384   |
| Berglunds snabbköp                   | 10278   |
| Berglunds snabbköp                   | 10280   |
| Blauer See Delikatessen              |         |
| Blondel père et fils                 | 10265   |
| Blondel père et fils                 | 10297   |
| Blondel père et fils                 | 10360   |
| Blondel père et fils                 | 10436   |
| Bólido Comidas preparadas            | 10326   |
| Bon app                              | 10331   |
| Bon app                              | 10340   |
| Bon app                              | 10362   |
| Bottom-Dollar Marketse               | 10389   |
| Bottom-Dollar Marketse               | 10431   |
| Bottom-Dollar Marketse               | 10410   |
| Bottom-Dollar Marketse               | 10411   |
| Bs Beverages                         | 10289   |
| Cactus Comidas para llevar           |         |
| Centro comercial Moctezuma           | 10259   |
| Chop-suey Chinese                    | 10254   |
| Chop-suey Chinese                    | 10370   |
| Comércio Mineiro                     | 10290   |
| Consolidated Holdings                | 10435   |
| Die Wandernde Kuh                    | 10301   |
| Die Wandernde Kuh                    | 10312   |
| Die Wandernde Kuh                    | 10348   |
| Die Wandernde Kuh                    | 10356   |
| Drachenblut Delikatessend            | 10391   |
| Drachenblut Delikatessend            | 10363   |
| Du monde entier                      | 10311   |
| Eastern Connection                   | 10364   |
| Eastern Connection                   | 10400   |
| Ernst Handel                         | 10402   |
| Ernst Handel                         | 10403   |
| Ernst Handel                         | 10430   |
| Ernst Handel                         | 10442   |
| Ernst Handel                         | 10368   |
| Ernst Handel                         | 10390   |
| Ernst Handel                         | 10382   |
| Ernst Handel                         | 10351   |
| Ernst Handel                         | 10258   |
| Ernst Handel                         | 10263   |
| Familia Arquibaldo                   | 10347   |
| Familia Arquibaldo                   | 10386   |
| Familia Arquibaldo                   | 10414   |
| FISSA Fabrica Inter. Salchichas S.A. |         |
| Folies gourmandes                    | 10408   |
| Folk och fä HB                       | 10434   |
| Folk och fä HB                       | 10378   |
| Folk och fä HB                       | 10327   |
| Folk och fä HB                       | 10264   |
| France restauration                  |         |
| Franchi S.p.A.                       | 10422   |
| Frankenversand                       | 10267   |
| Frankenversand                       | 10342   |
| Frankenversand                       | 10337   |
| Frankenversand                       | 10396   |
| Furia Bacalhau e Frutos do Mar       | 10352   |
| Furia Bacalhau e Frutos do Mar       | 10328   |
| Galería del gastrónomo               | 10366   |
| Galería del gastrónomo               | 10426   |
| Godos Cocina Típica                  | 10303   |
| Gourmet Lanchonetes                  | 10423   |
| Great Lakes Food Market              |         |
| GROSELLA-Restaurante                 | 10268   |
| Hanari Carnes                        | 10253   |
| Hanari Carnes                        | 10250   |
| HILARIÓN-Abastos                     | 10257   |
| HILARIÓN-Abastos                     | 10395   |
| Hungry Coyote Import Store           | 10394   |
| Hungry Coyote Import Store           | 10415   |
| Hungry Coyote Import Store           | 10375   |
| Hungry Owl All-Night Grocers         | 10373   |
| Hungry Owl All-Night Grocers         | 10380   |
| Hungry Owl All-Night Grocers         | 10335   |
| Hungry Owl All-Night Grocers         | 10309   |
| Hungry Owl All-Night Grocers         | 10298   |
| Hungry Owl All-Night Grocers         | 10429   |
| Island Trading                       | 10315   |
| Island Trading                       | 10318   |
| Island Trading                       | 10321   |
| Königlich Essen                      | 10323   |
| Königlich Essen                      | 10325   |
| La corne dabondance                  |         |
| La maison dAsie                      | 10371   |
| La maison dAsie                      | 10358   |
| La maison dAsie                      | 10350   |
| La maison dAsie                      | 10425   |
| La maison dAsie                      | 10413   |
| Laughing Bacchus Wine Cellars        |         |
| Lazy K Kountry Store                 |         |
| Lehmanns Marktstand                  | 10343   |
| Lehmanns Marktstand                  | 10284   |
| Lehmanns Marktstand                  | 10279   |
| Lets Stop N Shop                     |         |
| LILA-Supermercado                    | 10296   |
| LILA-Supermercado                    | 10283   |
| LILA-Supermercado                    | 10330   |
| LILA-Supermercado                    | 10381   |
| LILA-Supermercado                    | 10357   |
| LINO-Delicateses                     | 10405   |
| Lonesome Pine Restaurant             | 10317   |
| Lonesome Pine Restaurant             | 10307   |
| Magazzini Alimentari Riuniti         | 10300   |
| Magazzini Alimentari Riuniti         | 10275   |
| Magazzini Alimentari Riuniti         | 10404   |
| Maison Dewey                         |         |
| Mère Paillarde                       | 10424   |
| Mère Paillarde                       | 10439   |
| Mère Paillarde                       | 10332   |
| Mère Paillarde                       | 10339   |
| Mère Paillarde                       | 10376   |
| Morgenstern Gesundkost               | 10277   |
| North/South                          |         |
| Océano Atlántico Ltda.               | 10409   |
| Old World Delicatessen               | 10441   |
| Old World Delicatessen               | 10260   |
| Old World Delicatessen               | 10305   |
| Old World Delicatessen               | 10338   |
| Ottilies Käseladen                   | 10407   |
| Paris spécialités                    |         |
| Pericles Comidas clásicas            | 10322   |
| Pericles Comidas clásicas            | 10354   |
| Piccolo und mehr                     | 10353   |
| Piccolo und mehr                     | 10427   |
| Piccolo und mehr                     | 10392   |
| Princesa Isabel Vinhoss              | 10397   |
| Princesa Isabel Vinhoss              | 10433   |
| Princesa Isabel Vinhoss              | 10336   |
| Que Delícia                          | 10379   |
| Que Delícia                          | 10291   |
| Que Delícia                          | 10261   |
| Que Delícia                          | 10421   |
| Queen Cozinha                        | 10406   |
| Queen Cozinha                        | 10372   |
| QUICK-Stop                           | 10361   |
| QUICK-Stop                           | 10345   |
| QUICK-Stop                           | 10273   |
| QUICK-Stop                           | 10285   |
| QUICK-Stop                           | 10286   |
| QUICK-Stop                           | 10313   |
| QUICK-Stop                           | 10418   |
| Rancho grande                        |         |
| Rattlesnake Canyon Grocery           | 10401   |
| Rattlesnake Canyon Grocery           | 10314   |
| Rattlesnake Canyon Grocery           | 10316   |
| Rattlesnake Canyon Grocery           | 10294   |
| Rattlesnake Canyon Grocery           | 10272   |
| Rattlesnake Canyon Grocery           | 10262   |
| Rattlesnake Canyon Grocery           | 10346   |
| Reggiani Caseifici                   | 10288   |
| Reggiani Caseifici                   | 10428   |
| Reggiani Caseifici                   | 10443   |
| Ricardo Adocicados                   | 10299   |
| Ricardo Adocicados                   | 10287   |
| Richter Supermarkt                   | 10255   |
| Richter Supermarkt                   | 10419   |
| Romero y tomillo                     | 10281   |
| Romero y tomillo                     | 10282   |
| Romero y tomillo                     | 10306   |
| Santé Gourmet                        | 10387   |
| Save-a-lot Markets                   | 10324   |
| Save-a-lot Markets                   | 10398   |
| Save-a-lot Markets                   | 10393   |
| Save-a-lot Markets                   | 10440   |
| Seven Seas Imports                   | 10388   |
| Seven Seas Imports                   | 10377   |
| Seven Seas Imports                   | 10359   |
| Simons bistro                        | 10341   |
| Simons bistro                        | 10417   |
| Spécialités du monde                 |         |
| Split Rail Beer & Ale                | 10432   |
| Split Rail Beer & Ale                | 10349   |
| Split Rail Beer & Ale                | 10329   |
| Split Rail Beer & Ale                | 10369   |
| Split Rail Beer & Ale                | 10385   |
| Split Rail Beer & Ale                | 10271   |
| Suprêmes délices                     | 10252   |
| Suprêmes délices                     | 10302   |
| The Big Cheese                       | 10310   |
| The Cracker Box                      |         |
| Toms Spezialitäten                   | 10438   |
| Tortuga Restaurante                  | 10304   |
| Tortuga Restaurante                  | 10293   |
| Tortuga Restaurante                  | 10276   |
| Tortuga Restaurante                  | 10319   |
| Tradição Hipermercados               | 10249   |
| Tradição Hipermercados               | 10292   |
| Trails Head Gourmet Provisioners     |         |
| Vaffeljernet                         | 10367   |
| Vaffeljernet                         | 10399   |
| Victuailles en stock                 | 10334   |
| Victuailles en stock                 | 10251   |
| Vins et alcools Chevalier            | 10274   |
| Vins et alcools Chevalier            | 10295   |
| Wartian Herkku                       | 10333   |
| Wartian Herkku                       | 10320   |
| Wartian Herkku                       | 10270   |
| Wartian Herkku                       | 10266   |
| Wartian Herkku                       | 10416   |
| Wartian Herkku                       | 10412   |
| Wartian Herkku                       | 10437   |
| Wellington Importadora               | 10420   |
| Wellington Importadora               | 10256   |
| White Clover Markets                 | 10269   |
| White Clover Markets                 | 10344   |
| Wilman Kala                          | 10248   |
| Wolski                               | 10374   |

Tip: To find only the customers who have not placed any order, add a WHERE clause to filter for NULL values on the right table:

## Example:
```sql
SELECT Customers.CustomerName, Orders.OrderID
FROM Customers
LEFT JOIN Orders
ON Customers.CustomerID = Orders.CustomerID
WHERE Orders.CustomerID IS NULL;
```

| CustomerName                         | OrderID |
| ------------------------------------ | ------- |
| Alfreds Futterkiste                  |         |
| Blauer See Delikatessen              |         |
| Cactus Comidas para llevar           |         |
| FISSA Fabrica Inter. Salchichas S.A. |         |
| France restauration                  |         |
| Great Lakes Food Market              |         |
| La corne dabondance                  |         |
| Laughing Bacchus Wine Cellars        |         |
| Lazy K Kountry Store                 |         |
| Lets Stop N Shop                     |         |
| Maison Dewey                         |         |
| North/South                          |         |
| Paris spécialités                    |         |
| Rancho grande                        |         |
| Spécialités du monde                 |         |
| The Cracker Box                      |         |
| Trails Head Gourmet Provisioners     |         |


# SQL Joins
The JOIN clause is used to combine rows from two or more tables, based on a related column between them.

Here are the different types of JOINs in SQL:
* (INNER) JOIN: Returns only rows that have matching values in both tables
* LEFT (OUTER) JOIN: Returns all rows from the left table, and only the matched rows from the right table
* RIGHT (OUTER) JOIN: Returns all rows from the right table, and only the matched rows from the left table
* FULL (OUTER) JOIN: Returns all rows when there is a match in either the left or right table

Look at an order in "Orders" table

| OrderID | CustomerID | OrderDate  |
| ------- | ---------- | ---------- |
| 10308   | 2          | 1996-09-18 |

Then, look at a customer in the "Customers" table:

| CustomerID | CustomerName                       | ContactName  | Country |
| ---------- | ---------------------------------- | ------------ | ------- |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo | Mexico  |

Here we see that the "CustomerID" column in the "Orders" table refers to the "CustomerID" in the "CustomerID" column.

Then, we can create the following SQL statement (that contains an INNER JOIN), that selects records that have matching values in both tables:

## Example:
```sql
SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers
ON Orders.CustomerID=Customers.CustomerID;
```

and it will produce something like this:

| OrderID | CustomerName                       | OrderDate  |
| ------- | ---------------------------------- | ---------- |
| 10308   | Ana Trujillo Emparedados y helados | 1996-09-18 |
| 10365   | Antonio Moreno Taquería            | 1996-11-27 |
| 10355   | Around the Horn                    | 1996-11-15 |
| 10383   | Around the Horn                    | 1996-12-16 |
| 10384   | Berglunds snabbköp                 | 1996-12-16 |
| 10278   | Berglunds snabbköp                 | 1996-08-12 |
| 10280   | Berglunds snabbköp                 | 1996-08-14 |
| 10265   | Blondel père et fils               | 1996-07-25 |
| 10297   | Blondel père et fils               | 1996-09-04 |
| 10360   | Blondel père et fils               | 1996-11-22 |
| 10436   | Blondel père et fils               | 1997-02-05 |
| 10326   | Bólido Comidas preparadas          | 1996-10-10 |
| 10331   | Bon app                            | 1996-10-16 |
| 10340   | Bon app                            | 1996-10-29 |
| 10362   | Bon app                            | 1996-11-25 |
| 10389   | Bottom-Dollar Marketse             | 1996-12-20 |
| 10431   | Bottom-Dollar Marketse             | 1997-01-30 |
| 10410   | Bottom-Dollar Marketse             | 1997-01-10 |
| 10411   | Bottom-Dollar Marketse             | 1997-01-10 |
| 10289   | Bs Beverages                       | 1996-08-26 |
| 10259   | Centro comercial Moctezuma         | 1996-07-18 |
| 10254   | Chop-suey Chinese                  | 1996-07-11 |
| 10370   | Chop-suey Chinese                  | 1996-12-03 |
| 10290   | Comércio Mineiro                   | 1996-08-27 |
| 10435   | Consolidated Holdings              | 1997-02-04 |
| 10391   | Drachenblut Delikatessend          | 1996-12-23 |
| 10363   | Drachenblut Delikatessend          | 1996-11-26 |
| 10311   | Du monde entier                    | 1996-09-20 |
| 10364   | Eastern Connection                 | 1996-11-26 |
| 10400   | Eastern Connection                 | 1997-01-01 |
| 10402   | Ernst Handel                       | 1997-01-02 |
| 10403   | Ernst Handel                       | 1997-01-03 |
| 10430   | Ernst Handel                       | 1997-01-30 |
| 10442   | Ernst Handel                       | 1997-02-11 |
| 10368   | Ernst Handel                       | 1996-11-29 |
| 10390   | Ernst Handel                       | 1996-12-23 |
| 10382   | Ernst Handel                       | 1996-12-13 |
| 10351   | Ernst Handel                       | 1996-11-11 |
| 10258   | Ernst Handel                       | 1996-07-17 |
| 10263   | Ernst Handel                       | 1996-07-23 |
| 10347   | Familia Arquibaldo                 | 1996-11-06 |
| 10386   | Familia Arquibaldo                 | 1996-12-18 |
| 10414   | Familia Arquibaldo                 | 1997-01-14 |
| 10408   | Folies gourmandes                  | 1997-01-08 |
| 10434   | Folk och fä HB                     | 1997-02-03 |
| 10378   | Folk och fä HB                     | 1996-12-10 |
| 10327   | Folk och fä HB                     | 1996-10-11 |
| 10264   | Folk och fä HB                     | 1996-07-24 |
| 10267   | Frankenversand                     | 1996-07-29 |
| 10342   | Frankenversand                     | 1996-10-30 |
| 10337   | Frankenversand                     | 1996-10-24 |
| 10396   | Frankenversand                     | 1996-12-27 |
| 10422   | Franchi S.p.A.                     | 1997-01-22 |
| 10352   | Furia Bacalhau e Frutos do Mar     | 1996-11-12 |
| 10328   | Furia Bacalhau e Frutos do Mar     | 1996-10-14 |
| 10366   | Galería del gastrónomo             | 1996-11-28 |
| 10426   | Galería del gastrónomo             | 1997-01-27 |
| 10303   | Godos Cocina Típica                | 1996-09-11 |
| 10423   | Gourmet Lanchonetes                | 1997-01-23 |
| 10268   | GROSELLA-Restaurante               | 1996-07-30 |
| 10253   | Hanari Carnes                      | 1996-07-10 |
| 10250   | Hanari Carnes                      | 1996-07-08 |
| 10257   | HILARIÓN-Abastos                   | 1996-07-16 |
| 10395   | HILARIÓN-Abastos                   | 1996-12-26 |
| 10394   | Hungry Coyote Import Store         | 1996-12-25 |
| 10415   | Hungry Coyote Import Store         | 1997-01-15 |
| 10375   | Hungry Coyote Import Store         | 1996-12-06 |
| 10373   | Hungry Owl All-Night Grocers       | 1996-12-05 |
| 10380   | Hungry Owl All-Night Grocers       | 1996-12-12 |
| 10335   | Hungry Owl All-Night Grocers       | 1996-10-22 |
| 10309   | Hungry Owl All-Night Grocers       | 1996-09-19 |
| 10298   | Hungry Owl All-Night Grocers       | 1996-09-05 |
| 10429   | Hungry Owl All-Night Grocers       | 1997-01-29 |
| 10315   | Island Trading                     | 1996-09-26 |
| 10318   | Island Trading                     | 1996-10-01 |
| 10321   | Island Trading                     | 1996-10-03 |
| 10323   | Königlich Essen                    | 1996-10-07 |
| 10325   | Königlich Essen                    | 1996-10-09 |
| 10371   | La maison dAsie                    | 1996-12-03 |
| 10358   | La maison dAsie                    | 1996-11-20 |
| 10350   | La maison dAsie                    | 1996-11-11 |
| 10425   | La maison dAsie                    | 1997-01-24 |
| 10413   | La maison dAsie                    | 1997-01-14 |
| 10343   | Lehmanns Marktstand                | 1996-10-31 |
| 10284   | Lehmanns Marktstand                | 1996-08-19 |
| 10279   | Lehmanns Marktstand                | 1996-08-13 |
| 10296   | LILA-Supermercado                  | 1996-09-03 |
| 10283   | LILA-Supermercado                  | 1996-08-16 |
| 10330   | LILA-Supermercado                  | 1996-10-16 |
| 10381   | LILA-Supermercado                  | 1996-12-12 |
| 10357   | LILA-Supermercado                  | 1996-11-19 |
| 10405   | LINO-Delicateses                   | 1997-01-06 |
| 10317   | Lonesome Pine Restaurant           | 1996-09-30 |
| 10307   | Lonesome Pine Restaurant           | 1996-09-17 |
| 10300   | Magazzini Alimentari Riuniti       | 1996-09-09 |
| 10275   | Magazzini Alimentari Riuniti       | 1996-08-07 |
| 10404   | Magazzini Alimentari Riuniti       | 1997-01-03 |
| 10424   | Mère Paillarde                     | 1997-01-23 |
| 10439   | Mère Paillarde                     | 1997-02-07 |
| 10332   | Mère Paillarde                     | 1996-10-17 |
| 10339   | Mère Paillarde                     | 1996-10-28 |
| 10376   | Mère Paillarde                     | 1996-12-09 |
| 10277   | Morgenstern Gesundkost             | 1996-08-09 |
| 10409   | Océano Atlántico Ltda.             | 1997-01-09 |
| 10441   | Old World Delicatessen             | 1997-02-10 |
| 10260   | Old World Delicatessen             | 1996-07-19 |
| 10305   | Old World Delicatessen             | 1996-09-13 |
| 10338   | Old World Delicatessen             | 1996-10-25 |
| 10407   | Ottilies Käseladen                 | 1997-01-07 |
| 10322   | Pericles Comidas clásicas          | 1996-10-04 |
| 10354   | Pericles Comidas clásicas          | 1996-11-14 |
| 10353   | Piccolo und mehr                   | 1996-11-13 |
| 10427   | Piccolo und mehr                   | 1997-01-27 |
| 10392   | Piccolo und mehr                   | 1996-12-24 |
| 10397   | Princesa Isabel Vinhoss            | 1996-12-27 |
| 10433   | Princesa Isabel Vinhoss            | 1997-02-03 |
| 10336   | Princesa Isabel Vinhoss            | 1996-10-23 |
| 10379   | Que Delícia                        | 1996-12-11 |
| 10291   | Que Delícia                        | 1996-08-27 |
| 10261   | Que Delícia                        | 1996-07-19 |
| 10421   | Que Delícia                        | 1997-01-21 |
| 10406   | Queen Cozinha                      | 1997-01-07 |
| 10372   | Queen Cozinha                      | 1996-12-04 |
| 10361   | QUICK-Stop                         | 1996-11-22 |
| 10345   | QUICK-Stop                         | 1996-11-04 |
| 10273   | QUICK-Stop                         | 1996-08-05 |
| 10285   | QUICK-Stop                         | 1996-08-20 |
| 10286   | QUICK-Stop                         | 1996-08-21 |
| 10313   | QUICK-Stop                         | 1996-09-24 |
| 10418   | QUICK-Stop                         | 1997-01-17 |
| 10401   | Rattlesnake Canyon Grocery         | 1997-01-01 |
| 10314   | Rattlesnake Canyon Grocery         | 1996-09-25 |
| 10316   | Rattlesnake Canyon Grocery         | 1996-09-27 |
| 10294   | Rattlesnake Canyon Grocery         | 1996-08-30 |
| 10272   | Rattlesnake Canyon Grocery         | 1996-08-02 |
| 10262   | Rattlesnake Canyon Grocery         | 1996-07-22 |
| 10346   | Rattlesnake Canyon Grocery         | 1996-11-05 |
| 10288   | Reggiani Caseifici                 | 1996-08-23 |
| 10428   | Reggiani Caseifici                 | 1997-01-28 |
| 10443   | Reggiani Caseifici                 | 1997-02-12 |
| 10299   | Ricardo Adocicados                 | 1996-09-06 |
| 10287   | Ricardo Adocicados                 | 1996-08-22 |
| 10255   | Richter Supermarkt                 | 1996-07-12 |
| 10419   | Richter Supermarkt                 | 1997-01-20 |
| 10281   | Romero y tomillo                   | 1996-08-14 |
| 10282   | Romero y tomillo                   | 1996-08-15 |
| 10306   | Romero y tomillo                   | 1996-09-16 |
| 10387   | Santé Gourmet                      | 1996-12-18 |
| 10324   | Save-a-lot Markets                 | 1996-10-08 |
| 10398   | Save-a-lot Markets                 | 1996-12-30 |
| 10393   | Save-a-lot Markets                 | 1996-12-25 |
| 10440   | Save-a-lot Markets                 | 1997-02-10 |
| 10388   | Seven Seas Imports                 | 1996-12-19 |
| 10377   | Seven Seas Imports                 | 1996-12-09 |
| 10359   | Seven Seas Imports                 | 1996-11-21 |
| 10341   | Simons bistro                      | 1996-10-29 |
| 10417   | Simons bistro                      | 1997-01-16 |
| 10432   | Split Rail Beer & Ale              | 1997-01-31 |
| 10349   | Split Rail Beer & Ale              | 1996-11-08 |
| 10329   | Split Rail Beer & Ale              | 1996-10-15 |
| 10369   | Split Rail Beer & Ale              | 1996-12-02 |
| 10385   | Split Rail Beer & Ale              | 1996-12-17 |
| 10271   | Split Rail Beer & Ale              | 1996-08-01 |
| 10252   | Suprêmes délices                   | 1996-07-09 |
| 10302   | Suprêmes délices                   | 1996-09-10 |
| 10310   | The Big Cheese                     | 1996-09-20 |
| 10438   | Toms Spezialitäten                 | 1997-02-06 |
| 10304   | Tortuga Restaurante                | 1996-09-12 |
| 10293   | Tortuga Restaurante                | 1996-08-29 |
| 10276   | Tortuga Restaurante                | 1996-08-08 |
| 10319   | Tortuga Restaurante                | 1996-10-02 |
| 10249   | Tradição Hipermercados             | 1996-07-05 |
| 10292   | Tradição Hipermercados             | 1996-08-28 |
| 10367   | Vaffeljernet                       | 1996-11-28 |
| 10399   | Vaffeljernet                       | 1996-12-31 |
| 10334   | Victuailles en stock               | 1996-10-21 |
| 10251   | Victuailles en stock               | 1996-07-08 |
| 10274   | Vins et alcools Chevalier          | 1996-08-06 |
| 10295   | Vins et alcools Chevalier          | 1996-09-02 |
| 10301   | Die Wandernde Kuh                  | 1996-09-09 |
| 10312   | Die Wandernde Kuh                  | 1996-09-23 |
| 10348   | Die Wandernde Kuh                  | 1996-11-07 |
| 10356   | Die Wandernde Kuh                  | 1996-11-18 |
| 10333   | Wartian Herkku                     | 1996-10-18 |
| 10320   | Wartian Herkku                     | 1996-10-03 |
| 10270   | Wartian Herkku                     | 1996-08-01 |
| 10266   | Wartian Herkku                     | 1996-07-26 |
| 10416   | Wartian Herkku                     | 1997-01-16 |
| 10412   | Wartian Herkku                     | 1997-01-13 |
| 10437   | Wartian Herkku                     | 1997-02-05 |
| 10420   | Wellington Importadora             | 1997-01-21 |
| 10256   | Wellington Importadora             | 1996-07-15 |
| 10269   | White Clover Markets               | 1996-07-31 |
| 10344   | White Clover Markets               | 1996-11-01 |
| 10248   | Wilman Kala                        | 1996-07-04 |
| 10374   | Wolski                             | 1996-12-05 |

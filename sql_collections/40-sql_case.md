# SQL CASE Expression
The CASE expression is used to define different results based on specified conditions in an SQL statement.

The CASE expression goes through the conditions and stops at the first match (like an if-then-else statement). So, once a condition is true, it will stop processing and return the result. If no conditions are true, it returns the value in the ELSE clause. If there is no ELSE clause and no conditions are true, it returns NULL.

## CASE Syntax
```sql
CASE
  WHEN condition1 THEN result1
  WHEN condition2 THEN result2
  WHEN conditionN THEN resultN
  ELSE default_result
END;
```

## SQL CASE Example
Here we use the CASE expression to categorize data (Price) and we create a new column (PriceCategory) that shows in which price category each product is:

## Example:
```sql
SELECT ProductName, Price,
CASE
  WHEN Price < 20 THEN 'Low Cost'
  WHEN Price BETWEEN 20 AND 50 THEN 'Medium Cost'
  ELSE 'High Cost'
END AS PriceCategory
FROM Products;
```

| ProductName                      | Price  | PriceCategory |
| -------------------------------- | ------ | ------------- |
| Chais                            | 18.00  | Low Cost      |
| Chang                            | 19.00  | Low Cost      |
| Aniseed Syrup                    | 10.00  | Low Cost      |
| Chef Anton's Cajun Seasoning     | 22.00  | Medium Cost   |
| Chef Anton's Gumbo Mix           | 21.35  | Medium Cost   |
| Grandma's Boysenberry Spread     | 25.00  | Medium Cost   |
| Uncle Bob's Organic Dried Pears  | 30.00  | Medium Cost   |
| Northwoods Cranberry Sauce       | 40.00  | Medium Cost   |
| Mishi Kobe Niku                  | 97.00  | High Cost     |
| Ikura                            | 31.00  | Medium Cost   |
| Queso Cabrales                   | 21.00  | Medium Cost   |
| Queso Manchego La Pastora        | 38.00  | Medium Cost   |
| Konbu                            | 6.00   | Low Cost      |
| Tofu                             | 23.25  | Medium Cost   |
| Genen Shouyu                     | 15.50  | Low Cost      |
| Pavlova                          | 17.45  | Low Cost      |
| Alice Mutton                     | 39.00  | Medium Cost   |
| Carnarvon Tigers                 | 62.50  | High Cost     |
| Teatime Chocolate Biscuits       | 9.20   | Low Cost      |
| Sir Rodney's Marmalade           | 81.00  | High Cost     |
| Sir Rodney's Scones              | 10.00  | Low Cost      |
| Gustaf's Knäckebröd              | 21.00  | Medium Cost   |
| Tunnbröd                         | 9.00   | Low Cost      |
| Guaraná Fantástica               | 4.50   | Low Cost      |
| NuNuCa Nuß-Nougat-Creme          | 14.00  | Low Cost      |
| Gumbär Gummibärchen              | 31.23  | Medium Cost   |
| Schoggi Schokolade               | 43.90  | Medium Cost   |
| Rössle Sauerkraut                | 45.60  | Medium Cost   |
| Thüringer Rostbratwurst          | 123.79 | High Cost     |
| Nord-Ost Matjeshering            | 25.89  | Medium Cost   |
| Gorgonzola Telino                | 12.50  | Low Cost      |
| Mascarpone Fabioli               | 32.00  | Medium Cost   |
| Geitost                          | 2.50   | Low Cost      |
| Sasquatch Ale                    | 14.00  | Low Cost      |
| Steeleye Stout                   | 18.00  | Low Cost      |
| Inlagd Sill                      | 19.00  | Low Cost      |
| Gravad lax                       | 26.00  | Medium Cost   |
| Côte de Blaye                    | 263.50 | High Cost     |
| Chartreuse verte                 | 18.00  | Low Cost      |
| Boston Crab Meat                 | 18.40  | Low Cost      |
| Jack's New England Clam Chowder  | 9.65   | Low Cost      |
| Singaporean Hokkien Fried Mee    | 14.00  | Low Cost      |
| Ipoh Coffee                      | 46.00  | Medium Cost   |
| Gula Malacca                     | 19.45  | Low Cost      |
| Røgede sild                      | 9.50   | Low Cost      |
| Spegesild                        | 12.00  | Low Cost      |
| Zaanse koeken                    | 9.50   | Low Cost      |
| Chocolade                        | 12.75  | Low Cost      |
| Maxilaku                         | 20.00  | Medium Cost   |
| Valkoinen suklaa                 | 16.25  | Low Cost      |
| Manjimup Dried Apples            | 53.00  | High Cost     |
| Filo Mix                         | 7.00   | Low Cost      |
| Perth Pasties                    | 32.80  | Medium Cost   |
| Tourtière                        | 7.45   | Low Cost      |
| Pâté chinois                     | 24.00  | Medium Cost   |
| Gnocchi di nonna Alice           | 38.00  | Medium Cost   |
| Ravioli Angelo                   | 19.50  | Low Cost      |
| Escargots de Bourgogne           | 13.25  | Low Cost      |
| Raclette Courdavault             | 55.00  | High Cost     |
| Camembert Pierrot                | 34.00  | Medium Cost   |
| Sirop d'érable                   | 28.50  | Medium Cost   |
| Tarte au sucre                   | 49.30  | Medium Cost   |
| Vegie-spread                     | 43.90  | Medium Cost   |
| Wimmers gute Semmelknödel        | 33.25  | Medium Cost   |
| Louisiana Fiery Hot Pepper Sauce | 21.05  | Medium Cost   |
| Louisiana Hot Spiced Okra        | 17.00  | Low Cost      |
| Laughing Lumberjack Lager        | 14.00  | Low Cost      |
| Scottish Longbreads              | 12.50  | Low Cost      |
| Gudbrandsdalsost                 | 36.00  | Medium Cost   |
| Outback Lager                    | 15.00  | Low Cost      |
| Fløtemysost                      | 21.50  | Medium Cost   |
| Mozzarella di Giovanni           | 34.80  | Medium Cost   |
| Röd Kaviar                       | 15.00  | Low Cost      |
| Longlife Tofu                    | 10.00  | Low Cost      |
| Rhönbräu Klosterbier             | 7.75   | Low Cost      |
| Lakkalikööri                     | 18.00  | Low Cost      |
| Original Frankfurter grüne Soße  | 13.00  | Low Cost      |


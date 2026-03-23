# SQL UNION Operator
The UNION operator is used to combine the result-set of two or more SELECT statements.

The UNION operator automatically removes duplicate rows from the result set.

Requirements fro UNION:
* Every SELECT statement within UNION must have the same number of columns
* The columns must also have similar data types
* The columns in every SELECT statement must also be in the same order

## UNION Syntax
```sql
SELECT column_name(s) FROM table1
UNION
SELECT column_name(s) FROM table2;
```

Note: The column names in the result-set are usually equal to the column names in the first SELECT statement.

## Demo Database
Below is a selection from the "Customers" table:

| CustomerID | CustomerName                       | ContactName    | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | -------------- | ----------------------------- | ----------- | ---------- | ------- |
| 1          | Alfreds Futterkiste                | Maria Anders   | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo   | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno | Mataderos 2312                | México D.F. | 05023      | Mexico  |

And a selection from the "Suppliers" table:

| SupplierID | SupplierName               | ContactName      | Address        | City        | PostalCode | Country |
| ---------- | -------------------------- | ---------------- | -------------- | ----------- | ---------- | ------- |
| 1          | Exotic Liquid              | Charlotte Cooper | 49 Gilbert St. | London      | EC1 4SD    | UK      |
| 2          | New Orleans Cajun Delights | Shelley Burke    | P.O. Box 78934 | New Orleans | 70117      | USA     |
| 3          | Grandma Kelly's Homestead  | Regina Murphy    | 707 Oxford Rd. | Ann Arbor   | 48104      | USA     |

## SQL UNION Example
The following SQL returns the unique (distinct) countries from both the "Customers" and the "Suppliers" table:

## Example:
```sql
SELECT Country FROM Customers
UNION
SELECT Country FROM Suppliers
ORDER BY Country;
```

| Country     |
| ----------- |
| Argentina   |
| Australia   |
| Austria     |
| Belgium     |
| Brazil      |
| Canada      |
| Denmark     |
| Finland     |
| France      |
| Germany     |
| Ireland     |
| Italy       |
| Japan       |
| Mexico      |
| Netherlands |
| Norway      |
| Poland      |
| Portugal    |
| Singapore   |
| Spain       |
| Sweden      |
| Switzerland |
| UK          |
| USA         |
| Venezuela   |

Note: If some customers or suppliers have the same country, each country will only be listed once, because UNION selects only distinct values. Use UNION ALL to also select duplicate values!

## SQL UNION With WHERE
Here we add a WHERE clause to only return the unique German cities from both the "Customers" and the "Suppliers" table:

## Example:
```sql
SELECT City, Country FROM Customers
WHERE Country='Germany'
UNION
SELECT City, Country FROM Suppliers
WHERE Country='Germany'
ORDER BY City;
```

| City           | Country |
| -------------- | ------- |
| Aachen         | Germany |
| Berlin         | Germany |
| Brandenburg    | Germany |
| Cunewalde      | Germany |
| Cuxhaven       | Germany |
| Frankfurt      | Germany |
| Frankfurt a.M. | Germany |
| Köln           | Germany |
| Leipzig        | Germany |
| Mannheim       | Germany |
| München        | Germany |
| Münster        | Germany |
| Stuttgart      | Germany |

## Another UNION Example:
The following SQL lists all customers and suppliers:

## Example:
```sql
SELECT 'Customer' AS Type, ContactName, City, Country
FROM Customers
UNION
SELECT 'Supplier', ContactName, City, Country
FROM Suppliers
```

| Type     | ContactName                | City            | Country     |
| -------- | -------------------------- | --------------- | ----------- |
| Customer | Alejandra Camino           | Madrid          | Spain       |
| Customer | Alexander Feuer            | Leipzig         | Germany     |
| Customer | Ana Trujillo               | México D.F.     | Mexico      |
| Customer | Anabela Domingues          | São Paulo       | Brazil      |
| Customer | André Fonseca              | Campinas        | Brazil      |
| Customer | Ann Devon                  | London          | UK          |
| Customer | Annette Roulet             | Toulouse        | France      |
| Customer | Antonio Moreno             | México D.F.     | Mexico      |
| Customer | Aria Cruz                  | São Paulo       | Brazil      |
| Customer | Art Braunschweiger         | Lander          | USA         |
| Customer | Bernardo Batista           | Rio de Janeiro  | Brazil      |
| Customer | Carine Schmitt             | Nantes          | France      |
| Customer | Carlos González            | Barquisimeto    | Venezuela   |
| Customer | Carlos Hernández           | San Cristóbal   | Venezuela   |
| Customer | Catherine Dewey            | Bruxelles       | Belgium     |
| Customer | Christina Berglund         | Luleå           | Sweden      |
| Customer | Daniel Tonini              | Versailles      | France      |
| Customer | Diego Roel                 | Madrid          | Spain       |
| Customer | Dominique Perrier          | Paris           | France      |
| Customer | Eduardo Saavedra           | Barcelona       | Spain       |
| Customer | Elizabeth Brown            | London          | UK          |
| Customer | Elizabeth Lincoln          | Tsawassen       | Canada      |
| Customer | Felipe Izquierdo           | I. de Margarita | Venezuela   |
| Customer | Fran Wilson                | Portland        | USA         |
| Customer | Francisco Chang            | México D.F.     | Mexico      |
| Customer | Frédérique Citeaux         | Strasbourg      | France      |
| Customer | Georg Pipps                | Salzburg        | Austria     |
| Customer | Giovanni Rovelli           | Bergamo         | Italy       |
| Customer | Guillermo Fernández        | México D.F.     | Mexico      |
| Customer | Hanna Moos                 | Mannheim        | Germany     |
| Customer | Hari Kumar                 | London          | UK          |
| Customer | Helen Bennett              | Cowes           | UK          |
| Customer | Helvetius Nagy             | Kirkland        | USA         |
| Customer | Henriette Pfalzheim        | Köln            | Germany     |
| Customer | Horst Kloss                | Cunewalde       | Germany     |
| Customer | Howard Snyder              | Eugene          | USA         |
| Customer | Isabel de Castro           | Lisboa          | Portugal    |
| Customer | Jaime Yorres               | San Francisco   | USA         |
| Customer | Janete Limeira             | Rio de Janeiro  | Brazil      |
| Customer | Janine Labrune             | Nantes          | France      |
| Customer | Jean Fresnière             | Montréal        | Canada      |
| Customer | John Steel                 | Walla Walla     | USA         |
| Customer | Jonas Bergulfsen           | Stavern         | Norway      |
| Customer | Jose Pavarotti             | Boise           | USA         |
| Customer | José Pedro Freyre          | Sevilla         | Spain       |
| Customer | Jytte Petersen             | København       | Denmark     |
| Customer | Karin Josephs              | Münster         | Germany     |
| Customer | Karl Jablonski             | Seattle         | USA         |
| Customer | Laurence Lebihans          | Marseille       | France      |
| Customer | Lino Rodriguez             | Lisboa          | Portugal    |
| Customer | Liu Wong                   | Butte           | USA         |
| Customer | Liz Nixon                  | Portland        | USA         |
| Customer | Lúcia Carvalho             | São Paulo       | Brazil      |
| Customer | Manuel Pereira             | Caracas         | Venezuela   |
| Customer | Maria Anders               | Berlin          | Germany     |
| Customer | Maria Larsson              | Bräcke          | Sweden      |
| Customer | Marie Bertrand             | Paris           | France      |
| Customer | Mario Pontes               | Rio de Janeiro  | Brazil      |
| Customer | Martín Sommer              | Madrid          | Spain       |
| Customer | Martine Rancé              | Lille           | France      |
| Customer | Mary Saveley               | Lyon            | France      |
| Customer | Matti Karttunen            | Helsinki        | Finland     |
| Customer | Maurizio Moroni            | Reggio Emilia   | Italy       |
| Customer | Michael Holz               | Genève          | Switzerland |
| Customer | Miguel Angel Paolino       | México D.F.     | Mexico      |
| Customer | Palle Ibsen                | Århus           | Denmark     |
| Customer | Paolo Accorti              | Torino          | Italy       |
| Customer | Pascale Cartrain           | Charleroi       | Belgium     |
| Customer | Patricia McKenna           | Cork            | Ireland     |
| Customer | Patricio Simpson           | Buenos Aires    | Argentina   |
| Customer | Paul Henriot               | Reims           | France      |
| Customer | Paula Parente              | Resende         | Brazil      |
| Customer | Paula Wilson               | Albuquerque     | USA         |
| Customer | Pedro Afonso               | São Paulo       | Brazil      |
| Customer | Peter Franken              | München         | Germany     |
| Customer | Philip Cramer              | Brandenburg     | Germany     |
| Customer | Pirkko Koskitalo           | Oulu            | Finland     |
| Customer | Renate Messner             | Frankfurt a.M.  | Germany     |
| Customer | Rene Phillips              | Anchorage       | USA         |
| Customer | Rita Müller                | Stuttgart       | Germany     |
| Customer | Roland Mendel              | Graz            | Austria     |
| Customer | Sergio Gutiérrez           | Buenos Aires    | Argentina   |
| Customer | Simon Crowther             | London          | UK          |
| Customer | Sven Ottlieb               | Aachen          | Germany     |
| Customer | Thomas Hardy               | London          | UK          |
| Customer | Victoria Ashworth          | London          | UK          |
| Customer | Yang Wang                  | Bern            | Switzerland |
| Customer | Yoshi Latimer              | Elgin           | USA         |
| Customer | Yoshi Tannamuri            | Vancouver       | Canada      |
| Customer | Yvonne Moncada             | Buenos Aires    | Argentina   |
| Customer | Zbyszek                    | Walla           | Poland      |
| Supplier | Anne Heikkonen             | Lappeenranta    | Finland     |
| Supplier | Antonio del Valle Saavedra | Oviedo          | Spain       |
| Supplier | Beate Vileid               | Sandvika        | Norway      |
| Supplier | Carlos Diaz                | São Paulo       | Brazil      |
| Supplier | Chandra Leka               | Singapore       | Singapore   |
| Supplier | Chantal Goulet             | Ste-Hyacinthe   | Canada      |
| Supplier | Charlotte Cooper           | Londona         | UK          |
| Supplier | Cheryl Saylor              | Bend            | USA         |
| Supplier | Dirk Luchte                | Zaandam         | Netherlands |
| Supplier | Eliane Noz                 | Annecy          | France      |
| Supplier | Elio Rossi                 | Ravenna         | Italy       |
| Supplier | Giovanni Giudici           | Salerno         | Italy       |
| Supplier | Guylène Nodier             | Paris           | France      |
| Supplier | Ian Devling                | Melbourne       | Australia   |
| Supplier | Jean-Guy Lauzon            | Montréal        | Canada      |
| Supplier | Lars Peterson              | Göteborg        | Sweden      |
| Supplier | Marie Delamare             | Montceau        | France      |
| Supplier | Martin Bein                | Frankfurt       | Germany     |
| Supplier | Mayumi Ohno                | Osaka           | Japan       |
| Supplier | Michael Björn              | Stockholm       | Sweden      |
| Supplier | Niels Petersen             | Lyngby          | Denmark     |
| Supplier | Peter Wilson               | Manchester      | UK          |
| Supplier | Petra Winkler              | Berlin          | Germany     |
| Supplier | Regina Murphy              | Ann Arbor       | USA         |
| Supplier | Robb Merchant              | Boston          | USA         |
| Supplier | Shelley Burke              | New Orleans     | USA         |
| Supplier | Sven Petersen              | Cuxhaven        | Germany     |
| Supplier | Wendy Mackenzie            | Sydney          | Australia   |
| Supplier | Yoshi Nagase               | Tokyo           | Japan       |

Notice the "AS Type" above - it is an alias. Aliases are used to give a column a temporary name. So, here we have created a temporary column named "Type", that list whether the contact person is a "Customer" or a "Supplier".

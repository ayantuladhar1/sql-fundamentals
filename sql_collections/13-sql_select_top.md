# SQL SELECT TOP, LIMIT and FETCH FIRST
The SELECT TOP clause is used to limit the number of records to return.

The SELECT TOP clause is useful on large tables with thousands of records.
Returning a large number of records can impact performance.

The following SQL selects only the first 3 records of the "Customers" table:

## Example:
Select only the first 3 records of the Customers table:
```sql
SELECT TOP 3 * FROM Customers;
```

| CustomerID | CustomerName                       | ContactName    | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | -------------- | ----------------------------- | ----------- | ---------- | ------- |
| 1          | Alfreds Futterkiste                | Maria Anders   | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo   | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno | Mataderos 2312                | México D.F. | 05023      | Mexico  |

Note: Not all database systems support the SELECT TOP clause. MySQL supports the LIMIT clause to select a limited number of records, while Oracle uses FETCH FIRST n ROWS ONLY.

## Syntax for SQL Server/MS Access
```sql
SELECT TOP number|percent column_name(s)
FROM table_name
WHERE condition;
```

## Syntax for MySQL
```sql
SELECT column_name(s)
FROM table_name
WHERE condition
LIMIT number;
```

## Syntax for Oracle 12+
```sql
SELECT column_name(s)
FROM table_name
ORDER BY column_name(s)
FETCH FIRST number ROWS ONLY;
```

## Demo Database
Below is a selection from the Customers table used in the examples:

| CustomerID | CustomerName                       | ContactName        | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | ------------------ | ----------------------------- | ----------- | ---------- | ------- |
| 1          | Alfreds Futterkiste                | Maria Anders       | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo       | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno     | Mataderos 2312                | México D.F. | 05023      | Mexico  |
| 4          | Around the Horn                    | Thomas Hardy       | 120 Hanover Sq.               | London      | WA1 1DP    | UK      |
| 5          | Berglunds snabbköp                 | Christina Berglund | Berguvsvägen 8                | Luleå       | S-958 22   | Sweden  |

## MySQL - The LIMIT Clause
The following SQL shows the equivalent examples for MySQL:

## Example:
Select the first 3 records of the Customers table:
```sql
SELECT * FROM Customers LIMIT 3;
```

| CustomerID | CustomerName                       | ContactName    | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | -------------- | ----------------------------- | ----------- | ---------- | ------- |
| 1          | Alfreds Futterkiste                | Maria Anders   | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo   | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno | Mataderos 2312                | México D.F. | 05023      | Mexico  |

## Oracle - The FETCH FIRST Clause
The following SQL shows the equivalent example for Oracle:

## Example:
Select the first 3 records of the Customers table:
```sql
SELECT * FROM Customers
FETCH FIRST 3 ROWS ONLY;
```

## SQL TOP PERCENT Example
Here we will use the SELECT TOP clause with the percent syntax.

The following SQL selects the first 50% of the records from the "Customers" table (for SQL Server/MS Access):

## Example:
```sql
SELECT TOP 50 PERCENT * FROM Customers;
```

| CustomerID | CustomerName                         | ContactName        | Address                                        | City           | PostalCode | Country     |
| ---------- | ------------------------------------ | ------------------ | ---------------------------------------------- | -------------- | ---------- | ----------- |
| 1          | Alfreds Futterkiste                  | Maria Anders       | Obere Str. 57                                  | Berlin         | 12209      | Germany     |
| 2          | Ana Trujillo Emparedados y helados   | Ana Trujillo       | Avda. de la Constitución 2222                  | México D.F.    | 05021      | Mexico      |
| 3          | Antonio Moreno Taquería              | Antonio Moreno     | Mataderos 2312                                 | México D.F.    | 05023      | Mexico      |
| 4          | Around the Horn                      | Thomas Hardy       | 120 Hanover Sq.                                | London         | WA1 1DP    | UK          |
| 5          | Berglunds snabbköp                   | Christina Berglund | Berguvsvägen 8                                 | Luleå          | S-958 22   | Sweden      |
| 6          | Blauer See Delikatessen              | Hanna Moos         | Forsterstr. 57                                 | Mannheim       | 68306      | Germany     |
| 7          | Blondel père et fils                 | Frédérique Citeaux | 24, place Kléber                               | Strasbourg     | 67000      | France      |
| 8          | Bólido Comidas preparadas            | Martín Sommer      | C/ Araquil, 67                                 | Madrid         | 28023      | Spain       |
| 9          | Bon app                              | Laurence Lebihans  | 12, rue des Bouchers                           | Marseille      | 13008      | France      |
| 10         | Bottom-Dollar Marketse               | Elizabeth Lincoln  | 23 Tsawassen Blvd.                             | Tsawassen      | T2F 8M4    | Canada      |
| 11         | Bs Beverages                         | Victoria Ashworth  | Fauntleroy Circus                              | London         | EC2 5NT    | UK          |
| 12         | Cactus Comidas para llevar           | Patricio Simpson   | Cerrito 333                                    | Buenos Aires   | 1010       | Argentina   |
| 13         | Centro comercial Moctezuma           | Francisco Chang    | Sierras de Granada 9993                        | México D.F.    | 05022      | Mexico      |
| 14         | Chop-suey Chinese                    | Yang Wang          | Hauptstr. 29                                   | Bern           | 3012       | Switzerland |
| 15         | Comércio Mineiro                     | Pedro Afonso       | Av. dos Lusíadas, 23                           | São Paulo      | 05432-043  | Brazil      |
| 16         | Consolidated Holdings                | Elizabeth Brown    | Berkeley Gardens 12 Brewery                    | London         | WX1 6LT    | UK          |
| 17         | Drachenblut Delikatessend            | Sven Ottlieb       | Walserweg 21                                   | Aachen         | 52066      | Germany     |
| 18         | Du monde entier                      | Janine Labrune     | 67, rue des Cinquante Otages                   | Nantes         | 44000      | France      |
| 19         | Eastern Connection                   | Ann Devon          | 35 King George                                 | London         | WX3 6FW    | UK          |
| 20         | Ernst Handel                         | Roland Mendel      | Kirchgasse 6                                   | Graz           | 8010       | Austria     |
| 21         | Familia Arquibaldo                   | Aria Cruz          | Rua Orós, 92                                   | São Paulo      | 05442-030  | Brazil      |
| 22         | FISSA Fabrica Inter. Salchichas S.A. | Diego Roel         | C/ Moralzarzal, 86                             | Madrid         | 28034      | Spain       |
| 23         | Folies gourmandes                    | Martine Rancé      | 184, chaussée de Tournai                       | Lille          | 59000      | France      |
| 24         | Folk och fä HB                       | Maria Larsson      | Åkergatan 24                                   | Bräcke         | S-844 67   | Sweden      |
| 25         | Frankenversand                       | Peter Franken      | Berliner Platz 43                              | München        | 80805      | Germany     |
| 26         | France restauration                  | Carine Schmitt     | 54, rue Royale                                 | Nantes         | 44000      | France      |
| 27         | Franchi S.p.A.                       | Paolo Accorti      | Via Monte Bianco 34                            | Torino         | 10100      | Italy       |
| 28         | Furia Bacalhau e Frutos do Mar       | Lino Rodriguez     | Jardim das rosas n. 32                         | Lisboa         | 1675       | Portugal    |
| 29         | Galería del gastrónomo               | Eduardo Saavedra   | Rambla de Cataluña, 23                         | Barcelona      | 08022      | Spain       |
| 30         | Godos Cocina Típica                  | José Pedro Freyre  | C/ Romero, 33                                  | Sevilla        | 41101      | Spain       |
| 31         | Gourmet Lanchonetes                  | André Fonseca      | Av. Brasil, 442                                | Campinas       | 04876-786  | Brazil      |
| 32         | Great Lakes Food Market              | Howard Snyder      | 2732 Baker Blvd.                               | Eugene         | 97403      | USA         |
| 33         | GROSELLA-Restaurante                 | Manuel Pereira     | 5ª Ave. Los Palos Grandes                      | Caracas        | 1081       | Venezuela   |
| 34         | Hanari Carnes                        | Mario Pontes       | Rua do Paço, 67                                | Rio de Janeiro | 05454-876  | Brazil      |
| 35         | HILARIÓN-Abastos                     | Carlos Hernández   | Carrera 22 con Ave. Carlos Soublette #8-35     | San Cristóbal  | 5022       | Venezuela   |
| 36         | Hungry Coyote Import Store           | Yoshi Latimer      | City Center Plaza 516 Main St.                 | Elgin          | 97827      | USA         |
| 37         | Hungry Owl All-Night Grocers         | Patricia McKenna   | 8 Johnstown Road                               | Cork           |            | Ireland     |
| 38         | Island Trading                       | Helen Bennett      | Garden House Crowther Way                      | Cowes          | PO31 7PJ   | UK          |
| 39         | Königlich Essen                      | Philip Cramer      | Maubelstr. 90                                  | Brandenburg    | 14776      | Germany     |
| 40         | La corne dabondance                  | Daniel Tonini      | 67, avenue de lEurope                          | Versailles     | 78000      | France      |
| 41         | La maison dAsie                      | Annette Roulet     | 1 rue Alsace-Lorraine                          | Toulouse       | 31000      | France      |
| 42         | Laughing Bacchus Wine Cellars        | Yoshi Tannamuri    | 1900 Oak St.                                   | Vancouver      | V3F 2K1    | Canada      |
| 43         | Lazy K Kountry Store                 | John Steel         | 12 Orchestra Terrace                           | Walla Walla    | 99362      | USA         |
| 44         | Lehmanns Marktstand                  | Renate Messner     | Magazinweg 7                                   | Frankfurt a.M. | 60528      | Germany     |
| 45         | Lets Stop N Shop                     | Jaime Yorres       | 87 Polk St. Suite 5                            | San Francisco  | 94117      | USA         |
| 46         | LILA-Supermercado                    | Carlos González    | Carrera 52 con Ave. Bolívar #65-98 Llano Largo | Barquisimeto   | 3508       | Venezuela   |

The following SQL shoes the equivalent examples for Oracle:

## Example:
```sql
SELECT * FROM Customers
FETCH FIRST 50 PERCENT ROWS ONLY;
```

## SELECT TOP with WHERE
The following SQL selects the first three records from the "Customers" table where Country is "Germany" (for SQL Server/MS Access):

## Example:
```sql
SELECT TOP 3 * FROM Customers
WHERE Country='Germany';
```

| CustomerID | CustomerName              | ContactName  | Address        | City     | PostalCode | Country |
| ---------- | ------------------------- | ------------ | -------------- | -------- | ---------- | ------- |
| 1          | Alfreds Futterkiste       | Maria Anders | Obere Str. 57  | Berlin   | 12209      | Germany |
| 6          | Blauer See Delikatessen   | Hanna Moos   | Forsterstr. 57 | Mannheim | 68306      | Germany |
| 17         | Drachenblut Delikatessend | Sven Ottlieb | Walserweg 21   | Aachen   | 52066      | Germany |



# SQL Self Join
A self join is a regular join, vut the table is joined with itself.

## Self Join Syntax
```sql
SELECT column_name(s)
FROM table1 T1, table1 T2
WHERE condition;
```

T1 and T2 are different table aliases for the same table.

## Demo Database
Below is a selection from the "Customers" table:

| CustomerID | CustomerName                       | ContactName    | Address                       | City        | PostalCode | Country |
| ---------- | ---------------------------------- | -------------- | ----------------------------- | ----------- | ---------- | ------- |
| 1          | Alfreds Futterkiste                | Maria Anders   | Obere Str. 57                 | Berlin      | 12209      | Germany |
| 2          | Ana Trujillo Emparedados y helados | Ana Trujillo   | Avda. de la Constitución 2222 | México D.F. | 05021      | Mexico  |
| 3          | Antonio Moreno Taquería            | Antonio Moreno | Mataderos 2312                | México D.F. | 05023      | Mexico  |

## SQL Self Join Example:
The following SQL statement matches customers that are from the same city:

## Example:
```sql
SELECT A.CustomerName AS CustomerName1, B.CustomerName AS CustomerName2, A.City
FROM Customers A, Customers B
WHERE A.CustomerID <> B.CustomerID
AND A.City = B.City 
ORDER BY A.City;
```

| CustomerName1                        | CustomerName2                        | City           |
| ------------------------------------ | ------------------------------------ | -------------- |
| Océano Atlántico Ltda.               | Rancho grande                        | Buenos Aires   |
| Océano Atlántico Ltda.               | Cactus Comidas para llevar           | Buenos Aires   |
| Rancho grande                        | Océano Atlántico Ltda.               | Buenos Aires   |
| Rancho grande                        | Cactus Comidas para llevar           | Buenos Aires   |
| Cactus Comidas para llevar           | Océano Atlántico Ltda.               | Buenos Aires   |
| Cactus Comidas para llevar           | Rancho grande                        | Buenos Aires   |
| Furia Bacalhau e Frutos do Mar       | Princesa Isabel Vinhoss              | Lisboa         |
| Princesa Isabel Vinhoss              | Furia Bacalhau e Frutos do Mar       | Lisboa         |
| Seven Seas Imports                   | North/South                          | London         |
| Seven Seas Imports                   | Eastern Connection                   | London         |
| Seven Seas Imports                   | Bs Beverages                         | London         |
| Seven Seas Imports                   | Consolidated Holdings                | London         |
| Seven Seas Imports                   | Around the Horn                      | London         |
| North/South                          | Seven Seas Imports                   | London         |
| North/South                          | Eastern Connection                   | London         |
| North/South                          | Bs Beverages                         | London         |
| North/South                          | Consolidated Holdings                | London         |
| North/South                          | Around the Horn                      | London         |
| Eastern Connection                   | Seven Seas Imports                   | London         |
| Eastern Connection                   | North/South                          | London         |
| Eastern Connection                   | Bs Beverages                         | London         |
| Eastern Connection                   | Consolidated Holdings                | London         |
| Eastern Connection                   | Around the Horn                      | London         |
| Bs Beverages                         | Seven Seas Imports                   | London         |
| Bs Beverages                         | North/South                          | London         |
| Bs Beverages                         | Eastern Connection                   | London         |
| Bs Beverages                         | Consolidated Holdings                | London         |
| Bs Beverages                         | Around the Horn                      | London         |
| Consolidated Holdings                | Seven Seas Imports                   | London         |
| Consolidated Holdings                | North/South                          | London         |
| Consolidated Holdings                | Eastern Connection                   | London         |
| Consolidated Holdings                | Bs Beverages                         | London         |
| Consolidated Holdings                | Around the Horn                      | London         |
| Around the Horn                      | Seven Seas Imports                   | London         |
| Around the Horn                      | North/South                          | London         |
| Around the Horn                      | Eastern Connection                   | London         |
| Around the Horn                      | Bs Beverages                         | London         |
| Around the Horn                      | Consolidated Holdings                | London         |
| Bólido Comidas preparadas            | FISSA Fabrica Inter. Salchichas S.A. | Madrid         |
| Bólido Comidas preparadas            | Romero y tomillo                     | Madrid         |
| FISSA Fabrica Inter. Salchichas S.A. | Bólido Comidas preparadas            | Madrid         |
| FISSA Fabrica Inter. Salchichas S.A. | Romero y tomillo                     | Madrid         |
| Romero y tomillo                     | Bólido Comidas preparadas            | Madrid         |
| Romero y tomillo                     | FISSA Fabrica Inter. Salchichas S.A. | Madrid         |
| Ana Trujillo Emparedados y helados   | Antonio Moreno Taquería              | México D.F.    |
| Ana Trujillo Emparedados y helados   | Centro comercial Moctezuma           | México D.F.    |
| Ana Trujillo Emparedados y helados   | Pericles Comidas clásicas            | México D.F.    |
| Ana Trujillo Emparedados y helados   | Tortuga Restaurante                  | México D.F.    |
| Antonio Moreno Taquería              | Ana Trujillo Emparedados y helados   | México D.F.    |
| Antonio Moreno Taquería              | Centro comercial Moctezuma           | México D.F.    |
| Antonio Moreno Taquería              | Pericles Comidas clásicas            | México D.F.    |
| Antonio Moreno Taquería              | Tortuga Restaurante                  | México D.F.    |
| Centro comercial Moctezuma           | Ana Trujillo Emparedados y helados   | México D.F.    |
| Centro comercial Moctezuma           | Antonio Moreno Taquería              | México D.F.    |
| Centro comercial Moctezuma           | Pericles Comidas clásicas            | México D.F.    |
| Centro comercial Moctezuma           | Tortuga Restaurante                  | México D.F.    |
| Pericles Comidas clásicas            | Ana Trujillo Emparedados y helados   | México D.F.    |
| Pericles Comidas clásicas            | Antonio Moreno Taquería              | México D.F.    |
| Pericles Comidas clásicas            | Centro comercial Moctezuma           | México D.F.    |
| Pericles Comidas clásicas            | Tortuga Restaurante                  | México D.F.    |
| Tortuga Restaurante                  | Ana Trujillo Emparedados y helados   | México D.F.    |
| Tortuga Restaurante                  | Antonio Moreno Taquería              | México D.F.    |
| Tortuga Restaurante                  | Centro comercial Moctezuma           | México D.F.    |
| Tortuga Restaurante                  | Pericles Comidas clásicas            | México D.F.    |
| France restauration                  | Du monde entier                      | Nantes         |
| Du monde entier                      | France restauration                  | Nantes         |
| Paris spécialités                    | Spécialités du monde                 | Paris          |
| Spécialités du monde                 | Paris spécialités                    | Paris          |
| Lonesome Pine Restaurant             | The Big Cheese                       | Portland       |
| The Big Cheese                       | Lonesome Pine Restaurant             | Portland       |
| Ricardo Adocicados                   | Que Delícia                          | Rio de Janeiro |
| Ricardo Adocicados                   | Hanari Carnes                        | Rio de Janeiro |
| Que Delícia                          | Ricardo Adocicados                   | Rio de Janeiro |
| Que Delícia                          | Hanari Carnes                        | Rio de Janeiro |
| Hanari Carnes                        | Ricardo Adocicados                   | Rio de Janeiro |
| Hanari Carnes                        | Que Delícia                          | Rio de Janeiro |
| Queen Cozinha                        | Familia Arquibaldo                   | São Paulo      |
| Queen Cozinha                        | Comércio Mineiro                     | São Paulo      |
| Queen Cozinha                        | Tradição Hipermercados               | São Paulo      |
| Familia Arquibaldo                   | Queen Cozinha                        | São Paulo      |
| Familia Arquibaldo                   | Comércio Mineiro                     | São Paulo      |
| Familia Arquibaldo                   | Tradição Hipermercados               | São Paulo      |
| Comércio Mineiro                     | Queen Cozinha                        | São Paulo      |
| Comércio Mineiro                     | Familia Arquibaldo                   | São Paulo      |
| Comércio Mineiro                     | Tradição Hipermercados               | São Paulo      |
| Tradição Hipermercados               | Queen Cozinha                        | São Paulo      |
| Tradição Hipermercados               | Familia Arquibaldo                   | São Paulo      |
| Tradição Hipermercados               | Comércio Mineiro                     | São Paulo      |


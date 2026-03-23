# SQL RIGHT JOIN
The RIGHT JOIN returns all rows from the right table (table2), and only the matched rows from the left table (table1).

If there is no match in the left table, the result for the columns from the left table will be NULL.

The RIGHT JOIN and RIGHT OUTER JOIN keywords are equal - the OUTER keyword is optional.

<img width="276" height="185" alt="image" src="https://github.com/user-attachments/assets/bf8d33af-b06c-4658-8d4d-b02a04e6c8cf" />

## RIGHT JOIN Syntax
```sql
SELECT column_name(s)
FROM table1
RIGHT JOIN table2
ON table1.column_name = table2.column_name;
```

## Demo Database
Below is a selection from the "Orders" table:

| OrderID | CustomerID | EmployeeID | OrderDate  | ShipperID |
| ------- | ---------- | ---------- | ---------- | --------- |
| 10308   | 2          | 7          | 1996-09-18 | 3         |
| 10309   | 37         | 3          | 1996-09-19 | 1         |
| 10310   | 77         | 8          | 1996-09-20 | 2         |

And a selection from the "Employees" table:

| EmployeeID | LastName  | FirstName | BirthDate | Photo      |
| ---------- | --------- | --------- | --------- | ---------- |
| 1          | Davolio   | Nancy     | 12/8/1968 | EmpID1.pic |
| 2          | Fuller    | Andrew    | 2/19/1952 | EmpID2.pic |
| 3          | Leverling | Janet     | 8/30/1963 | EmpID3.pic |

## SQL RIGHT JOIN Example:
The following SQL will return all employees, and any orders they might have placed:

## Example:
```sql
SELECT Orders.OrderID, Employees.LastName, Employees.FirstName
FROM Orders
RIGHT JOIN Employees
ON Orders.EmployeeID = Employees.EmployeeID
ORDER BY Orders.OrderID;
```

| OrderID | LastName  | FirstName |
| ------- | --------- | --------- |
|         | West      | Adam      |
| 10248   | Buchanan  | Steven    |
| 10249   | Suyama    | Michael   |
| 10250   | Peacock   | Margaret  |
| 10251   | Leverling | Janet     |
| 10252   | Peacock   | Margaret  |
| 10253   | Leverling | Janet     |
| 10254   | Buchanan  | Steven    |
| 10255   | Dodsworth | Anne      |
| 10256   | Leverling | Janet     |
| 10257   | Peacock   | Margaret  |
| 10258   | Davolio   | Nancy     |
| 10259   | Peacock   | Margaret  |
| 10260   | Peacock   | Margaret  |
| 10261   | Peacock   | Margaret  |
| 10262   | Callahan  | Laura     |
| 10263   | Dodsworth | Anne      |
| 10264   | Suyama    | Michael   |
| 10265   | Fuller    | Andrew    |
| 10266   | Leverling | Janet     |
| 10267   | Peacock   | Margaret  |
| 10268   | Callahan  | Laura     |
| 10269   | Buchanan  | Steven    |
| 10270   | Davolio   | Nancy     |
| 10271   | Suyama    | Michael   |
| 10272   | Suyama    | Michael   |
| 10273   | Leverling | Janet     |
| 10274   | Suyama    | Michael   |
| 10275   | Davolio   | Nancy     |
| 10276   | Callahan  | Laura     |
| 10277   | Fuller    | Andrew    |
| 10278   | Callahan  | Laura     |
| 10279   | Callahan  | Laura     |
| 10280   | Fuller    | Andrew    |
| 10281   | Peacock   | Margaret  |
| 10282   | Peacock   | Margaret  |
| 10283   | Leverling | Janet     |
| 10284   | Peacock   | Margaret  |
| 10285   | Davolio   | Nancy     |
| 10286   | Callahan  | Laura     |
| 10287   | Callahan  | Laura     |
| 10288   | Peacock   | Margaret  |
| 10289   | King      | Robert    |
| 10290   | Callahan  | Laura     |
| 10291   | Suyama    | Michael   |
| 10292   | Davolio   | Nancy     |
| 10293   | Davolio   | Nancy     |
| 10294   | Peacock   | Margaret  |
| 10295   | Fuller    | Andrew    |
| 10296   | Suyama    | Michael   |
| 10297   | Buchanan  | Steven    |
| 10298   | Suyama    | Michael   |
| 10299   | Peacock   | Margaret  |
| 10300   | Fuller    | Andrew    |
| 10301   | Callahan  | Laura     |
| 10302   | Peacock   | Margaret  |
| 10303   | King      | Robert    |
| 10304   | Davolio   | Nancy     |
| 10305   | Callahan  | Laura     |
| 10306   | Davolio   | Nancy     |
| 10307   | Fuller    | Andrew    |
| 10308   | King      | Robert    |
| 10309   | Leverling | Janet     |
| 10310   | Callahan  | Laura     |
| 10311   | Davolio   | Nancy     |
| 10312   | Fuller    | Andrew    |
| 10313   | Fuller    | Andrew    |
| 10314   | Davolio   | Nancy     |
| 10315   | Peacock   | Margaret  |
| 10316   | Davolio   | Nancy     |
| 10317   | Suyama    | Michael   |
| 10318   | Callahan  | Laura     |
| 10319   | King      | Robert    |
| 10320   | Buchanan  | Steven    |
| 10321   | Leverling | Janet     |
| 10322   | King      | Robert    |
| 10323   | Peacock   | Margaret  |
| 10324   | Dodsworth | Anne      |
| 10325   | Davolio   | Nancy     |
| 10326   | Peacock   | Margaret  |
| 10327   | Fuller    | Andrew    |
| 10328   | Peacock   | Margaret  |
| 10329   | Peacock   | Margaret  |
| 10330   | Leverling | Janet     |
| 10331   | Dodsworth | Anne      |
| 10332   | Leverling | Janet     |
| 10333   | Buchanan  | Steven    |
| 10334   | Callahan  | Laura     |
| 10335   | King      | Robert    |
| 10336   | King      | Robert    |
| 10337   | Peacock   | Margaret  |
| 10338   | Peacock   | Margaret  |
| 10339   | Fuller    | Andrew    |
| 10340   | Davolio   | Nancy     |
| 10341   | King      | Robert    |
| 10342   | Peacock   | Margaret  |
| 10343   | Peacock   | Margaret  |
| 10344   | Peacock   | Margaret  |
| 10345   | Fuller    | Andrew    |
| 10346   | Leverling | Janet     |
| 10347   | Peacock   | Margaret  |
| 10348   | Peacock   | Margaret  |
| 10349   | King      | Robert    |
| 10350   | Suyama    | Michael   |
| 10351   | Davolio   | Nancy     |
| 10352   | Leverling | Janet     |
| 10353   | King      | Robert    |
| 10354   | Callahan  | Laura     |
| 10355   | Suyama    | Michael   |
| 10356   | Suyama    | Michael   |
| 10357   | Davolio   | Nancy     |
| 10358   | Buchanan  | Steven    |
| 10359   | Buchanan  | Steven    |
| 10360   | Peacock   | Margaret  |
| 10361   | Davolio   | Nancy     |
| 10362   | Leverling | Janet     |
| 10363   | Peacock   | Margaret  |
| 10364   | Davolio   | Nancy     |
| 10365   | Leverling | Janet     |
| 10366   | Callahan  | Laura     |
| 10367   | King      | Robert    |
| 10368   | Fuller    | Andrew    |
| 10369   | Callahan  | Laura     |
| 10370   | Suyama    | Michael   |
| 10371   | Davolio   | Nancy     |
| 10372   | Buchanan  | Steven    |
| 10373   | Peacock   | Margaret  |
| 10374   | Davolio   | Nancy     |
| 10375   | Leverling | Janet     |
| 10376   | Davolio   | Nancy     |
| 10377   | Davolio   | Nancy     |
| 10378   | Buchanan  | Steven    |
| 10379   | Fuller    | Andrew    |
| 10380   | Callahan  | Laura     |
| 10381   | Leverling | Janet     |
| 10382   | Peacock   | Margaret  |
| 10383   | Callahan  | Laura     |
| 10384   | Leverling | Janet     |
| 10385   | Davolio   | Nancy     |
| 10386   | Dodsworth | Anne      |
| 10387   | Davolio   | Nancy     |
| 10388   | Fuller    | Andrew    |
| 10389   | Peacock   | Margaret  |
| 10390   | Suyama    | Michael   |
| 10391   | Leverling | Janet     |
| 10392   | Fuller    | Andrew    |
| 10393   | Davolio   | Nancy     |
| 10394   | Davolio   | Nancy     |
| 10395   | Suyama    | Michael   |
| 10396   | Davolio   | Nancy     |
| 10397   | Buchanan  | Steven    |
| 10398   | Fuller    | Andrew    |
| 10399   | Callahan  | Laura     |
| 10400   | Davolio   | Nancy     |
| 10401   | Davolio   | Nancy     |
| 10402   | Callahan  | Laura     |
| 10403   | Peacock   | Margaret  |
| 10404   | Fuller    | Andrew    |
| 10405   | Davolio   | Nancy     |
| 10406   | King      | Robert    |
| 10407   | Fuller    | Andrew    |
| 10408   | Callahan  | Laura     |
| 10409   | Leverling | Janet     |
| 10410   | Leverling | Janet     |
| 10411   | Dodsworth | Anne      |
| 10412   | Callahan  | Laura     |
| 10413   | Leverling | Janet     |
| 10414   | Fuller    | Andrew    |
| 10415   | Leverling | Janet     |
| 10416   | Callahan  | Laura     |
| 10417   | Peacock   | Margaret  |
| 10418   | Peacock   | Margaret  |
| 10419   | Peacock   | Margaret  |
| 10420   | Leverling | Janet     |
| 10421   | Callahan  | Laura     |
| 10422   | Fuller    | Andrew    |
| 10423   | Suyama    | Michael   |
| 10424   | King      | Robert    |
| 10425   | Suyama    | Michael   |
| 10426   | Peacock   | Margaret  |
| 10427   | Peacock   | Margaret  |
| 10428   | King      | Robert    |
| 10429   | Leverling | Janet     |
| 10430   | Peacock   | Margaret  |
| 10431   | Peacock   | Margaret  |
| 10432   | Leverling | Janet     |
| 10433   | Leverling | Janet     |
| 10434   | Leverling | Janet     |
| 10435   | Callahan  | Laura     |
| 10436   | Leverling | Janet     |
| 10437   | Callahan  | Laura     |
| 10438   | Leverling | Janet     |
| 10439   | Suyama    | Michael   |
| 10440   | Peacock   | Margaret  |
| 10441   | Leverling | Janet     |
| 10442   | Leverling | Janet     |
| 10443   | Callahan  | Laura     |

Note: The RIGHT JOIN keyword returns all records from the right table (Employees), even if there are no matches in the left table (Orders).

# SQL Operators
SQL operators are keywords and symbols used to perform operations with data values.

SQL operators are used in SQL statements like SELECT, WHERE, LIKE, etc.

SQL operator is categorized into the following types:
* Airthmetic operators
* Comparison operators
* Compound operators
* Bitwise operators
* Logical operators

## SQL Airthmetic Operators

| Operator | Description    | 
| -------- | -------------- | 
| +        | Addition       |         
| \-       | Subtraction    |         
| \*       | Multiplication |         
| /        | Division       |         
| %        | Modulus        |

```sql
SELECT 30 + 20;
```

50

## SQL Comparison Operators

| Operator | Description              |
| -------- | ------------------------ | 
| \=       | Equal to                 |         
| \>       | Greater than             |         
| <        | Less than                |         
| \>=      | Greater than or equal to |         
| <=       | Less than or equal to    |         
| <>       | Not equal to             |

```sql
SELECT * FROM Products
WHERE Price = 18;
```

| ProductID | ProductName      | SupplierID | CategoryID | Unit               | Price |
| --------- | ---------------- | ---------- | ---------- | ------------------ | ----- |
| 1         | Chais            | 1          | 1          | 10 boxes x 20 bags | 18.00 |
| 35        | Steeleye Stout   | 16         | 1          | 24 - 12 oz bottles | 18.00 |
| 39        | Chartreuse verte | 18         | 1          | 750 cc per bottle  | 18.00 |
| 76        | Lakkalikööri     | 23         | 1          | 500 ml             | 18.00 |

## SQL Compound Operators

| Operator | Description              |
| -------- | ------------------------ |
| +=       | Add equals               |
| \-=      | Subtract equals          |
| \*=      | Multiply equals          |
| /=       | Divide equals            |
| %=       | Modulo equals            |
| &=       | Bitwise AND equals       |
| ^=       | Bitwise exclusive equals |
| \|\*=    | Bitwise OR equals        |

## SQL Bitwise Operators

| Operator | Description          |
| -------- | -------------------- |
| &        | Bitwise AND          |
| \|       | Bitwise OR           |
| ^        | Bitwise exclusive OR |
| ~        | Bitwise NOT          |

## SQL Logical Operators

| Operator | Description                                                  |
| -------- | ------------------------------------------------------------ |
| ALL      | TRUE if all of the subquery values meet the condition        |
| AND      | TRUE if all the conditions separated by AND is TRUE          |
| ANY      | TRUE if any of the subquery values meet the condition        |
| BETWEEN  | TRUE if the operand is within the range of comparisons       |
| EXISTS   | TRUE if the subquery returns one or more records             |
| IN       | TRUE if the operand is equal to one of a list of expressions |
| LIKE     | TRUE if the operand matches a pattern                        |
| NOT      | Displays a record if the condition(s) is NOT TRUE            |
| OR       | TRUE if any of the conditions separated by OR is TRUE        |
| SOME     | TRUE if any of the subquery values meet the condition        |


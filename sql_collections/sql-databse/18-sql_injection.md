# SQL Injection
SQL injection is a code injection technique that can destroy your database. SQL injections are a common web hacking techniquw.

SQL injections are when attackers insert malicious SQL code into user-input fields, and this way can read, modify, or delete sensitive data in a database.

SQL injections usually occur when you ask a user for input, like username/userid, and instead of giving a name/id, the attacker inserts and SQL command that executes something in your database.

Look at the following example which creates a SELECT statement by adding a variable (txtUserId) to a select string. The variable is fetched from user input (getRequestString):

## Example:
```sql
txtUserId = getRequestString("UserId");
txtSQL = "SELECT * FROM Users WHERE UserId = " + txtUserId;
```

The rest of this chapter describes the potential dangers of using user input in SQL statements.

The next chapters show the most effective methods to prevent SQL injections, using SQL Parameters and SQL Prepared Statements.

## SQL Injection Based on 1 = 1 is Always True
Look at the example above again. The original purpose of the SQL code was to select a user with a given user id.

If there is nothing to prevent a user from entering "wrong" input, the user can enter some "smart" input like this:

UserId: 105 OR 1=1

Then, the SQL statement will look like this:
```sql
SELECT * FROM Users WHERE UserId = 105 OR 1=1;
```

The SQL above is valid and will return ALL rows from the "Users" table, since OR 1 = 1 is always TRUE.

Does the example above look dangerous? What if the "Users" table contains names and passwords?

A hacker might get access to all the users and passwords in a database, by simply inserting 105 OR 1 = 1 into the input field.

## SQL Injection Based on OR ""="" is Always True
Here is an example of a user login on a web site:

Username:
John Doe

Password:
myPass

## Example:
```sql
uName = getRequestString("username");
uPass = getRequestString("userpassword");

sql = 'SELECT * FROM Users WHERE Name ="' + uName + '" AND Pass ="' + uPass + '"'
```

## Result:
```sql
SELECT * FROM Users WHERE Name ="John Doe" AND Pass ="myPass"
```

A hacker might get access to user names and passwords in a database by simply inserting "OR" "=" into the user name or password text box:

UserName:
"or""="

Password:
"or""="

The SQL statement will now look like this:

## Result:
```sql
SELECT * FROM Users WHERE Name ="" or ""="" AND Pass ="" or ""=""
```

## SQL Injection From Batched SQL Statements
Batched SQL statements is a group of two or more SQL statements, separated by semicolons.

The SQL statement below will return all rows from the "Users" table, then delete the "Suppliers" table.

## Example:
```sql
SELECT * FROM Users; DROP TABLE Suppliers;
```

Look at the following example:

## Example:
```sql
txtUserId = getRequestString("UserId");
txtSQL = "SELECT * FROM Users WHERE UserId = " + txtUserId;
```

And the following input:
User id: 105; DROP TABLE Suppliers

The valid SQL statements would look like this:

## Result
```sql
SELECT * FROM Users WHERE UserId = 105; DROP TABLE Suppliers;
```

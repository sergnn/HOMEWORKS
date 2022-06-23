[![N|Solid](https://upload.wikimedia.org/wikipedia/commons/3/3e/W3Schools_logo.png)](https://www.w3schools.com/sql/default.asp)

# SQL Tutorial. Exercises
## _SQL SELECT_

##### 1. Insert the missing statement to get all the columns from the **Customers** table
```sql
SELECT * FROM Customers;
```
##### 2. Write a statement that will select the City column from the **Customers** table
```sql
SELECT City FROM Customers;
```
##### 3. Select all the different values from the Country column in the **Customers** table
```sql
SELECT DISTINCT Country FROM Customers;
```
## _SQL WHERE_
##### 1. Select all records where the City column has the value "Berlin"
```sql
SELECT * FROM Customers WHERE CITY = 'BERLIN';
```
##### 2. Use the NOT keyword to select all records where City is NOT "Berlin"
```sql
SELECT * FROM Customers WHERE NOT CITY = 'BERLIN';
```
##### 3. Select all records where the CustomerID column has the value 32
```sql
SELECT * FROM Customers WHERE CustomerID = 32;
```
##### 4. Select all records where the City column has the value 'Berlin' and the PostalCode column has the value 12209
```sql
SELECT * FROM Customers WHERE City = 'Berlin' AND POSTALCODE = 12209;
```
##### 5. Select all records where the City column has the value 'Berlin' or 'London'
```sql
SELECT * FROM Customers WHERE City = 'Berlin' OR CITY = 'LONDON';
```
## _SQL ORDER BY_
##### 1. Select all records from the Customers table, sort the result alphabetically by the column City
```sql
SELECT * FROM Customers ORDER BY CITY;
```
##### 2. Select all records from the Customers table, sort the result reversed alphabetically by the column City
```sql
SELECT * FROM Customers ORDER BY CITY DESC;
```
##### 3. Select all records from the Customers table, sort the result alphabetically, first by the column Country, then, by the column City
```sql
SELECT * FROM Customers ORDER BY COUNTRY, CITY;
```
## _SQL INSERT_
##### 1. Insert a new record in the Customers table
```sql
INSERT INTO Customers (CustomerName, Address, City, PostalCode,Country)
VALUES ('Hekkan Burger','Gateveien 15','Sandnes','4306','Norway');
```

## _SQL NULL_
##### 1. Select all records from the Customers where the PostalCode column is empty
```sql
SELECT * FROM Customers WHERE POSTALCODE IS NULL;
```
##### 2. Select all records from the Customers where the PostalCode column is NOT empty
```sql
SELECT * FROM Customers WHERE POSTALCODE IS NOT NULL;
```

## _SQL UPDATE_
##### 1. Update the City column of all records in the Customers table
```sql
UPDATE Customers SET City = 'Oslo';
```
##### 2. Set the value of the City columns to 'Oslo', but only the ones where the Country column has the value "Norway"
```sql
UPDATE Customers SET City = 'Oslo' WHERE Country = 'Norway';
```
##### 3. Update the City value and the Country value
```sql
UPDATE Customers SET City = 'Oslo', COUNTRY = 'Norway' WHERE CustomerID = 32;
```

## _SQL DELETE_
##### 1. Delete all the records from the Customers table where the Country value is 'Norway'
```sql
DELETE FROM Customers WHERE Country = 'Norway';
```
##### 2. Delete all the records from the Customers table
```sql
DELETE FROM Customers;
```

## _SQL FUNCTIONS_
##### 1. Use the MIN function to select the record with the smallest value of the Price column
```sql
SELECT MIN(PRICE) FROM Products;
```
##### 2. Use an SQL function to select the record with the highest value of the Price column
```sql
SELECT MAX(PRICE) FROM Products;
```
##### 3. Use the correct function to return the number of records that have the Price value set to 18
```sql
SELECT COUNT(*) FROM Products WHERE Price = 18;
```
##### 4. Use an SQL function to calculate the average price of all products
```sql
SELECT AVG(PRICE) FROM Products;
```
##### 5. Use an SQL function to calculate the sum of all the Price column values in the Products table
```sql
SELECT SUM(PRICE) FROM Products;
```

## _SQL LIKE_
##### 1. Select all records where the value of the City column starts with the letter "a"
```sql
SELECT * FROM Customers WHERE CITY LIKE 'a%';
```
##### 2. Select all records where the value of the City column ends with the letter "a"
```sql
SELECT * FROM Customers WHERE CITY LIKE '%a';
```
##### 3. Select all records where the value of the City column contains the letter "a"
```sql
SELECT * FROM Customers WHERE CITY LIKE '%a%';
```
##### 4. Select all records where the value of the City column starts with letter "a" and ends with the letter "b"
```sql
SELECT * FROM Customers WHERE CITY LIKE 'a%b';
```
##### 5. Select all records where the value of the City column does NOT start with the letter "a"
```sql
SELECT * FROM Customers WHERE CITY NOT LIKE 'a%';
```

## _SQL WILDCARDS_
##### 1. Select all records where the second letter of the City is an "a"
```sql
SELECT * FROM Customers WHERE City LIKE '?a%';
```
##### 2. Select all records where the first letter of the City is an "a" or a "c" or an "s"
```sql
SELECT * FROM Customers WHERE City LIKE '[acs]%';
```
##### 3. Select all records where the first letter of the City starts with anything from an "a" to an "f"
```sql
SELECT * FROM Customers WHERE City LIKE '[a-f]%';
```
##### 4. Select all records where the first letter of the City is NOT an "a" or a "c" or an "f"
```sql
SELECT * FROM Customers WHERE City LIKE '[!acf]%';
```

## _SQL IN_
##### 1. Use the IN operator to select all the records where Country is either "Norway" or "France"
```sql
SELECT * FROM Customers WHERE COUNTRY IN ('NORWAY', 'France');
```
##### 2. Use the IN operator to select all the records where Country is NOT "Norway" and NOT "France"
```sql
SELECT * FROM Customers WHERE COUNTRY NOT IN ('NORWAY', 'France');
```

## _SQL BETWEEN_
##### 1. Use the BETWEEN operator to select all the records where the value of the Price column is between 10 and 20
```sql
SELECT * FROM Products WHERE Price BETWEEN 10 AND 20;
```
##### 2. Use the BETWEEN operator to select all the records where the value of the Price column is NOT between 10 and 20
```sql
SELECT * FROM Products WHERE Price NOT BETWEEN 10 AND 20;
```
##### 3. Use the BETWEEN operator to select all the records where the value of the ProductName column is alphabetically between 'Geitost' and 'Pavlova'
```sql
SELECT * FROM Products WHERE ProductName BETWEEN 'GEITOST' AND 'PAVLOVA';
```

## _SQL ALIAS_
##### 1. When displaying the Customers table, make an ALIAS of the PostalCode column, the column should be called Pno instead
```sql
SELECT CustomerName, Address, PostalCode AS PNO FROM Customers;
```
##### 2. When displaying the Customers table, refer to the table as Consumers instead of Customers
```sql
SELECT * FROM Customers AS CONSUMERS;
```

## _SQL JOIN_
##### 1. Insert the missing parts in the JOIN clause to join the two tables Orders and Customers, using the CustomerID field in both tables as the relationship between the two tables
```sql
SELECT * FROM Orders LEFT JOIN Customers ON ORDERS.CUSTOMERID = CUSTOMERS.CUSTOMERID;
```
##### 2. Choose the correct JOIN clause to select all records from the two tables where there is a match in both tables
```sql
SELECT * FROM Orders INNER JOIN CUSTOMERS ON Orders.CustomerID=Customers.CustomerID;
```
##### 3. Choose the correct JOIN clause to select all the records from the Customers table plus all the matches in the Orders table
```sql
SELECT * FROM Orders RIGHT JOIN CUSTOMERS ON Orders.CustomerID=Customers.CustomerID;
```
## _SQL GROUP BY_
##### 1. List the number of customers in each country
```sql
SELECT COUNT(CustomerID), Country FROM Customers GROUP BY COUNTRY;
```
##### 2. List the number of customers in each country, ordered by the country with the most customers first
```sql
SELECT COUNT(CustomerID), Country FROM Customers 
GROUP BY Country 
ORDER BY COUNT(CustomerID) DESC;
```

## _SQL DATABASE_
##### 1. Write the correct SQL statement to create a new database called testDB
```sql
CREATE DATABASE TESTDB;
```
##### 2. Write the correct SQL statement to delete a database named testDB.
```sql
DROP DATABASE TESTDB;
```
##### 3. Write the correct SQL statement to create a new table called Persons
```sql
CREATE TABLE PERSONS (PersonID int, LastName varchar(255), FirstName varchar(255), Address varchar(255), City varchar(255));
```
##### 4. Write the correct SQL statement to delete a table called Persons
```sql
DROP TABLE Persons;
```
##### 5. Use the TRUNCATE statement to delete all data inside a table
```sql
TRUNCATE TABLE Persons;
```
##### 6. Add a column of type DATE called Birthday
```sql
ALTER TABLE Persons ADD Birthday DATE;
```
##### 7. Delete the column Birthday from the Persons table
```sql
ALTER TABLE Persons DROP COLUMN Birthday;
```



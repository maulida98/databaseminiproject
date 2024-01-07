![image](https://github.com/maulida98/databaseminiproject/assets/106392408/25ca7def-d4da-430f-8174-08d2441d2b6a)# databaseminiproject
A tutorial for database mini project for beginner

First, we will make a database with Oracle. This is pretty simple, but if you're confused with Oracle, let me show you the steps. Before you try this tutorial, you have to download Oracle on your PC first.
Open the oracle "Go To Database" on your search bar, there will be appeard a website of oracle. You have to create an account / database to login to Oracle. After you entered the system, you can go 'Home' > 'Administration' > 'Manage Database User'> 'Create Database User' , and then you'll find the 'create database user' page to create a database. You can use your creativity for database name, but make sure that the database is familiar to you, don't be so serious because this is only a tutorial for beginner, right ? Enjoy the moment!

![image](https://github.com/maulida98/databaseminiproject/assets/106392408/8076435a-44e0-40ce-8667-c55e1055879d)

For example, mine is 'ecommerce' database. Why ? Because I love shopping ! LOL
Let us talk about shopping, what kind of activity when we want to shopping online ? Sure, we have to create an account first. Then, the first table we have to create is 'users' table, right?
Let's create our first table !

CREATE TABLE Customers (
  CustomerID INT PRIMARY KEY,
  CustomerName VARCHAR(50),
  Email VARCHAR(50) UNIQUE,
  Address VARCHAR(255)
);



After that, what's next ? Of course the item or the product that suppliers want to show. Let's make a display on our shopping ecommerce database !

CREATE TABLE Products (
  ProductID INT PRIMARY KEY,
  ProductName VARCHAR(50) UNIQUE,
  Description VARCHAR(255),
  Price DECIMAL(10, 2) CHECK (Price >= 0)
);


Wait, are you confused? Why we use VARCHAR2 rather than VARCHAR or CHAR ? because, as I said before that we use Oracle in here. Oracle can use VARCHAR2 that I want you to remember that, that's why I use that. But, that's optional whether you use that or the other methode it's okay as long as it's running.

Then, after that we can create one more table for mix both table.

CREATE TABLE Orders (
  OrderID INT PRIMARY KEY,
  CustomerID INT,
  OrderDate DATE CHECK (OrderDate <= CURRENT_DATE),
  Status VARCHAR(20),
  FOREIGN KEY (CustomerID) REFERENCES Customers(CustomerID)
);


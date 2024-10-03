# ECommerce Database Management System
_Problem Statement_

This project focuses on managing an e-commerce database that handles key data for customers, orders, products, suppliers, and order details. The primary goal is to efficiently manage customer orders, product inventory, and supplier relationships. The database tracks the following:

- Customers and their personal information.
- Orders placed by customers, including order dates and total amounts.
- Products, with details such as price, stock levels, and supplier information.
- OrderDetails specifying the products included in each order.
- Suppliers who provide the products.
The database facilitates seamless querying for order processing, inventory management, and supplier coordination, ensuring smooth operations for both system administrators and users. 

# SQL Commands Executed
1. Table Creation:
The following tables were created to store essential data:

- Customers Table: Stores customer details like name, email, and phone number.
- Orders Table: Contains order details and includes a foreign key referencing the Customers table.
- Products Table: Holds product details such as name, price, and category.
- OrderDetails Table: Links orders to the specific products, joining the Orders and Products tables.
- Suppliers Table: Contains supplier information for the products.
- ProductSuppliers Table: Manages the many-to-many relationship between products and their suppliers.

SQL Example for Creating the Customers Table:

CREATE TABLE Customers (
    CustomerID NUMBER PRIMARY KEY,
    FirstName VARCHAR2(50),
    LastName VARCHAR2(50),
    Email VARCHAR2(100),
    Phone VARCHAR2(15)
);

2. Inserting Data:
Data was added to all tables using the INSERT INTO command. Below is an example of inserting customer data into the Customers table:

SQL Example for Inserting Data into Customers Table:

INSERT INTO Customers (CustomerID, FirstName, LastName, Email, Phone) VALUES 
(1, 'Kevin', 'Nshuti', 'nshutikevin@gmail.com', '0788956407');

INSERT INTO Customers (CustomerID, FirstName, LastName, Email, Phone) VALUES 
(2, 'Fabrice', 'Mucyo', 'mutabazi@gmail.com', '0783123333');

3. Querying the Database:
SQL queries were used to retrieve various information, such as customer orders and product details. An example of a JOIN query to fetch customer orders is shown below:

SQL Example for Retrieving Customer Orders:

SELECT c.FirstName, c.LastName, o.OrderID, o.OrderDate, o.TotalAmount
FROM Customers c
JOIN Orders o ON c.CustomerID = o.CustomerID;

4. Updating Data:
The UPDATE command was used to modify existing data. For instance, updating a customer’s email address:

SQL Example for Updating a Customer’s Email:

UPDATE Customers
SET Email = 'nshkev808@gmail.com'
WHERE CustomerID = 1;

5. Deleting Data:
The DELETE command was utilized to remove records from tables. An example of deleting an order is provided below:

SQL Example for Deleting an Order:

DELETE FROM Orders
WHERE OrderID = 102;



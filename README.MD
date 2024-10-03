# E-Commerce Database Management System

## Problem Statement
This project focuses on managing an e-commerce database that handles key data for customers, orders, products, suppliers, and order details. The primary goal is to efficiently manage customer orders, product inventory, and supplier relationships. The database tracks the following:

- **Customers** and their personal information.
- **Orders** placed by customers, including order dates and total amounts.
- **Products**, with details such as price, stock levels, and supplier information.
- **OrderDetails** specifying the products included in each order.
- **Suppliers** who provide the products.

The database facilitates seamless querying for order processing, inventory management, and supplier coordination, ensuring smooth operations for both system administrators and users.

## SQL Commands Executed

### 1. Table Creation

The following tables were created to store essential data:

- **Customers Table**: Stores customer details like name, email, and phone number.
- **Orders Table**: Contains order details and includes a foreign key referencing the Customers table.
- **Products Table**: Holds product details such as name, price, and category.
- **OrderDetails Table**: Links orders to the specific products, joining the Orders and Products tables.
- **Suppliers Table**: Contains supplier information for the products.
- **ProductSuppliers Table**: Manages the many-to-many relationship between products and their suppliers.

#### Example SQL for Creating the Customers Table:

```sql
CREATE TABLE Customers (
    CustomerID NUMBER PRIMARY KEY,
    FirstName VARCHAR2(50),
    LastName VARCHAR2(50),
    Email VARCHAR2(100),
    Phone VARCHAR2(15)
);

## 2. Inserting Data

Data was added to all tables using the `INSERT INTO` command. Below is an example of inserting customer data into the Customers table:

### Example SQL for Inserting Data into Customers Table:
```sql
INSERT INTO Customers (CustomerID, FirstName, LastName, Email, Phone) VALUES 
(1, 'kevin', 'nshuti', 'nshutikeevin@gmail.com', '0788956407');

INSERT INTO Customers (CustomerID, FirstName, LastName, Email, Phone) VALUES 
(2, 'Fabrice', 'Mucyo', 'mutabazi@gmail.com', '0783123333');

## 3. Querying the Database

Queries were performed to extract data such as customer orders and product details. The following example demonstrates a `JOIN` query that retrieves customer orders.

### Example SQL for Retrieving Customer Orders:
```sql
SELECT c.FirstName, c.LastName, o.OrderID, o.OrderDate, o.TotalAmount
FROM Customers c
JOIN Orders o ON c.CustomerID = o.CustomerID;

## 4. Data updating. 

The `UPDATE` command was utilized to change existing records in the database. For example, the following query updates a customer’s email address:

### Example SQL for Updating a Customer’s Email:

UPDATE Customers
SET Email = 'john.doe.update@example.com'
WHERE CustomerID = 1;

## 5. Deleting Data

The `DELETE` command was used to remove specific records from the tables. Below is an example of how to delete an order:

### Example SQL for Deleting an Order:
```sql
DELETE FROM Orders
WHERE OrderID = 102s;



Sales Database
This README.md provides an overview of the Sales database schema, including details about tables, attributes, and their relationships. This database is designed to manage customer information, suppliers, payments, orders, shipping, and products.

Database Schema
The Sales database consists of the following tables:

Customer
Supplier
Payment
Orders
Shipping
Products
Table Descriptions
1. Customer Table
Attributes:

C_ID (INT): Primary Key, unique customer ID.
name (VARCHAR(60)): Name of the customer.
email (VARCHAR(150)): Email address of the customer.
phone_no (VARCHAR(60)): Phone number of the customer.
address (VARCHAR(250)): Address of the customer.
city (VARCHAR(90)): City where the customer resides.
country (VARCHAR(90)): Country where the customer resides.
pincode (VARCHAR(50)): Postal code of the customer's address.
products_buyed (VARCHAR(90)): List of products bought by the customer.
Description: Stores customer details.

Independent Entity: The Customer table does not depend on any other table.

2. Supplier Table
Attributes:

S_ID (INT): Primary Key, unique supplier ID.
name (VARCHAR(90)): Name of the supplier.
phone_no (VARCHAR(60)): Phone number of the supplier.
email (VARCHAR(160)): Email address of the supplier.
address (VARCHAR(255)): Address of the supplier.
city (VARCHAR(120)): City where the supplier is located.
country (VARCHAR(80)): Country where the supplier is located.
pin_code (VARCHAR(90)): Postal code of the supplier's address.
product_supplied (VARCHAR(160)): List of products supplied by the supplier.
Description: Stores supplier details.

Independent Entity: The Supplier table does not depend on any other table.

3. Payment Table
Attributes:

pay_ID (INT): Primary Key, unique payment ID.
C_ID (INT): Foreign Key, references Customer(C_ID).
amount (DECIMAL(10,3)): Amount of the payment.
status (VARCHAR(90)): Status of the payment (e.g., Completed, Pending).
pay_method (VARCHAR(50)): Method of payment (e.g., Credit Card, PayPal).
pay_date (TIMESTAMP): Date and time of payment (default is current timestamp).
Description: Records payment details for customers.

Dependent Entity:

C_ID references the Customer table, linking payments to customers.
4. Orders Table
Attributes:

Order_ID (INT): Primary Key, unique order ID.
C_ID (INT): Foreign Key, references Customer(C_ID).
p_id (INT): Foreign Key, references Products(p_id).
price (DECIMAL(10,2)): Price of the order.
status (VARCHAR(60)): Status of the order (e.g., Completed, Shipped).
delivery_address (VARCHAR(255)): Address where the order will be delivered.
pay_method (VARCHAR(50)): Method of payment for the order.
quantity (INT): Quantity of the product ordered.
feedback (VARCHAR(400)): Customer feedback on the order.
Order_date (TIMESTAMP): Date and time of order (default is current timestamp).
Description: Contains information about customer orders.

Dependent Entities:

C_ID references the Customer table.
p_id references the Products table.
5. Shipping Table
Attributes:

shipp_ID (INT): Primary Key, unique shipping ID.
ship_status (VARCHAR(120)): Status of the shipment (e.g., In Transit, Delivered).
ship_type (VARCHAR(90)): Type of shipment (e.g., Express, Standard).
ship_cost (DECIMAL(10,2)): Cost of shipping.
tracking_no (VARCHAR(90)): Tracking number for the shipment.
delivery_date (DATE): Expected delivery date.
shipp_date (TIMESTAMP): Date and time of shipping (default is current timestamp).
Description: Manages shipping information.

Independent Entity: The Shipping table does not depend on any other table.

6. Products Table
Attributes:

p_id (INT): Primary Key, unique product ID.
name (VARCHAR(90)): Name of the product.
type (VARCHAR(60)): Type or category of the product.
price (DECIMAL(10,2)): Price of the product.
quantity (INT): Quantity available in stock.
availability (VARCHAR(100)): Availability status of the product.
S_ID (INT): Foreign Key, references Supplier(S_ID).
Description: Contains details about products available for sale.

Dependent Entity:

S_ID references the Supplier table, linking products to suppliers.

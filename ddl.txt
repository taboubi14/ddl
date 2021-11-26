-- Creation of table Customer

CREATE TABLE Customer(
Customer_id VARCHAR(20) PRIMARY KEY,
Customer_Name VARCHAR(20) NOT NULL,
Customer_Tel Number
);

-- Creation of table Product

CREATE TABLE Product(
Product_id VARCHAR(20) PRIMARY KEY,
Product_Name VARCHAR(20) NOT NULL,
Price Number CHECK(Price>0)
);

-- Creation of table Orders

CREATE TABLE Orders(
Customer_id VARCHAR(20) PRIMARY KEY,
Product_id VARCHAR(20) PRIMARY KEY,
Quntity NUMBER,
Total_amount NUMBER,
CONSTRAINT fk_Orders_Customer FOREIGN KEY (Customer_id) REFERENCES Customer(Customer_id),
CONSTRAINT fk_Orders_Products FOREIGN KEY (Product_id) REFERENCES Product(Product_id) 
);

-- Add a column Category to the PRODUCT table

ALTER TABLE Product ADD Category VARCHAR2(20);

-- //Add a column OrderDate  to the ORDERS table which have SYSDATE as a default value.

ALTER TABLE ORDERS ADD OrderDate DATE DEFAULT 'SYSDATE';
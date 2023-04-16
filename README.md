# mySQL

1.
CREATE DATABASE devisec;
USE dev;
CREATE TABLE phones
(
ID INT PRIMARY KEY NOT NULL, 
ProductName VARCHAR(30) NOT NULL,
Manufacturer VARCHAR(40) NOT NULL,
ProductCount INT,
Price VARCHAR(15) NOT NULL
);
INSERT phones
(
ID, ProductName, Manufacturer, ProductCount, Price
)
VALUES
(1, 'iPhone X', 'Apple',3, 76000);
INSERT phones
(
ID, ProductName, Manufacturer, ProductCount, Price
)
VALUES
(2, 'iPhone 8', 'Apple',2, 51000),
(3, 'Galaxy S9', 'Samsung',2, 56000),
(4, 'Galaxy S8', 'Samsung',1, 41000),
(5, 'P20 Pro', 'Huawei',5, 36000);

2. 
SELECT * FROM seminar1.phones;
SELECT ProductName, Manufacturer, Price FROM phones
WHERE ProductCount >= 2;

3. 

SELECT * FROM seminar1.phones;
SELECT ProductName FROM phones
WHERE Manufacturer = "Samsung";

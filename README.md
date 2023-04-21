DROP SCHEMA IF EXISTS hw2;
CREATE SCHEMA IF NOT EXISTS hw2;

USE hw2;

DROP TABLE IF EXISTS sales;
CREATE TABLE IF NOT EXISTS sales
(
id INT PRIMARY KEY AUTO_INCREMENT,
order_date YEAR NOT NULL,
count_product INT
);

SELECT * FROM sales;


INSERT INTO sales (order_date, count_product)
VALUES 
(2022-01-01,156),
(2022-01-02,180),
(2022-01-03,21),
(2022-01-04,124),
(2022-01-05,341);

SELECT 
id AS "id заказа",
IF (count_product < 100, "Маленький заказ",
IF (count_product >= 100 AND count_product <= 300, "Средний заказ",
IF ( count_product > 300, "Большой заказ","неопределено")))
AS "Тип заказа"
FROM sales;

DROP TABLE IF EXISTS orders;
CREATE TABLE IF NOT EXISTS orders
(
id INT PRIMARY KEY AUTO_INCREMENT,
employee_id VARCHAR(45) NULL,
amount FLOAT,
order_status VARCHAR(45) NOT NULL
);
SELECT * FROM orders;

INSERT INTO orders (employee_id, amount, order_status)
VALUES 
('e03',15.00,'OPEN'),
('e01',25.50,'OPEN'),
('e05',100.70,'CLOSED'),
('e02',22.18,'OPEN'),
('e04',9.50,'CANCELLED');


SELECT 
id AS "order_status",
IF (order_status = 'OPEN', "Order is open state",
IF (order_status = 'CLOSED', "Order in closed",
IF ( order_status = 'CANCELLED', "Order is cancelled","неопределено")))
AS "full_order_status"
FROM orders;

# HomeWorkSQL
1.Используя операторы языка SQL, создайте табличку “sales”. Заполните ее данными
```
CREATE DATABASE homeworksql;
SHOW DATABASES;
USE homeworksql;

# Задача 1. Используя операторы языка SQL, cоздайте таблицу “sales”. Заполните ее данными.
CREATE TABLE sales (
	id INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    order_date DATE NOT NULL,
    bucret INT NOT NULL);
    
INSERT sales (order_date, bucret) VALUES
("2021-01-01", 290),
("2021-01-02", 150),
("2021-01-03", 98),
("2021-01-04", 102),
("2021-01-05", 350);

SELECT * FROM sales;
```

2.Сгруппируйте значений количества в 3 сегмента — меньше 100, 100-300 и больше 300.

```
# Задача 2. Сгруппируйте значений количества в 3 сегмента — меньше 100, 100-300 и больше 300.
SELECT id, order_date,
CASE
    WHEN bucret < 100 THEN 'меньше 100'
    WHEN bucret >= 100 AND bucret <= 300 THEN '100-300'
    ELSE 'больше 300'
END AS order_size
FROM sales;
```

3.Создайте таблицу “orders”, заполните ее значениями. Покажите “полный” статус заказа, используя оператор CASE
```
# Задача 3. Создайте таблицу “orders”, заполните ее значениями. Покажите “полный” статус заказа, используя оператор CASE
CREATE TABLE orders (
	id_orders INT NOT NULL AUTO_INCREMENT PRIMARY KEY,
    amount DOUBLE NOT NULL,
    orderstatus TEXT NOT NULL);
    
INSERT orders (amount, orderstatus) VALUES
	(150.00, "SELL"),
    (220.50, "SELL"),
    (200.00, "OPEN"),
    (500.00, "OPEN"),
    (90.00, "SELL");
    
SELECT * FROM orders;

SELECT id_orders, orderstatus,
CASE 
	WHEN orderstatus = 'OPEN' THEN 'Order is open.'
	WHEN orderstatus = 'SELL' THEN 'Order is closed.'
	ELSE 'NONE'
END AS conclusion
FROM orders;
```

4.Чем NULL отличается от 0?
```
0 - это числовое значение, а NULL - это неинициализированная переменная (объект).
```

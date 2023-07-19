1. Вывести на экран сколько машин каждого цвета для машин марок BMW и LADA
```
SELECT MARK, color, COUNT(color) AS 'Quantity of cars' FROM AUTO
WHERE MARK = 'LADA'
GROUP BY color, mark 
UNION SELECT MARK, color, COUNT(color) AS 'Quantity of cars' FROM AUTO
WHERE MARK = 'BMW'
GROUP BY color, mark;
```
2. Вывести на экран марку авто и количество AUTO не этой марки
```
SELECT MARK, (COUNT(color) - 1) AS 'Quantity of cars' FROM AUTO
GROUP BY MARK;
```
3. Напишите запрос, который вернет строки из таблицы test_a, id которых нет в таблице test_b, НЕ используя ключевого слова NOT.
```
CREATE TABLE test_a (id_number INT, data VARCHAR(1));
CREATE TABLE test_b (id_number INT);
INSERT INTO test_a (id_number, data) VALUES
	(10, 'A'), (20, 'A'), (30, 'F'), (40, 'D'), (50, 'C');
INSERT INTO test_b(id_number) VALUES 
	(10), (30), (50);

SELECT * FROM test_a NATURAL LEFT JOIN test_b WHERE test_b.id_number IS NULL;
```

1. Создайте функцию, которая принимает кол-во сек и формат их в кол-во дней часов. Пример: 123456 ->'1 days 10 hours 17 minutes 36 seconds '
```
DELIMITER $$
CREATE PROCEDURE time(second INT)
BEGIN
    DECLARE day INT default 0;
    DECLARE hour INT default 0;
    DECLARE min INT default 0;

    WHILE second >= 84600 DO
    SET day = second / 84600;
    SET second = second % 84600;
    END WHILE;

    WHILE second >= 3600 DO
    SET hour = second / 3600;
    SET second = second % 3600;
    END WHILE;

    WHILE second >= 60 DO
    SET min = second / 60;
    SET second = second % 60;
    END WHILE;

SELECT day, hour, min, second;
END $$
DELIMITER ;

CALL time(123456);
```

2. Выведите только четные числа от 1 до 10. Пример: 2,4,6,8,10 Данная промежуточная аттестация оценивается по системе "зачет" / "не зачет" "Зачет" ставится, если слушатель успешно выполнил 1 или 2 задачи "Незачет" ставится, если слушатель успешно выполнил 0 задач Критерии оценивания: 1 - слушатель верно создал функцию, которая принимает кол-во сек и формат их в кол-во дней часов. 2 - слушатель выведили только четные числа от 1 до 10.
```
DELIMITER $$
CREATE PROCEDURE num()
BEGIN
    DECLARE n INT default 0;
    DROP TABLE IF EXISTS nums;
    CREATE TABLE nums (n INT);

    WHILE n < 10 DO
    SET n = n + 2;
    INSERT INTO nums VALUES(n);
    END WHILE;

SELECT * FROM nums;
END $$
DELIMITER ;

CALL num();
```

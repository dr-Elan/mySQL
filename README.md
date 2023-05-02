USE lesson_5;

#Создайте функцию, которая принимает кол-во сек и формат их в кол-во дней часов.
#Пример: 123456 ->'1 days 10 hours 17 minutes 36 seconds '
-- IF NOT EXISTS (select * from lesson_5 where name = 'sectotime')

DROP FUNCTION IF EXISTS sectotime;



delimiter //
CREATE FUNCTION sectotime (val INT)
RETURNS CHAR(15)
DETERMINISTIC
BEGIN
DECLARE DD CHAR(3);
DECLARE HH, MI, SS CHAR(2);
DECLARE res CHAR(15);
SET DD = CAST(FLOOR(val/60/60/24) AS CHAR(3));
SET HH = CAST(FLOOR(MOD(val/60/60/24,1)*24) AS CHAR(2));
SET MI = CAST(FLOOR(MOD(MOD(val/60/60/24,1)*24,1)*60) AS CHAR(2));
SET SS = CAST(ROUND(MOD(MOD(MOD(val/60/60/24,1)*24,1)*60,1)*60) AS CHAR(2));
SET res = CONCAT(DD,'.',HH,':',MI,':',SS);
RETURN res;
END ;
// 
delimiter ;
SELECT sectotime(18400000) ;








#Выведите только четные числа от 1 до 10.
SELECT * FROM numbers WHERE number % 2 = 0 AND number BETWEEN 1 AND 10;
#Пример: 2,4,6,8,10

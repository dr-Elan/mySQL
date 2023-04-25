#Создайте представление, в которое попадут автомобили стоимостью до 25 000 долларов
CREATE OR REPLACE VIEW cheap AS SELECT * FROM cars WHERE 	cost<25000;
SELECT * FROM cheap;

# Изменить в существующем представлении порог для стоимости: пусть цена будет до 30 000 долларов (используя оператор ALTER VIEW)

ALTER VIEW cheap  AS SELECT * FROM cars WHERE cost<30000;
SELECT * FROM cheap;

# Создайте представление, в котором будут только автомобили марки “Шкода” и “Ауди”
CREATE OR REPLACE VIEW wv AS SELECT * FROM cars WHERE 	(name = 'Skoda' OR name = 'Audi') ;
SELECT * FROM wv;

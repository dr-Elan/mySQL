# Вывести всех котиков по магазинам по id (условие соединения shops.id = cats.shops_id)
SELECT cats.name FROM cats
LEFT JOIN shops ON shops.id = cats.shops_id;
# .Вывести магазин, в котором продается кот “Мурзик” (попробуйте выполнить 2 способами)
SELECT shops.shopname FROM shops
JOIN cats ON cats.shops_id=shops.id
WHERE cats.name = 'Murzik';
# Вывести магазины, в которых НЕ продаются коты “Мурзик” и “Zuza” Табличка (после слов “Последнее задание, таблица:”)
SELECT shops.shopname FROM shops
JOIN cats ON cats.shops_id=shops.id
WHERE NOT ( cats.name = 'Zuza' OR cats.name = 'Murzik' ) ;
# 4.Вывести название и цену для всех анализов, которые продавались 5 февраля 2020 и всю следующую неделю.
SELECT Analysis.an_name, Analysis.an_price FROM Analysis
RIGHT JOIN Orders ON Orders.ord_an=Analysis.an_group
WHERE Orders.ord_datetime > '2020-02-05' AND Orders.ord_datetime < '2020-02-12'

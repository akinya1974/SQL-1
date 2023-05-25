# «SQL. Часть 1» Акиньшин С.Г.

## Задание-1

1. `Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.`
'''
SELECT DISTINCT district 
FROM address 
WHERE district  LIKE 'k%a' and district not LIKE  '% %';
'''
![Link](https://github.com/akinya1974/SQL-1/blob/main/JPG/Задание-1.jpg)


## Задание-2

2. `Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года включительно и стоимость которых превышает 10.00.`
'''
SELECT *
FROM payment
WHERE payment_date BETWEEN  CAST('2005-06-15' AS DATE) AND CAST('2005-06-19' AS DATE)
AND amount > 10;
'''
![Link](https://github.com/akinya1974/SQL-1/blob/main/JPG/Задание-2.jpg)


## Задание-3

3. `Получите последние пять аренд фильмов.`
'''
SELECT *  
FROM rental   
ORDER by rental_date DESC 
LIMIT 5
'''
![Link](https://github.com/akinya1974/SQL-1/blob/main/JPG/Задание-3.jpg)

## Задание-4

4. `Одним запросом получите активных покупателей, имена которых Kelly или Willie.`
'''
SELECT LOWER(REPLACE(first_name, 'L', 'p')), LOWER(last_name) 
FROM customer
WHERE first_name LIKE 'Willie' OR first_name  LIKE 'Kelly'
'''
![Link](https://github.com/akinya1974/SQL-1/blob/main/JPG/Задание-4.jpg)

## Задание-5

5. `Выведите Email каждого покупателя, разделив значение Email на две отдельных колонки: в первой колонке должно быть значение, указанное до @, во второй — значение, указанное после @.`
'''
SELECT email, SUBSTRING_INDEX(email , '@', 1), SUBSTRING_INDEX(email , '@', -1)
FROM customer;
'''
![Link](https://github.com/akinya1974/SQL-1/blob/main/JPG/Задание-5.jpg)
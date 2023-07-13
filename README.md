### Домашнее задание к занятию «SQL. Часть 1» - Корольков Денис

Задание можно выполнить как в любом IDE, так и в командной строке.

### Задание 1

Получите уникальные названия районов из таблицы с адресами, которые начинаются на “K” и заканчиваются на “a” и не содержат пробелов.

Ответ:
```
Берем таблицу с адресами - address  district (район).
Для уникальности названий используем DISTINCT.
А также нам нужен будет предикат LIKE.
SELECT DISTINCT district FROM address WHERE district LIKE ‘K%a’ AND district NOT LIKE ‘% %’;
```

![screen1](https://github.com/KorolkovDenis/12.3---SQL-p.1/blob/main/screenshots/screen1.jpg)
![screen2](https://github.com/KorolkovDenis/12.3---SQL-p.1/blob/main/screenshots/screen2.jpg)

### Задание 2

Получите из таблицы платежей за прокат фильмов информацию по платежам, которые выполнялись в промежуток с 15 июня 2005 года по 18 июня 2005 года **включительно** и стоимость которых превышает 10.00.

Ответ:

Условие:
```
Таблица платежей – payment. 
Payment_date 2005-06-15 по 2005-06-18 включительно. 
amount > 10.00
```
```
SELECT CAST (payment_date AS DATE), amount
FROM payment
WHERE amount  > 10.00 AND payment_date BETWEEN ‘2005-06-15’ AND ‘2005-06-19’
ORDER BY payment_date;
```

![screen3](https://github.com/KorolkovDenis/12.3---SQL-p.1/blob/main/screenshots/screen3.jpg)
![screen4](https://github.com/KorolkovDenis/12.3---SQL-p.1/blob/main/screenshots/screen4.jpg)

### Задание 3

Получите последние пять аренд фильмов.

Ответ:

Из таблицы аренды rental:
```
SELECT rental_id, rental_date, inventory_id
FROM rental
ORDER BY rental_date DESC
LIMIT 5;
```
![screen5](https://github.com/KorolkovDenis/12.3---SQL-p.1/blob/main/screenshots/screen5.jpg)
![screen6](https://github.com/KorolkovDenis/12.3---SQL-p.1/blob/main/screenshots/screen6.jpg)

### Задание 4

Одним запросом получите активных покупателей, имена которых Kelly или Willie. 

Сформируйте вывод в результат таким образом:
- все буквы в фамилии и имени из верхнего регистра переведите в нижний регистр,
- замените буквы 'll' в именах на 'pp'.

Ответ:

От себя для ясности добавил фамилию и порядковый номер.
```
SELECT LOWER(first_name), REPLACE(first_name, ‘LL’, ‘pp’) last_name, customer_id
FROM customer
WHERE first_name = ‘Kelly’ OR first_name = ‘Willie’;
```

![screen7](https://github.com/KorolkovDenis/12.3---SQL-p.1/blob/main/screenshots/screen7.jpg)

## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.

### Задание 5*

Выведите Email каждого покупателя, разделив значение Email на две отдельных колонки: в первой колонке должно быть значение, указанное до @, во второй — значение, указанное после @.

### Задание 6*

Доработайте запрос из предыдущего задания, скорректируйте значения в новых колонках: первая буква должна быть заглавной, остальные — строчными.


[Cсылка на google docs по «SQL. Часть 1»](https://docs.google.com/document/d/13AT4C8GPjh7Rlsl9itqLUu3Clv-0KoII/edit?usp=drive_link&ouid=104113173630640462528&rtpof=true&sd=true)

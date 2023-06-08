Домашнее задание к занятию «Индексы»  SKOPKIN ILYA


Задание 1
Напишите запрос к учебной базе данных, который вернёт процентное отношение общего размера всех индексов к общему размеру всех таблиц.


![alt text](https://github.com/matiz86/git_hw-12.5/blob/main/Screenshot_3.jpg)




Задание 2
Выполните explain analyze следующего запроса:


select distinct concat(c.last_name, ' ', c.first_name), sum(p.amount) over (partition by c.customer_id, f.title)
from payment p, rental r, customer c, inventory i, film f
where date(p.payment_date) = '2005-07-30' and p.payment_date = r.rental_date and r.customer_id = c.customer_id and i.inventory_id = r.inventory_id


![alt text](https://github.com/matiz86/git_hw-12.5/blob/main/Screenshot_1.jpg)

перечислите узкие места;

Узкие места наблюдаются в момент использования оконных функций OVER и PARTITION BY.Много сравнений в WHERE.

оптимизируйте запрос: внесите корректировки по использованию операторов, при необходимости добавьте индексы.


![alt text](https://github.com/matiz86/git_hw-12.5/blob/main/Screenshot_2.jpg)




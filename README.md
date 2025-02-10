# Домашнее задание к занятию "`Название занятия`" - `Фамилия и имя студента`

### Задание 1


1. `Устанавливаю mysql локально `

![1](https://github.com/Foxbeerxxx/DDL-DML/blob/main/img/img1.png)`

2. `По умолчанию подключаюсь под root`

```
sudo mysql -u root -p
```
![2](https://github.com/Foxbeerxxx/DDL-DML/blob/main/img/img2.png)`

3. `Создаю пользователя`
```
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY 'password';
```

4. `Отправляю команду на список пользователей и видим , что все прошло верно`
```
SELECT User, Host FROM mysql.user;
```
![3](https://github.com/Foxbeerxxx/DDL-DML/blob/main/img/img3.png)`

5. `Назначаю права на пользователя`
```
   GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost' WITH GRANT OPTION;
   
```
6. `Просматриваем права пользователя sys_temp`
```
SHOW GRANTS FOR 'systemp'@'localhost';
```
![4](https://github.com/Foxbeerxxx/DDL-DML/blob/main/img/img4.png)`

7. `Перелогиниваемся в  mysql под sys_temp`
![5](https://github.com/Foxbeerxxx/DDL-DML/blob/main/img/img5.png)`

8. `Скачиваю и распаковываю архив`
```
wget https://downloads.mysql.com/docs/sakila-db.zip
unzip sakila-db.zip
```
![6](https://github.com/Foxbeerxxx/DDL-DML/blob/main/img/img6.png)`

9. `Создаю базу данных sakilla и подгружаю схему и данные с архива`
```
CREATE DATABASE sakila;
USE sakila;
```
```
 mysql -u sys_temp -p sakila < sakila-schema.sql
 mysql -u sys_temp -p sakila < sakila-data.sql
```

10. `Отправляем команду для проверки`
```
    mysql -u sys_temp -p sakila -e "SHOW TABLES;"

```
![7](https://github.com/Foxbeerxxx/DDL-DML/blob/main/img/img7.png)`

```
+----------------------------+
| Tables_in_sakila           |
+----------------------------+
| actor                      |
| actor_info                 |
| address                    |
| category                   |
| city                       |
| country                    |
| customer                   |
| customer_list              |
| film                       |
| film_actor                 |
| film_category              |
| film_list                  |
| film_text                  |
| inventory                  |
| language                   |
| nicer_but_slower_film_list |
| payment                    |
| rental                     |
| sales_by_film_category     |
| sales_by_store             |
| staff                      |
| staff_list                 |
| store                      |
+----------------------------+

```

---

### Задание 2



1. `Составляю таблицу`

![8](https://github.com/Foxbeerxxx/DDL-DML/blob/main/img/img8.png)`

```
Название таблицы	Н﻿азвание первичного ключа
﻿actor	﻿actor_id
﻿actor_info	не знаю :(
﻿address	﻿address_id
﻿category	﻿category_id
﻿city	city_id
﻿country	﻿country_id
﻿customer	﻿customer_id
﻿customer_list	не знаю :(
﻿film	﻿film_id
﻿film_actor	﻿ actor_id, film_id
﻿film_category	﻿film_id,category_id 
﻿film_list	не знаю :(
﻿film_text	﻿film_id
﻿inventory	﻿inventory_id
﻿language	﻿language_id
﻿payment	﻿payment_id
﻿rental	﻿ rental_id
﻿sales_by_film_category	не знаю :(   category_id ?
﻿sales_by_store	store id
﻿staff	﻿staff_id
﻿staff_list	﻿ actor_id, film_id,category_id
﻿store	﻿store_id


```


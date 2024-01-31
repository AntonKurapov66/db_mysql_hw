# Домашнее задание к занятию "Работа с данными (DDL/DML)" - `Курапов Антон`

### Задание 1
* 1.1. Поднимите чистый инстанс MySQL версии 8.0+. Можно использовать локальный сервер или контейнер Docker.
![alt text](https://github.com/AntonKurapov66/db_mysql_hw/blob/main/img/4.PNG)
* 1.2. Создайте учётную запись sys_temp.
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY'password';
* 1.3. Выполните запрос на получение списка пользователей в базе данных. (скриншот)
SELECT user, authentication_string,plugin,host FROM mysql.user;
![alt text](https://github.com/AntonKurapov66/db_mysql_hw/blob/main/img/1.PNG)
* 1.4. Дайте все права для пользователя sys_temp.
GRANT ALL ON *.* TO 'sys_temp'@'localhost';
* 1.5. Выполните запрос на получение списка прав для пользователя sys_temp. (скриншот)
SHOW GRANTS FOR 'sys_temp'@'localhost';
![alt text](https://github.com/AntonKurapov66/db_mysql_hw/blob/main/img/2.PNG)
* 1.6. Переподключитесь к базе данных от имени sys_temp.
exit
mysql -h localhost -u sys_temp -p
Для смены типа аутентификации с sha2 используйте запрос:
ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
* 1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачайте дамп базы данных.
wget https://downloads.mysql.com/docs/sakila-db.zip
unzip sakila-db.zip
* 1.7. Восстановите дамп в базу данных.
mysql -u sys_temp -p sakila_db < sakila-schema.sql
mysql -u sys_temp -p sakila_db < sakila-data.sql
* 1.8. При работе в IDE сформируйте ER-диаграмму получившейся базы данных. При работе в командной строке используйте команду для получения всех таблиц базы данных. (скриншот)
SHOW TABLES FROM sakila;
![alt text](https://github.com/AntonKurapov66/db_mysql_hw/blob/main/img/3.PNG)


### Задание 2
Составьте таблицу, используя любой текстовый редактор или Excel, в которой должно быть два столбца: в первом должны быть названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц. Пример: (скриншот/текст)

Название таблицы | Название первичного ключа
customer         | customer_id

* https://github.com/AntonKurapov66/db_mysql_hw/blob/main/2_task.txt - ссылка на текстовый файл 







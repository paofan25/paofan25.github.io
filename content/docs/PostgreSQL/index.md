---
title: "PostgreSQL"
date: 2025-01-29
draft: false
summary: "Something about SQL"
tags: ["SQL"]
showComments : true
---
## 进入数据库
```bash
postgres=> \c mario_database

SSL connection (protocol: TLSv1.3, cipher: TLS_AES_256_GCM_SHA384, bits: 256, compression: off)
You are now connected to database "mario_database" as user "freecodecamp".
mario_database=> DROP DATABASE second_database
```
## 列出已有数据库list
```shell
\l
mario_database=> \l
mario_database=>                                    List of databases
+----------------+--------------+----------+---------+---------+-----------------------+
|      Name      |    Owner     | Encoding | Collate |  Ctype  |   Access privileges   |
+----------------+--------------+----------+---------+---------+-----------------------+
| mario_database | freecodecamp | UTF8     | C.UTF-8 | C.UTF-8 |                       |
| postgres       | postgres     | UTF8     | C.UTF-8 | C.UTF-8 |                       |
| template0      | postgres     | UTF8     | C.UTF-8 | C.UTF-8 | =c/postgres          +|
|                |              |          |         |         | postgres=CTc/postgres |
| template1      | postgres     | UTF8     | C.UTF-8 | C.UTF-8 | =c/postgres          +|
|                |              |          |         |         | postgres=CTc/postgres |
+----------------+--------------+----------+---------+---------+-----------------------+
(4 rows)
```
## 展现数据库中的表
```bash
\d
Did not find any relations.
```
## 添加一个表
```SQL
CREATE TABLE characters();
return  CREATE TABLE if success
```
## 在表中添加行·列
```SQL
ALTER TABLE characters ADD COLUMN character_id SERIAL;
            (tablename)           (column name) (type)
ALTER TABLE table_name ADD COLUMN column_name DATATYPE CONSTRAINT;
                                                        (指定格式)
                                                        比如：NOT NULL
```
## 登录数据库
```bash
psql --username=freecodecamp --dbname=postgres
```
## 创建数据库·表·列
```SQL
CREATE DATABASE database_name;
CREATE TABLE table_name();
ALTER TABLE table_name ADD COLUMN column_name DATATYPE;
```
## 移除一列（remove）
```SQL
ALTER TABLE table_name DROP COLUMN column_name;
```
## 删除一行
```SQL
DELETE FROM students
WHERE id = 2;
```
## 删除表
```SQL
DROP TABLE table_name;
```
## 给表中的量添加值
```SQL
INSERT INTO second_table(id, username) VALUES(1, 'Samus');

INSERT INTO characters(name, homeland, favorite_color)
VALUES('Mario', 'Mushroom Kingdom', 'Red'),
('Luigi', 'Mushroom Kingdom', 'Green'),
('Peach', 'Mushroom Kingdom', 'Pink');
```
## 修改某值
```SQL
UPDATE students
SET age = 23
WHERE id = 2;
```
## 查看表中的值
```SQL
SELECT columns FROM table_name;
选中所有：*
```
## 以id排序
```SQL
SELECT columns FROM table_name ORDER BY column_name;
SELECT * FROM characters ORDER BY character_id;
```

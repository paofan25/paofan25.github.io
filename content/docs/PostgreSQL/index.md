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
## 列出数据库内容list列出已有数据库
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
```bash
CREATE TABLE characters();
return  CREATE TABLE if success
```
## 在表中添加行·列
```bash
ALTER TABLE characters ADD COLUMN character_id SERIAL;
            (tablename)           (column name) (type)
```
## 登录数据库
```bash
psql --username=freecodecamp --dbname=postgres
```
## 创建数据库·表·列
```bash
CREATE DATABASE database_name;
CREATE TABLE table_name();
ALTER TABLE table_name ADD COLUMN column_name DATATYPE;
```
## 移除一行（remove）
```bash
ALTER TABLE table_name DROP COLUMN column_name;
```
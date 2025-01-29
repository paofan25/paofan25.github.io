---
title: "PostgreSQL"
date: 2025-01-29
draft: false
summary: "Something about SQL"
tags: ["SQL"]
showComments : true
---
## enter a database
```bash
postgres=> \c mario_database

SSL connection (protocol: TLSv1.3, cipher: TLS_AES_256_GCM_SHA384, bits: 256, compression: off)
You are now connected to database "mario_database" as user "freecodecamp".
mario_database=> DROP DATABASE second_database
```
## list the data base
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
## display what is in database
```bash
\d
Did not find any relations.
```
## add a table in database
```bash
CREATE TABLE characters();
return  CREATE TABLE if success
```
## add a column
```bash
ALTER TABLE characters ADD COLUMN character_id SERIAL;
            (tablename)           (column name) (type)
```
## enter the data service
```bash
psql --username=freecodecamp --dbname=postgres
```
## create 
```bash
CREATE DATABASE database_name;
CREATE TABLE table_name();
ALTER TABLE table_name ADD COLUMN column_name DATATYPE;
```
## remove column
```bash
ALTER TABLE table_name DROP COLUMN column_name;
```
# SQL

## SQL简介

SQL(Structured Query Language，结构化语言)是一种用于管理和操作关系型数据库的标准化编程语言

SQL通过一系列的语句和命令来执行数据定义、数据查询、数据操作和数据控制等功能，包括数据插入、查询、更新和删除，数据库模式创建和修改，以及数据访问控制

SQL由国际标准化组织ISO和美国国家标准协会ANSI标准化

SQL提供了丰富的操作数据的功能，从简单的查询到复杂的数据库管理操作

RDBMS指关系型数据库管理系统，全称Relational Database Management System，其中数据被存储在称为表的数据库对象中，表是相关数据项的集合，它由列和行组成

## SQL语法

SQL是一种用于管理和操作关系数据库的标准语言，包括数据查询、数据插入、数据更新、数据删除、数据库结构创建和修改等功能

数据库表：一个数据库包含一个或多个表，每个表有一个名字标识，表包含带有数据的记录（行）。

SQL语句：在数据库上执行的大部分工作都有SQL语句完成，对大小写不敏感，SELECT和select是相同的，每条SQL语句末端使用分号，分号是数据库系统中分隔每条SQL语句的标准方法

```sql
SELECT  选择
UPDATE 更新
DELETE 删除数据
INSERT INTO 向数据库中插入新数据
CREATE DATABASE 创建数据库
ALTER DATABASE 修改数据库
CREATE TABLE 创建表
ALTER TABLE 改变表
DROP TABLE 删除表
CREATE INDEX 创建索引
DROP INDEX 删除索引

SELECT column_name(s) FROM table_name WHERE condition ORDER BY column_name[ASC|DESC]

INSERT INTO table_name (column1, column2, ...) VALUES (value1, value2, ...)

UPDATE table_name SET column1 = value1, column2 = value2, ... WHERE condition

DELETE FROM table_name WHERE condition

CREATE TABLE table_name (
    column1 data_type constraint,
    column2 data_type constraint,
    ...
)

ALTER TABLE table_name ADD column_name data_type

DROP TABLE table_name

CREATE INDEX index_name ON table_name (column_name)

DROP INDEX index_name ON table_name

SELECT column_name(s) FROM table_name WHERE condition

SELECT column_name(s) FROM table_name ORDER BY column_name [ASC|DESC]

SELECT column_name(s), aggregate_function(column_name) 
FROM table_name
WHERE condition
GROUP BY column_name(s)


```


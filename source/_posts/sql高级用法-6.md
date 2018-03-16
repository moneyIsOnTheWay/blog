---
title: sql高级用法-6
date: 2018-03-16 16:34:12
tags:
categories: SQL
---
### SQL ALTER TABLE

> 在已有的表中添加、修改和删除列

- 在已有的表中添加列

```
alter table table_name
add column_name datatype
```

- 在已有的表中删除列

```
alter table table_name
drop column column_name
```

> 注释：某些数据库系统不允许这种在数据库表中删除列的方式 (DROP COLUMN column_name)。

- 要改变表中列的数据类型，请使用下列语法

```
alter table table_name
alter column column_name datatype
```

### AUTO INCREMENT 字段

> Auto-increment 会在新记录插入表中时生成一个唯一的数字。

###### MySQL

```
create table table_name(
ID int NOT NULL AUTO INCREMENT,
LastName varchar(255),
FirstName varchar(255),
primary key(ID)
)
```

> MySQL 使用 AUTO_INCREMENT 关键字来执行 auto-increment 任务。
默认地，AUTO_INCREMENT 的开始值是 1，每条新记录递增 1。要让 AUTO_INCREMENT 序列以其他的值起始，请使用下列 SQL 语法：

```
ALTER TABLE Persons AUTO_INCREMENT=100
```

###### SQL SERVER

```
create table table_name(
ID int primary key identity,
...
)
```

> MS SQL 使用 IDENTITY 关键字来执行 auto-increment 任务。
默认地，IDENTITY 的开始值是 1，每条新记录递增 1。要规定 "P_Id" 列以 20 起始且递增 10，请把 identity 改为 IDENTITY(20,10)


### SQL VIEW

> 在 SQL 中，视图是基于 SQL 语句的结果集的可视化的表。视图包含行和列，就像一个真实的表。视图中的字段就是来自一个或多个数据库中的真实的表中的字段。我们可以向视图添加 SQL 函数、WHERE 以及 JOIN 语句，我们也可以提交数据，就像这些来自于某个单一的表。

- SQL CREATE VIEW 语法

```
create view view_name as select column_name(s) from table_name where condition
```

> 注释：视图总是显示最近的数据。每当用户查询视图时，数据库引擎通过使用 SQL 语句来重建数据。

- SQL 更新视图

```
CREATE OR REPLACE VIEW view_name AS
SELECT column_name(s)
FROM table_name
WHERE condition
```

- SQL 撤销视图

> 您可以通过 DROP VIEW 命令来删除视图。

```
DROP VIEW view_name
```
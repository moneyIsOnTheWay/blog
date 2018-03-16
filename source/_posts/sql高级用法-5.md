---
title: sql高级用法-5
date: 2018-03-16 16:08:39
tags:
categories: SQL
---
### SQL DEFAULT 约束

> DEFAULT 约束用于向列中插入默认值。如果没有规定其他的值，那么会将默认值添加到所有的新记录。

-  SQL 在 "Persons" 表创建时为 "City" 列创建 DEFAULT 约束

###### My SQL / SQL Server / Oracle / MS Access:

```
create table Persons(
Id_P int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName Varchar(255),
Address varchar(255),
City varchar(255) DEFAULT 'Chongqing'
)
```

- 通过使用类似 GETDATE() 这样的函数，DEFAULT 约束也可以用于插入系统值：

```
CREATE TABLE Orders
(
Id_O int NOT NULL,
OrderNo int NOT NULL,
Id_P int,
OrderDate date DEFAULT GETDATE()
)
```

- 在表已存在的情况下为 "City" 列创建 DEFAULT 约束，请使用下面的 SQL：

###### MySQL

```
alter table Persons
alter City SET DEFAULT 'Chongqing'
```

###### SQL Server / Oracle / MS Access:

```
alter table Persons
alter column City SET DEFAULT 'Chongqing'
```

### 撤销 DEFAULT 约束

> 如需撤销 DEFAULT 约束，请使用下面的 SQL：

###### MySQL

```
alter table Persons
alter City drop DEFAULT
```

###### SQL Server / Oracle / MS Access:

```
alter table Persons
alter COLUMN City drop default
```

### CREATE INDEX

> 语句用于在表中创建索引,在不读取整个表的情况下，索引使数据库应用程序可以更快地查找数据,您可以在表中创建索引，以便更加快速高效地查询数据。
用户无法看到索引，它们只能被用来加速搜索/查询。注释：更新一个包含索引的表需要比更新一个没有索引的表更多的时间，这是由于索引本身也需要更新。因此，理想的做法是仅仅在常常被搜索的列（以及表）上面创建索引。

- 在表上创建一个简单的索引。允许使用重复的值

```
create index index_name
on table_name(column_name)
```

> 注释："column_name" 规定需要索引的列。

- 在表上创建一个唯一的索引。唯一的索引意味着两个行不能拥有相同的索引值。

```
create unique index index_name on table_name(column_name)
```

### SQL DROP INDEX 语句

> 我们可以使用 DROP INDEX 命令删除表格中的索引。

###### sql server

```
drop index table_name.index_name
```

###### db2 and oracle

```
drop index index_name
```

###### mysql

```
alter table table_name drop index index_name
```

### SQL DROP TABLE 语句

> DROP TABLE 语句用于删除表（表的结构、属性以及索引也会被删除）

```
drop table table_name
```

### SQL DROP DATABASE 语句

> DROP DATABASE 语句用于删除数据库

```
drop database database_name
```

### SQL TRUNCATE TABLE 语句

> TRUNCATE TABLE 命令（仅仅删除表格中的数据）

```
truncate table table_name
```
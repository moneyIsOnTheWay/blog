---
title: sql高级用法-4
date: 2018-03-15 14:40:14
tags:
categories: SQL
---

### SQL CHECK 约束

> CHECK 约束用于限制列中的值的范围。如果对单个列定义 CHECK 约束，那么该列只允许特定的值。如果对一个表定义 CHECK 约束，那么此约束会在特定的列中对值进行限制

- 在 "Persons" 表创建时为 "Id_P" 列创建 CHECK 约束。CHECK 约束规定 "Id_P" 列必须只包含大于 0 的整数

###### MySQL

```
create table Persions(
Id_P int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Address varchar(255),
City varchar(255),
check(Id_P > 0)
)
```

###### SQL Server / Oracle / MS Access:

```
CREATE TABLE Persons
(
Id_P int NOT NULL CHECK (Id_P>0),
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Address varchar(255),
City varchar(255)
)
```

- 需要命名 CHECK 约束，以及为多个列定义 CHECK 约束，请使用下面的 SQL 语法：

###### MySQL / SQL Server / Oracle / MS Access:

```
CREATE TABLE Persons
(
Id_P int NOT NULL,
LastName varchar(255) NOT NULL,
FirstName varchar(255),
Address varchar(255),
City varchar(255),
constraint ck_Persion check(Id_P > 0 and City = "Chongqing")
)
```

- 在表已存在的情况下为 "Id_P" 列创建 CHECK 约束，请使用下面的 SQL：

###### MySQL / SQL Server / Oracle / MS Access:

```
alter table Persons
add check(Id_P > 0)
```

- 需要命名 CHECK 约束，以及为多个列定义 CHECK 约束，请使用下面的 SQL 语法

###### MySQL / SQL Server / Oracle / MS Access:

```
alter table Persons
add contraint ck_persons check(Id_P > 0 and city = "Beijing")
```

- 撤销 CHECK 约束

###### MySQL

```
alter table Persons
drop check ck_person
```

###### SQL Server / Oracle / MS Access:

```
alter table Persons
drop constraint ck_person
```
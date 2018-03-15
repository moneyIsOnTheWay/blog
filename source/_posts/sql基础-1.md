---
title: sql基础
date: 2018-02-02 11:50:00
categories: SQL
---

### select 查询

```
select c_name_1,c_name_2,... from t_name
```

### distince 去重

>在表中，可能会包含重复值。这并不成问题，不过，有时您也许希望仅仅列出不同（distinct）的值。关键词 DISTINCT 用于返回唯一不同的值。

```
select distinct c_name_1,c_name_2,... from t_name
```
### where 子句

>如需有条件地从表中选取数据，可将 WHERE 子句添加到 SELECT 语句

#### 操作符

- 大于
- 小于
- 等于
- 不等于
- like
- between

#### and-or

> 且与或

```
select * from tb_study where age > 20 and sex = '男'
select * from tb_study where age > 20 or sex = '男'
```

### order by (desc、asc)

> 将结果按某种顺序排（desc降、asc升) eg：分数按高到低排

```
select grade from tb_grade order by desc
```



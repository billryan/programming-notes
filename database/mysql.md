# MySQL

## 数据库的基础概念

- database(数据库)：保存有组织的数据的容器(通常是一个文件或一组文件)
- DBMS(数据库管理系统)：创建和操纵数据库的软件
- table(表)：某种特定类型数据的结构化清单(比如顾客的清单与订单的清单)
- schema(模式)：关于数据库和表的布局及特性的信息
- column(列)：表中的一个字段，所有表都是由一个或多个列组成的
- datatype(数据类型)：列中数据的类型。每个表列都有相应的数据类型，它限制了该列可以存储的数据
- row(行)：表中的一个记录(也称为数据库记录(record))
- primary key(主键)：一列(或一组列)，其值能唯一区分表中每个行
- SQL：结构化查询语言，专用来与数据库通信的语言

数据库与表的区别和联系：数据库类似文件柜，而表则相当于文件。数据库中的每个表都有一个名字(唯一)，用来标识自己。

何谓模式？表通常具有一些特性，如可以存储什么样的数据，数据如何分解，各部分信息如何命名等。描述表的这组信息就是所谓的模式。

表和列的关系：如顾客表中，一个列存储着顾客编号，另一个列存储着顾客名。

分解数据：例如城市、州、邮政编码应该总是独立的列，否则组合在一个列中按州进行排序或过滤会很麻烦。

主键条件：表中任何列都可以作为主键，需要满足
    1. 任意两行都不具有相同的主键值
    2. 每行都必须具有一个主键值(不可为NULL)

主键通常定义在表的一列上，但也可以使用多个列(多个列值的组合须唯一)作为主键。

主键的最佳实践：

- 不更新主键列中的值
- 不重用主键列的值
- 不在主键列中使用可能会更改的值

显示表列：
```
SHOW COLUMNS FROM customers;
```
可使用`DESCRIBE customers`代替之。

## 检索数据

使用`SELECT`检索表数据，必须至少给出两条信息——想选择什么以及从什么地方选择。
```
SELECT prod_name FROM products
```

检索多个列
```
SELECT prod_id, prod_name, prod_price FROM products;
```
SELECT后给出多个列名，列名之间加上逗号。

检索所有列
```
SELECT * FROM products;
```

检索不同的行
```
SELECT DISTINCT vend_id FROM products;
```

限制结果
```
SELECT prod_name FROM products LIMIT 5;
```
返回不多于5行。
```
SELECT prod_name FROM products LIMIT 5,4;
```
返回从行5开始的4行，行数从0开始计数。

使用完全限定的表名:

除了通过列名引用列之外也可以使用完全限定的名字来引用列(同时使用表名和列字)
```
SELECT products.prod_name FROM products;
```

### 排序检索数据

- clause(子句)：SQL语句由子句构成，比如SELECT语句的FROM子句。

```
SELECT prod_name FROM products ORDER BY prod_name;
```

按多个列排序，检索多个列，并对多列排序：
```
SELECT prod_id, prod_price, prod_name
FROM products
ORDER BY prod_price, prod_name;
```
先按`prod_price`排序，再按照`prod_name`排序。

指定排序方向，默认时按照升序排序。还可以使用DESC关键字对其进行逆序排序。

```
SELECT prod_id, prod_price, prod_name
FROM products
ORDER BY prod_price DESC;
```

还可以先降序后对其他列排序：
```
SELECT prod_id, prod_price, prod_name
FROM products
ORDER BY prod_price DESC, prod_name;
```
要想多个列降序排列，须多次使用DESC关键字，与DESC相反的是ASC.

默认情况下排序大小写不区分。

找到列中最大/小值，结合ORDER BY和LIMIT
```
SELECT prod_id, prod_price, prod_name
FROM products
ORDER BY prod_price DESC
LIMIT 1;
```

## 过滤数据

主要学习用`SELECT` 语句的`WHERE` 子句过滤返回的数据。如对相等、不相等、大于、小于、值的范围以及`NULL` 值等进行测试。

1. 使用 WHERE 子句

相等测试

```
SELECT prod_name, prod_price
FROM products
WHERE prod_price = 2.50;
```

> 同时使用 ORDER BY 和 WHERE 子句时，应该让 ORDER BY 位于 WHERE 之后，否则将会产生错误。

WHERE 子句支持的条件操作符除了常用的等于/小于/大于等组合外还支持如`<> 不等于`和`BETWEEN 在指定的两个值之间`.

### 检查单个值

```sql
SELECT prod_name, prod_price
FROM products
WHERE prod_name = 'fuses';
```

> MySQL 在执行匹配时默认不区分大小写。

> 何时使用引号：单/双引号用来限定字符串。

### 范围值检查

```mysql
mysql> SELECT prod_name, prod_price
    -> FROM products
    -> WHERE prod_price BETWEEN 5 and 10;
```

### 空值检查

一个列不包含值时称其为包含空值`NULL`

> NULL(no value) 与字段包含0、空字符串或仅仅包含空格不同。

```mysql
mysql> SELECT prod_name
    -> FROM products
    -> WHERE prod_price IS NULL;
```

> **Warning** `NULL`和不匹配：在过滤数据时不论他们是否被匹配，均不返回`NULL`的行，因为`NULL`具有特殊的含义。

## 数据过滤

本章主要总结如何用 AND 和 OR 操作符组合成 WHERE 子句，如何清晰地管理计算次序(使用圆括号), 如何使用 IN 和 NOT 操作符。

### 组合 WHERE 子句

MySQL 允许多个 WHERE 子句进行组合，具体方式有`AND`和`OR`

### OR 操作符

```mysql
mysql> SELECT prod_name, prod_price
    -> FROM products
    -> WHERE vend_id = 1002 OR vend_id = 1003;
```

#### 计算次序

WHERE 可以包含任意数目的 AND 和 OR 操作符，两者结合可以进行更加复杂和高级的过滤，在处理 OR 操作符前，优先处理 AND 操作符，故应尽可能使用圆括号运算符。

### IN 操作符

IN 操作符用来指定条件范围，范围中的每个条件都将进行匹配。

```mysql
mysql> SELECT prod_name, prod_price
    -> FROM products
    -> WHERE vend_id IN (1002, 1003)
    -> ORDER BY prod_name;
```

从中可以看出 IN 和 OR 操作符有些类似，但使用 IN 操作符有如下几个优点。

- 使用较长的合法选项清单时，IN 操作符的语法更清楚且更直观。
- 计算的次序更容易管理(使用的操作符更少)
- IN 一般比 OR 操作符清单执行更快
- 可以包含其他 SELECT 语句，使其能够更动态地建立 WHERE 子句杀手锏特性！

### NOT 操作符

用于否定 NOT 之后的所有条件。

```mysql
mysql> SELECT prod_desc, prod_name, prod_price
    -> FROM products
    -> WHERE vend_id NOT IN (1002,1003)
    -> ORDER BY prod_price;
```

MySQL 中 NOT 可以对 IN, BETWEEN, EXISTS 子句取反，不是对所有条件都可以取反。

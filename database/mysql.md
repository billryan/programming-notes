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

## 用通配符进行过滤

### LIKE 操作符

前面的章节中所有操作符均是针对已知值进行过滤，有时需要过滤不确定值就需要使用 LIKE 操作符了。

术语：

- 通配符(wildcard) 用来匹配值的一部分的特殊字符。
- 搜索模式(search pattern) 由字面值、通配符或者两者组合构成的搜索条件。

在搜索子句中使用通配符必须使用 LIKE 操作符，LIKE 指示 MySQL 后面的搜索模式利用通配符而不是直接相等匹配。通配符 % 表示0个或者多个字符，注意及时可表示0个字符，但也无法匹配到`NULL`.

```mysql
mysql> SELECT prod_id, prod_name
    -> FROM products
    -> WHERE prod_name LIKE 'jet%';
```

> 可以对 MySQL 进行配置使其搜索区分大小写。

通配符不仅可以用于搜索模式的结尾，还可用于其他任意位置，多个通配符可以同时使用。

```mysql
mysql> SELECT prod_id, prod_name
    -> FROM products
    -> WHERE prod_name LIKE '%anvil%';
```

#### 下划线(_) 通配符

下划线只匹配单个而不是多个字符，也不是0个字符。

```mysql
mysql> SELECT prod_id, prod_name
    -> FROM products
    -> WHERE prod_name LIKE '_ ton anvil';
```

通配符虽好，但也不应过度使用，因为其搜索起来比直接搜索慢。

## 用正则表达式进行搜索

### 使用 MySQL 正则表达式

#### 基本字符匹配

检索列`prod_name` 包含文本.000的所有行：

```mysql
mysql> SELECT prod_name
    -> FROM products
    -> WHERE prod_name REGEXP '.000'
    -> ORDER BY prod_name;
```

`.` 表示匹配任意一个字符，1000和2000都能匹配且返回。

使用 REGEXP 替代了 LIKE, REGEXP 和 LIKE 的区别在于 LIKE 匹配整个列，如果匹配不完全则不返回结果；而 REGEXP 在列值内进行匹配。

MySQL 中的正则表达式自3.23.4版本以后不再区分大小写，但是可以 BINARY 关键字指定。

```sql
WHERE prod_name REGEXP BINARY 'JetPack .000'
```

#### OR 匹配

正则表达式中使用一个或多个`|` 进行 OR 匹配，和 OR 使用效果相同，更为方便。

```mysql
mysql> SELECT prod_name
    -> FROM products
    -> WHERE prod_name REGEXP '1000|2000'
    -> ORDER BY prod_name;
```

#### 匹配几个字符之一

匹配任一特定一组字符中的一个字符，使用'[' 和 `]` 括起来。

```mysql
mysql> SELECT prod_name
    -> FROM products
    -> WHERE prod_name REGEXp '[123] Ton'
    -> ORDER BY prod_name;
```

`[123]`和`[1|2|3]`等价，但是显然前者更为方便。除了正向匹配字符集，我们还可对字符集之外的元素进行匹配，如`[^123]` 能匹配除了1,2,3之外的字符。

#### 匹配范围

虽然使用类似`[123]` 的集合方式能简化多次使用 OR 操作符，但是还可对其进一步简化以处理连续的数字或者字符序列。如使用`[0-9]` 简化`[0123456789]`这种数字列表。

```mysql
mysql> SELECT prod_name
    -> FROM products
    -> WHERE prod_name REGEXP '[1-5] Ton'
    -> ORDER BY prod_name;
```

#### 匹配特殊字符

对于特殊字符的匹配，容易想到的方案为使用转义序列，MySQL 中使用`\\`作为前导序列。

```mysql
mysql> SELECT vend_name
    -> FROM vendors
    -> WHERE vend_name REGEXP '\\.'
    -> ORDER BY vend_name;
```

通常的正则表达式使用一个反斜杠转移字符，MySQL 中要求两个，原因在于 MySQL 自己解释一个，正则表达式解释另一个。

#### 匹配字符类

为了方便常用的匹配模式，我们可以使用预定义的字符集来简化日常的匹配语法。MySQL 中这些预定义的字符集也称为字符类(character class).

#### 匹配多个实例

```
* 0个或多个匹配
+ 1个或多个匹配（等于{1,}）
? 0个或1个匹配（等于{0, 1}）
{n} 指定数目的匹配
{n,} 不少于指定数目的匹配
{n,m} 匹配数目的范围 {m 不超过255}
```

```mysql
mysql> SELECT prod_name
    -> FROM products
    -> WHERE prod_name REGEXP '\\([0-9] sticks?\\)'
    -> ORDER BY prod_name;
```

```mysql
mysql> SELECT prod_name
    -> FROM products
    -> WHERE prod_name REGEXP '[[:digit:]]{4}'
    -> ORDER BY prod_name;
```

#### 定位符

```
^   文本的开始
$   文本的结尾
[[:<:]] 词的开始
[[:>:]] 词的结尾
```

> **Note** ^有两种用法，在集合中(用[和]定义)用来否定该集合，否则用来指串的开始处。

REGEXP 和 LIKE，LIKE 匹配整个串而 REGEXP 匹配子串。但是通过定位符^和$可使 REGEXP 作用和 LIKE 一样。

对正则表达式进行测试：`SELECT 'hello' REGEXP '[0-9]';`

## 创建计算字段

### 计算字段

计算字段的作用：有时我们需要直接从数据库中检索出转换、计算或格式化过的数据，而不是检索出数据。

> 字段(field): 基本上与列(column)意义相同，字段通常用在计算字段的连接上。

> 拼接(concatenate): 将值联结到一起构成单个值。

多数 DBMS 使用 + 或||来实现拼接，MySQL 则使用 `Concat()` 函数来实现。

```mysql
mysql> SELECT Concat(vend_name, ' (', vend_country, ')')
    -> FROM vendors
    -> ORDER BY vend_name;
```
`Concat`需要一个或多个指定的串，各个串之间用逗号分隔。

`Trim()`: 去掉串左右两边的空格
`RTrim()`: 去掉串右边的空格
`LTrim()`: 去掉串左边的空格

由于拼接后的新列只是一个值而无法引用，故 SQL 中使用 AS 关键字赋予列别名，别名也称导出列(derived column).

```mysql
mysql> SELECT Concat(RTrim(vend_name), ' (', RTrim(vend_country), ')') AS
    -> vend_title
    -> FROM vendors
    -> ORDER BY vend_name;
```

### 执行算术计算

```mysql
mysql> SELECT prod_id, quantity, item_price,
    -> quantity * item_price AS expanded_price
    -> FROM orderitems
    -> WHERE order_num = 20005;
```

输出中显示的`expanded_price`为计算字段。

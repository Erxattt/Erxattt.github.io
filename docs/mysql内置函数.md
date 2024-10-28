---
title: mysql内置函数
date: 2023-07-23 16:18:20
tags: [mysql]
categories: [数据库]
feature: /img/mysql/mysql.png
# excerpt: 一些关于mysql的内置函数用法
toc: true
---

### 基本函数

```sql
-- 绝对值
SELECT ABS(-1);

-- 取符号 正数为1 负数为-1
SELECT SIGN(-2),SIGN(2);

-- 圆周率 小数后6位
SELECT PI();

-- 天花板 && 地板(向上取整或向下取整) 33 32
SELECT CEIL(32.22),FLOOR(32.22);

-- 取余
SELECT MOD(13,5);

-- 随机数 0-1 随机的一个数
SELECT RAND();

-- 有参数 且相同的参数出来的值是一样的
SELECT RAND(10);

-- 四舍五入 3 123.5 参数为保留几个小数
SELECT ROUND(3.2), ROUND(123.46,1);

-- 截断函数 保留几个小数 123.2
SELECT TRUNCATE(123.253,1);

-- 进制转换 10的二进制 和 16进制
SELECT BIN(10),HEX(10);

```

### 字符串函数

```sql
-- 返回ascii码
SELECT ASCII('abc');

-- 返回长度 3 6 2
SELECT LENGTH('abc'),LENGTH('我们'),CHAR_LENGTH('我们');

-- 拼接字符串
SELECT CONCAT('hello',' world');

-- 拼接字符串 第一个参数是分隔符 hello-world
SELECT CONCAT_WS('-','hello','world');

-- 向字符串中插入字符 haaaaaoworld 从目标字符串中从下标为2开始替换后面3个字符为插入的字符
SELECT INSERT('helloworld',2,3,'aaaaa');

-- 替换 hemmo
SELECT REPLACE('hello','ll','mm')

-- 大小写 ABC abc
SELECT UPPER('abc'),LOWER('ABC');

-- 左右取
SELECT LEFT('hello',2),RIGHT('hello',3),RIGHT('hello',12);

-- Trim 去空格
SELECT LTRIM(' abc'),RTRIM('abc '),TRIM(' abc ');

-- 重复
SELECT REPEAT('hello',4);

-- 空格 返回n个空格
SELECT LENGTH(SPACE(4));

-- 截取 el
SELECT SUBSTR('hello',2,2);

-- 首次出现位置 3
SELECT LOCATE('l','hello');
```

### 日期与时间函数

```sql
-- 获取时间,日期
SELECT CURDATE(),CURRENT_DATE,CURRENT_TIME,NOW(),SYSDATE(),UTC_DATE(),UTC_TIME();

-- 时间戳 返回 现在时间的时间戳 返回对于时间戳的时间
SELECT UNIX_TIMESTAMP(),FROM_UNIXTIME(1690634352);

-- EXTRCAT 函数 返回时间的特定属性 比如 时分秒 日期等
SELECT EXTRACT(SECOND FROM NOW());
SELECT EXTRACT(MINUTE FROM NOW());
SELECT EXTRACT(DAY FROM NOW());
....

```

### 流程控制函数

```sql
-- 判断第一个字符串返回是否为true 是就返回第二个值 否则返回第三个值 类似三元运算符
SELECT IF(1>0,'hello','world');

-- 第一个参数为null 返回第二个参数
SELECT IFNULL(NULL,'test');
-- 第一种
SELECT last_name,salary,CASE WHEN salary>=15000 THEN'高薪'
WHEN salary>=10000 THEN '中薪'
WHEN salary>=8000 THEN '低薪'
ELSE '垃圾' END "薪资水平"
FROM employees;
-- 第二种
SELECT employee_id,last_name,department_id,salary,CASE department_id
	WHEN 10 THEN
    salary * 1.1
  WHEN 20 THEN
    salary * 1.2
	WHEN 30 THEN
    salary * 1.3
	ELSE
		salary * 1.4
END "details" FROM employees;

```

### 加密与解密

```sql
-- 加密函数 8.0已经弃用
SELECT PASSWORD('mysql');

-- MD5 sha 不可逆
SELECT MD5('mysql'), SHA('mysql');

```

### mysql 信息函数

```sql
-- mysql 版本
SELECT VERSION();
-- 返回mysql服务器连接数
SELECT CONNECTION_ID();
-- mysql 命令行所在的数据库
SELECT DATABASE(),SCHEMA();

SELECT USER(),CURRENT_USER(),SYSTEM_USER(),SESSION_USER(),CHARSET('abc'),COLLATION('abc');

```

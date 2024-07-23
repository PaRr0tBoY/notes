## 一些最重要的 SQL 命令

- **SELECT** - 从数据库中提取数据（查询）
	- 从表中查询选定记录
	- 语法
		- 选中列提取
			- SELECT column1, column2, ... 
			- FROM table_name;
		- 选中所有列并提取
			- SELECT * FROM table_name;
		- 从列中提取非重复值
			- SELECT DISTINCT column1, column2, ...
			- FROM table_name;
	- 注意	
		- 可以一行也可以两行写
		- 字符串要用‘’包围起来，字符串区分大小写
- WHERE - 限定范围
	- 限定所查询的结果集范围
	- 语法
		- SELECT column1, column2, ...
		- FROM table_name
		- WHERE condition;
			- where+条件：= > < >= ,<=, !=,<> 表示（不等于）
			- 逻辑运算：()    not        and         or
				- and，两个条件都成立才查询该记录
				- or，只要有一条成立就查询该记录
				- ()，x > 30 and (y=123 or z=321)
			- 隐式转换：where 1返回所有行中选定列的值，where 0返回空集
			- 特殊条件：
				- **空值判断： is null / not null**
				- **between 100 and 300**
				- in (5000,3000,1500) - 等于5000，3000，1500
				- like - 省略
- ORDER BY - 排序
	- 对结果集按照单列或多列排序
	- 语法
		- SELECT column1, column2, ...
		- FROM table_name
		- ORDER BY column1, column2, ... ASC|DESC;
			- ASC是升序，未指明时默认未ASC
			- DESC为降序
			- ORDER BY 多列的时候，先按照第一个column name排序，在按照第二个column name排序
- **UPDATE** - 更新数据库中的数据
	- 更新表中记录
	- 语法
		- UPDATE table_name
		- SET column1 = value1, column2 = value2, ...
		- WHERE condition;
			- where子句用于指定哪些数据需要修改，一旦遗漏将修改所有记录中的列！
- **DELETE** - 从数据库中删除数据
	- 删除表中记录
	- 语法
		- DELETE FROM table_name
		- WHERE condition;
			- 不加where会删除表中所有行，但是表的结构、索引、属性将保持不变
- **INSERT INTO** - 向数据库中插入新数据
	- 向表中插入新纪录
	- 语法
		- 省略要插入数据的列名
			- INSERT INTO table_name
			- VALUES (value1,value2,value3,...);
		- 指定要插入数据的列名
			- INSERT INTO table_name (column1,column2,column3,...)
			- VALUES (value1,value2,value3,...);
				- 没有指定要插入数据的列名的形式需要列出插入行的每一列数据，相当于插入完整的一行
- **CREATE DATABASE** - 创建新数据库
- **ALTER DATABASE** - 修改数据库
- **CREATE TABLE** - 创建新表
- **ALTER TABLE** - 变更（改变）数据库表
- **DROP TABLE** - 删除表
	- 删的一干二净，释放空间，毫无保留
- **CREATE INDEX** - 创建索引（搜索键）
- **DROP INDEX** - 删除索引

- **use RUNOOB;** 命令用于选择数据库。
- **set names utf8;** 命令用于设置使用的字符集。
- **SELECT * FROM Websites;** 读取数据表的信息。
- 上面的表包含五条记录（每一条对应一个网站信息）和5个列（id、name、url、alexa 和country）。

- SQL 对大小写不敏感：SELECT 与 select 是相同的。

---

## SQL 语句后面的分号？

某些数据库系统要求在每条 SQL 语句的末端使用分号。

分号是在数据库系统中分隔每条 SQL 语句的标准方法，这样就可以在对服务器的相同请求中执行一条以上的 SQL 语句。

在本教程中，我们将在每条 SQL 语句的末端使用分号。

【强制】表名、字段名必须使用小写字母或数字 ， 禁止出现数字开头，禁止两个下划线中间只 出现数字。数据库字段名的修改代价很大，因为无法进行预发布，所以字段名称需要慎重考虑。
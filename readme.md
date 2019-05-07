# 产品经理XX天sql入门到精通  :smiley:
+ [安装mysql](./安装mysql.md)
+ [基本语法与建库建表](./基本语法与建库建表.md)
+ [更新删除数据](./更新删除数据.md)
+ [导入导出以及可视化](./导入导出以及可视化.md)  
+ [基础查询](./基础查询.md)  
+ [聚合查询](./聚合查询.md)
+ [多表查询](./多表查询.md)



登陆本地数据库:`mysql -u root -p`紧跟着输入密码或者回车输入密码    
登陆远程数据库:`mysql -h ip地址 -u 用户名 -p -P 端口`回车输入密码  

|操作|语法|
|----|----|
|创建库|create database 数据库名;|
|删除库|drop  database 数据库名;|
|创建表|create table 表名 (字段 数据类型 [约束],...);|
|删除表|drop table 表名;|
|列出数据库|show databases;|
|列出数据表|show tables;|
|使用切换数据库|use 数据库名;|
|查看数据表结构|explain 数据表名; 或者(desc 数据表名;)|
|表中新增一列|alter table 数据表名 add column 列名称 数据类型 [约束];|
|表中删除一列|alter table 数据表名 drop column 列名称;|
|插入数据|insert into 表名称 (列名称1, 列名称2, ...) values (值1, 值2, ...),...;|
|删除数据|delete from 数据表名 where 约束条件;|
|修改数据|update 数据表名 set 列名称1=值1,列名称2=值2,... where 筛选条件;|

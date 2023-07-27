SpringBoot项目@tableid注解设置IdType.AUTO不生效的解决方法

事故原因

首先造成这个问题的原因可能是我在没有设置@tableid注解的情况下，先用编写的程序插入了一条数据，由于程序默认的主键策略为ASSIGN_ID雪花算法，也就是以类似时间戳的值作为该数据主键值，这就导致后面主键自增的值都是在这个时间戳的基础上+1

解决方法

我要做的就是将Mysql记录的自增值重置一下

先删除之前插入的那条脏数据

再在mysql数据库中执行：ALTER TABLE  库名.表名 AUTO_INCREMENT = 0; 

重新测试

重置之后的自增值就会从已有数据中主键值最大的那条数据开始计算+1。

[SpringBoot项目@tableid注解设置IdType.AUTO不生效的解决方法_抚琴弄心弦的博客-CSDN博客](https://blog.csdn.net/woshisanba56/article/details/128046802)
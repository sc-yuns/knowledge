存储引擎
-

MySQL的核心就是存储引擎

不同的存储引擎有不同的功能，可以通过`SHOW ENGINES`查看服务端支持的引擎类型

### InnoDB

InnoDB是唯一支持事物的存储引擎（8.0.11），5.5.5开始作为默认存储引擎，支持以下特性：

1. 事物。支持行锁定，SELECT提供非锁定读
2. 性能。CPU效率极高
3. 文件。表和索引存储在逻辑表空间中，可以包含数个文件，表可以是任何尺寸
4. 外键。

### MyISAM

MyISAM是基于ISAM（索引顺序存取方法，Indexed Sequential Access Method）拓展的存储引擎，超高的插入、查询速度，
5.5.5之前作为默认存储引擎，支持以下特性：

1. 空间。DML语句混合使用产生更少的碎片
2. 索引。单表最大索引数64，索引最大列数16；BLOB和TEXT可以被索引；
3. 自增。AUTO_INCREMENT内部处理，加快最少10%。在序列的值被删除后不能使用
4. 文件。数据文件和索引文件可在不同目录
5. 字符。每个列可有不同的字符集

### MEMORY

MEMORY将数据存储在内存，支持以下特性：

1. 索引。单表最大索引数32，索引最大列数16，最大键长500B。执行HASH和BTREE索引
2. 列。不支持BLOB和TEXT列

###### InnoDB和MyISAM的对比

|属性|InnoDB|MyISAM|
|事务|支持|不支持|
|外键|支持|不支持|

一、 索引

MyISAM ：索引属于非聚簇索引，索引和行记录分开存储，也就是有单独的区域存储数据。主键索引和其他索引没有本质差异，主键索引叶子存储主键和指针，
其他索引存储列和指针。可以没有主键

InnoDB ：主键索引属于聚簇索引，索引和行记录，没有单独的区域存储数据。主键索引叶子存储主键和数据，其他索引存储主键，
因此不建议使用长列作为主键，会导致其他索引占用内存变大

因此，InnoDB有且只有一个聚簇索引。如果定义了主键则主键作为聚簇索引，否则第一个非空唯一索引作为聚簇索引，否则创建因此的row-id作为聚簇索引

MyISAM

MyISAM引擎是MySQL 5.1及之前版本的默认引擎，它的特点是：

1.不支持行锁，读取时对需要读到的所有表加锁，写入时则对表加排它锁

4.不支持崩溃后的安全恢复

5.在表有读取查询的同时，支持往表中插入新纪录

6.支持BLOB和TEXT的前500个字符索引，支持全文索引

7.支持延迟更新索引，极大提升写入性能

8.对于不会进行修改的表，支持压缩表，极大减少磁盘空间占用

InnoDB

InnoDB在MySQL 5.5后成为默认索引，它的特点是：

1.支持行锁，采用MVCC来支持高并发

4.支持崩溃后的安全恢复

5.不支持全文索引

总体来讲，MyISAM适合SELECT密集型的表，而InnoDB适合INSERT和UPDATE密集型的表

MyISAM速度可能超快，占用存储空间也小，但是程序要求事务支持，故InnoDB是必须的，故该方案无法执行，放弃！




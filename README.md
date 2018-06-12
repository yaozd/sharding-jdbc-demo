# sharding-jdbc-demo
sharding jdbc分库分表和强制路由的例子
### 参考
- shardingJdbc-2.x 分库分表
http://shardingjdbc.io/document/legacy/2.x/cn/02-guide/sharding/
- sharding jdbc + mybatis +spring boot的分库分表实现
https://www.jianshu.com/p/3b2ab87b0de7
### sql-清空table
```
truncate table user_0.user_info_0;
truncate table user_0.user_info_1;
truncate table user_1.user_info_0;
truncate table user_1.user_info_1;
```
### sql-创建table
```
CREATE DATABASE `user_0` /*!40100 DEFAULT CHARACTER SET utf8 */;

CREATE TABLE `user_info_1` (
  `user_id` bigint(19) NOT NULL,
  `user_name` varchar(45) DEFAULT NULL,
  `account` varchar(45) NOT NULL,
  `password` varchar(45) DEFAULT NULL,
  PRIMARY KEY (`user_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;


CREATE TABLE `user_info_0` (
  `user_id` bigint(19) NOT NULL,
  `user_name` varchar(45) DEFAULT NULL,
  `account` varchar(45) NOT NULL,
  `password` varchar(45) DEFAULT NULL,
  PRIMARY KEY (`user_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;


CREATE DATABASE `user_1` /*!40100 DEFAULT CHARACTER SET utf8 */;

CREATE TABLE `user_info_1` (
  `user_id` bigint(19) NOT NULL,
  `user_name` varchar(45) DEFAULT NULL,
  `account` varchar(45) NOT NULL,
  `password` varchar(45) DEFAULT NULL,
  PRIMARY KEY (`user_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;


CREATE TABLE `user_info_0` (
  `user_id` bigint(19) NOT NULL,
  `user_name` varchar(45) DEFAULT NULL,
  `account` varchar(45) NOT NULL,
  `password` varchar(45) DEFAULT NULL,
  PRIMARY KEY (`user_id`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8;

```
### 简单的MYBATIS的示例
```
参考：
com.yzd.canal.root=>com.yzd.example2.h5
```

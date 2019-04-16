[TOC]

# knowledge


## java

### java基础

- [序列化](./java/serialize.md)

## 框架

- [MyBatis教程](./mybatis/mybatis.md)






## 事务

- [分布式事物](./transaction/distributed%20transaction.md)


## spring boot

### spring boot mvc

- [JSON](./spring-boot-mvc-json/json.md)
- [参数校验](./spring-boot-mvc-validate/validate.md)

#### 

- [Spring Boot MyBatis]()

### 源码

- [Spring Boot 启动过程（一）SpringBootApplication](./spring-boot-source-code/SpringBootApplication.md)
- [Spring Boot 启动过程（二）SpringApplication](./spring-boot-source-code/SpringApplication.md)
- [Spring Boot AOP原理](./spring-boot-source-code/AOP.md)














### 领域模型规约

阿里规约（题主只是用VO和DO）

|简写|全写|说明|
|---|---|---|
|DO|Data Object|数据库表映射类，DAO层向上传输数据使用|
|DTO|Data Transfer Object|数据传输对象，Service层向上传输数据使用|
|BO|Business Object|业务对象，Service输出的封装业务逻辑对象|
|AO|Application Object|应用对象，Web层和Service层之间抽象的复用对象|
|VO|View Object|显示层对象，Web向模板传输的对象|
|Query|数据查询对象|各层接收上层的查询请求|

个人使用

|简写|全写|说明|
|---|---|---|
|DO|Data Object|数据库表映射类，DAO层向上传输数据使用|
|PO|Param Object|参数类，封装参数|
|VO|View Object|显示层对象，Web向模板传输的对象|





## Docker

- [修改容器端口](docker/modify_the_container_port.md)

## Java

- [反射 & 泛型](./java/reflect%20&%20generics.md)
- [并发——锁](java/concurrent/lock.md)

## MQ

### RocketMQ

- [介绍](./mq/rocketmq/README.md)
- [安装](./mq/rocketmq/install.md)
- [示例](./mq/rocketmq/example.md)

## MyBatis

- [动态SQL](./mybatis/dynamic_sql.md)

## MySQL

- [数据类型](./mysql/data-type.md)
- [索引使用](./mysql/index.md)
- [存储引擎](./mysql/storage_engines.md)
- [性能优化](./mysql/optimize.md)

## Nginx教程

- [yum安装](./nginx/install-yum.md)
- [docker安装](./nginx/install-docker.md)

## Redis

- [分布式锁](./redis/distributed%20lock.md)

## Spring Boot

- [文件上传](./spring-boot-mvc/file-upload.md)

## Web Server

- [qps](./web-server/qps.md)
- [过滤器和拦截器](https://mp.weixin.qq.com/s/c9d-avYSkhljLNDFVvFggA)

- [DNS](https://mp.weixin.qq.com/s/AeZn1wrN78F0GYEBEeyf7Q)
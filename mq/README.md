消息中间件

1 优点

	解耦：通过Pub/Sub发布订阅消息，解除系统之间的耦合性
	异步：异步处理，快速响应
	削峰：MySQL一般可以支持每秒2K请求，将请求写入消息中间件，慢慢拉取

2 缺点

	可用性降低：请求处理依赖消息中间件
	复杂的提高：需要处理重复消费、消息丢失、消息传递顺序等
	一致性问题：消息消费可能失败，导致数据不一致

3 对比

|特性|ActiveMQ|RabbitMQ|RocketMQ|Kafka|
|---|---|---|---|---|
|单机吞吐量|万级|万级|十万级，高吞吐|十万级，高吞吐，常用与实时计算、日志采集等场景|
|topic对吞吐量影响|||topic在几百/几千时，吞吐量会有较小的下降|topic在几十/几百时，吞吐量会大幅度下降|
|时效性|毫秒|微妙|毫秒|毫秒内|
|可用性|高，通过主从架构实现高可用|高，通过主从架构实现高可用|非常高，分布式架构|非常高，分布式，一个数据多副本，部分宕机不会丢失数据，不会不可用|
|可靠性|较低概率丢失数据||参数优化后可0丢失|参数优化后可0丢失|
|功能支持|极其完备|并发强、性能极好、延时很低|较为完善、分布式、拓展性好|较为简单|
|语言| |Erlang|Java|Scala|

> 常用中间件对比 https://mp.weixin.qq.com/s/bQ9loJHahBLIQ9UpBq4-_Q

4 建议

	ActiveMQ：没有大规模吞吐场景验证，没有活跃社区，不建议
	RabbitMQ：开源、社区活跃，erlang语言开发
	RocketMQ：阿里出品
	Kafka：大数据领域业内标准，社区活跃

###### RocketMQ

[顺序消息](rocketmq/order_message.md)

[事务消息](https://blog.csdn.net/prestigeding/article/details/81318980)

[ACL](https://mp.weixin.qq.com/s/el7miaJGILP0wYjC3v3Twg)

[分布式开放消息系统(RocketMQ)的原理与实践](https://www.jianshu.com/p/453c6e7ff81c)

[分布式事务](http://www.360doc.com/content/19/0403/14/99071_826164585.shtml)

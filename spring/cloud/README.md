Spring Cloud 专题
-

##### 注册中心

注册中心是微服务的核心。用于记录服务和地址的映射关系，维护服务存活状态

下面是已知的注册中心对比，时间：2019.07.01

<table cellpadding="0" cellspacing="0" width="1467" style="width: 556px;"><tbody><tr height="27" style="height:27px;"><td height="27" width="227" style="">Feature</td><td width="209" style="">Consul</td><td width="249" style="">zookeeper</td><td width="240" style="">etcd</td><td width="268" style="">eureka</td><td width="273" style="">nacos</td></tr><tr height="27" style="height:27px;"><td height="27" style="">语言</td><td>GO</td><td>JAVA</td><td>GO</td><td>JAVA</td><td>JAVA</td></tr><tr height="27" style="height:27px;"><td height="27" style="">官网</td><td>https://www.consul.io</td><td>https://zookeeper.apache.org</td><td>https://zookeeper.apache.org</td><td>https://github.com/Netflix/eureka</td><td>https://nacos.io/zh-cn/index.html</td></tr><tr height="27" style="height:27px;"><td height="27" style="">服务健康检查</td><td>服务状态，内存，硬盘等</td><td>(弱)长连接，keepalive</td><td>连接心跳</td><td>可配支持</td><td>连接心跳</td></tr><tr height="27" style="height:27px;"><td height="27" style="">多数据中心</td><td>支持</td><td>/</td><td>/</td><td>/</td><td>/</td></tr><tr height="27" style="height:27px;"><td height="27" style="">kv存储服务</td><td>支持</td><td>支持</td><td>支持</td><td>/</td><td>支持</td></tr><tr height="27" style="height:27px;"><td height="27" style="">一致性</td><td>raft</td><td>paxos</td><td>raft</td><td>/</td><td>raft</td></tr><tr height="27" style="height:27px;"><td height="27" style="">cap</td><td>cp</td><td>cp</td><td>cp</td><td>ap</td><td>ap cp</td></tr><tr height="27" style="height:27px;"><td height="27" style="">使用接口(多语言能力)</td><td>支持http和dns</td><td>客户端</td><td>http/grpc</td><td>http（sidecar）</td><td>客户端</td></tr><tr height="27" style="height:27px;"><td height="27" style="">watch支持</td><td>全量/支持long polling</td><td>支持</td><td>支持 long polling</td><td>支持 long polling/大部分增量</td><td>支持 long polling</td></tr><tr height="27" style="height:27px;"><td height="27" style="">自身监控</td><td>metrics</td><td>/</td><td>metrics</td><td>metrics</td><td>metrics</td></tr><tr height="27" style="height:27px;"><td height="27" style="">安全</td><td>acl /https</td><td>acl</td><td>https支持（弱)</td><td>/</td><td>/</td></tr><tr height="27" style="height:27px;"><td height="27" style="">spring cloud集成</td><td>支持</td><td>支持</td><td>支持</td><td>支持</td><td>支持</td></tr></tbody></table>

- [Spring Cloud 服务注册 - Nacos](/nacos/spring_cloud_discovery_provider.md)
- [Spring Cloud 服务消费 - Nacos](/nacos/spring_cloud_discovery_consumer.md)

##### 负载均衡

负载均衡是系统架构中一个非常重要的内容。可以提高系统的高可用、缓解网络压力、处理能力扩容

Spring Cloud 通过 @LoadBalanced 注解标记 RestTemplate 等客户端，实现负载均衡功能

- [Spring Cloud 负载均衡 - Ribbon](/ribbon/spring_cloud_loadbalancer.md)

[@LoadBalanced](LoadBalanced.md)

##### 配置中心

- [Spring Cloud 配置中心 - Nacos](/nacos/spring_cloud_config.md)

##### 网关组件

- [Spring Cloud Gateway](spring_cloud_gateway.md)
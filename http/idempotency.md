幂等性
-

幂等性：一次请求和多次请求最终的结果是一样的

### 解决方案

1. 连续点击导致重复提交

访问页面时，生成唯一ticket_id/token，第一次提交时删除，后面的提交则不处理

2. 乐观锁

通过版本号的解决问题

3. 悲观锁

SELECT * FROM xxx FOR UPDATE

4. 分布式锁

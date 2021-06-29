# 前言

以下是通过我最近面试前的一系列面试笔记整理出来的PHP和GO面试的一些面经，希望对大家有所帮助。几乎每一个知识点都会提供参考链接，如未提供或大家觉得我提供的不够好，可自己查阅

# php

1. php5和php7数组的区别，php7对数组做了哪些优化。[php5数组](https://www.cnblogs.com/s-b-b/p/6222198.html)，[php7数组](https://github.com/pangudashu/php7-internal/blob/master/2/zend_ht.md)
2. [cgi与fast-cgi](https://www.yuque.com/vergil0415/mqoc5g/kuqrf0)
3. [array_merge和+（加号）的区别](https://blog.csdn.net/jbh1224520/article/details/60151817)
4. [PHP 里的 self::class、static::class](https://blog.csdn.net/m0_37477061/article/details/88650175)
5. 简述一个请求从客户端发出到php服务又返回给客户端的全流程
6. opcache，[资料1](https://www.zybuluo.com/phper/note/1016714)，[资料2](https://www.cnblogs.com/lamp01/p/8985068.html)
7. [php生命周期](https://github.com/pangudashu/php7-internal/blob/master/1/base_process.md)
8. [php-fpm](https://github.com/pangudashu/php7-internal/blob/master/1/fpm.md)
9. [php垃圾回收](https://github.com/pangudashu/php7-internal/blob/master/5/gc.md)

php实际上问的不太多，并且像3，4这样的问题自己感觉了解即可，面试的时候拿出来问总让我感觉是在面刚毕业的大学生。

# golang

1. new和make的区别
2. slice源码层面，[资料1](https://draveness.me/golang/docs/part2-foundation/ch03-datastructure/golang-array-and-slice/)，[资料2](https://halfrost.com/go_slice/)
3. slice的len和cap: 容量表示底层数组的大小，长度是你可以使用的大小。(len以内的元素可以被直接访问到，而len到cap之间暂时无法被访问)
当你用 append扩展长度时，如果新的长度小于容量，不会更换底层数组，否则，go 会新申请一个底层数组，拷贝这边的值过去，把原来的数组丢掉。也就是说，容量的用途是：在数据拷贝和内存申请的消耗与内存占用之间提供一个权衡。
而长度，则是为了帮助你限制切片可用成员的数量，提供边界查询的。所以用 make 申请好空间后，需要注意不要越界访问元素【越 len 】
4. map：[资料1](https://i6448038.github.io/2018/08/26/map-secret/)，[资料2](http://yangxikun.github.io/golang/2019/10/07/golang-map.html)
5. defer：Go 多defer执行顺序：defer函数用栈存储，先进后出，[资料1](https://segmentfault.com/a/1190000006823652)，[资料2](https://sanyuesha.com/2017/07/23/go-defer/)
6. slice排序：实现sort包中的Interface接口（对，这个接口就叫Interface，大写的i），Less, Swap, Len三个方法
7. map官方并发安全map：[Go 1.9 sync.Map揭秘](https://colobu.com/2017/07/11/dive-into-sync-Map/)
8. [go编译原理](https://xiaomi-info.github.io/2019/11/13/golang-compiler-principle/)
9. gc：[资料1](https://draveness.me/golang/docs/part3-runtime/ch07-memory/golang-garbage-collector/)，[资料2](http://yangxikun.github.io/golang/2019/12/22/golang-gc.html)，[资料3](https://zhuanlan.zhihu.com/p/105571503)
10. [逃逸分析](https://zboya.github.io/post/golang_escape_analysis/)
11. [内联优化](Golang内联优化)
12. [Golang 内存管理](https://draveness.me/golang/docs/part3-runtime/ch07-memory/golang-memory-allocator/)
13. [groutine 堆栈](http://yangxikun.github.io/golang/2019/11/12/go-goroutine-stack.html)
14. goroutine泄露处理：[资料1](https://zhuanlan.zhihu.com/p/74090074)，[资料2](https://studygolang.com/articles/28416)，[资料3](https://blog.csdn.net/tencent_teg/article/details/103813995)
15. [Golang channel](https://studygolang.com/articles/20714)
16. [Go的goroutine调度 GPM](https://zboya.github.io/post/go_scheduler/)
17. [Go中锁的实现](https://draveness.me/golang/docs/part3-runtime/ch06-concurrency/golang-sync-primitives/)
18. [go的单例模式](https://studygolang.com/articles/11444)
19. 协程进程线程的区别：进程是分配资源的最小单位，线程是CPU可调度的最小单位，操作系统层面没有协程概念，协程是用户级的轻量级线程，无需cpu调度，但需要实现自己的调度系统。[资料1](https://juejin.im/post/5b0014b7518825426e023666)，[资料2](https://blog.csdn.net/weixin_43870646/article/details/86575142)

# mysql

**重要**：mysql我是通读了一遍《mysql是怎样运行的》一书（《mysql技术内幕--innodb存储引擎》也可），通读完书之后，大部分以下提到的知识点可以直接跳过，书中都有详细描述，并且书更系统，所以强烈推荐通读这两本书之一。

在此之外，mysql的大部分内容如下

1. [myisym 和innodb的区别](https://blog.csdn.net/xlgen157387/article/details/68978320)
2. [ACID](https://zh.wikipedia.org/wiki/ACID)
3. [聚簇索引的特性](https://blog.csdn.net/alexdamiao/article/details/51934917)
4. [mysql语句执行过程]( https://www.cnblogs.com/wyq178/p/11576065.html)
5. MVCC：[资料1](https://www.jianshu.com/p/0ef46997c300)，[资料2](https://juejin.im/post/5c68a4056fb9a049e063e0ab)，[资料3](https://juejin.im/post/5c9b1b7df265da60e21c0b57)
6. [锁和MVCC](https://draveness.me/database-concurrency-control)
7. B树和B+树：[资料1](https://juejin.im/post/5c68a0ea51882562c704ed75)，[资料2](https://stackoverflow.com/questions/870218/what-are-the-differences-between-b-trees-and-b-trees)
8. [mysql索引机制](https://juejin.im/post/5c68a2cde51d4501533df085)
9. [MySQL事务隔离级别](https://juejin.im/post/5c68a34551882562ec590924)
10. InnoDB锁机制:[资料1](https://juejin.im/post/5c68a3b4e51d457f136d22d0)，[资料2](https://zhuanlan.zhihu.com/p/48269420)
11. redoLog: [资料1](https://juejin.im/post/6844903778030714894)，[资料2](https://www.cnblogs.com/f-ck-need-u/archive/2018/05/08/9010872.html)
12. [undoLog](https://juejin.im/post/5c68a5e551882562eb50ee41)
13. [最左匹配](https://www.zhihu.com/question/36996520)
14. mysql 查询优化器
15. [binLog](https://www.cnblogs.com/f-ck-need-u/p/9001061.html#auto_id_4)
16. innodb页: [资料1](https://www.cnblogs.com/wade-luffy/ttps://www.cnblogs.com/xiaoboluo768/p/5191964.htmlp/6289917.html)，[资料2](https://juejin.im/post/5cb3e3dfe51d456e3428c0db)，[资料3](https://mp.weixin.qq.com/s?__biz=MzIxNTQ3NDMzMw==&mid=2247483670&idx=1&sn=751d84d0ce50d64934d636014abe2023&chksm=979688e4a0e101f2a51d1f06ec75e25c56f8936321ae43badc2fe9fc1257b4dc1c24223699de&scene=21#wechat_redirect)
17. [共享表空间&独立表空间]( https://www.cnblogs.com/ilifeilong/p/7221235.html)
18. [mysql分区](ttps://www.cnblogs.com/xiaoboluo768/p/5191964.html)
19. [mysql二次写](https://blog.csdn.net/jc_benben/article/details/78967380)
20. mysql主从延迟解决: a. 排查master的负载，是否有大事务的执行，在主从同步的场景下，大事务会阻塞主从同步（5.6之前）b. 使用多从的方式，降低从服务器的负载，进一步提升主从同步效率 c. 使用多线程主从同步 d. 使用更好的从服务器的硬件设备 e. 关闭从服务器的一些配置，比如不生成binlog。innodb_flushlog也可以设置为0来提高从服务器的执行性能。[资料1](https://developer.aliyun.com/article/42638)， [资料2](https://www.jianshu.com/p/ed19bb0e748a)
21. [隐式转换](https://www.cnblogs.com/wtcl/p/9085427.html)
22. 事务回滚的原理
23. count(*) 慢该如何解决
24. 对于千万级的大表，mysql 怎么优化
25. sql 用 join 好，还是多次 select 好，为什么
26. 数据库中间件: [shardingsphere](https://shardingsphere.apache.org/document/current/cn/overview/)，myCat
27. [大众点评分库分表实践](https://tech.meituan.com/dianping_order_db_sharding.html)
28. [乐观锁/悲观锁](https://www.jianshu.com/p/d2ac26ca6525)

# Redis
redis例举出的内容不太多，强烈建议通读《Redis设计与实现》

1. redis持久化 
2. 7种基础类型: SDS, 整数集合，字典，压缩链表，跳表，快速链表（新版本引入)，链表（废弃）
3. [为什么用跳跃表不用树](https://zhuanlan.zhihu.com/p/23370124)
4. 跳表查询的过程：查找数据M的时候，首先查找最高层的链表，找到最后一个小于等于待查数据的节点node，然后从下一层节点里面的包含了和node包含的数据一样的节点开始查找。重复上述动作，直到找到为止。对于上面的例子，如果我们要查找8的话，首先查找第4层，止步的数据为1，继续查找第3层，中止的数据为4，查找第2层，从4开始，止步的数据为7，查找第1层，从7开始，止步的数据为8。查询结束。
5. rehash的一个过程
6. 分布式锁/setnx： [资料1](https://www.cnblogs.com/austinspark-jessylu/p/8043726.html)， [资料2](https://yq.aliyun.com/articles/674394)
7. redis网络模型
8. redis过期键删除策略(定时删除，惰性删除)
9. redis内存不够时的key删除策略
10. redis主从集群
11. redis哨兵 
12. [脑裂问题](https://cloud.tencent.com/developer/article/1027323)
13. raft一致性算法: [原理模拟](http://thesecretlivesofdata.com/raft/) [原理模拟2](https://acehi.github.io/raft-algorithm-cn/)
14. redis主从同步
15. redis多线程 [资料1](https://mp.weixin.qq.com/s/FZu3acwK6zrCBZQ_3HoUgw), [资料2](https://draveness.me/whys-the-design-redis-single-thread/)
16. [一致性哈希算法](https://www.yuque.com/vergil0415/nsnq75/gxadgh)


# 操作系统

1. [I/O多路复用](https://i6448038.github.io/2019/11/10/io-multi/)
2. [epool](https://mp.weixin.qq.com/s/DVjFI4CVZwtjiV6e9LeY3A)

# 系统设计
1. 限流：[资料1](https://blog.csdn.net/weixin_41846320/article/details/95941361)，[资料2](https://www.cnblogs.com/linjiqin/p/9707713.html)
2. 熔断：[资料1](https://www.cnblogs.com/yawen/p/6655352.html)，[资料2](https://blog.csdn.net/baiducheng/article/details/78892111)
3. [微服务cap理论](https://www.hollischuang.com/archives/666)
4. [微服务BASE理论](https://www.hollischuang.com/archives/672)
5. 服务发现与服务注册
6. [微服务设计](https://www.zhihu.com/question/65502802)
7. [秒杀系统](https://www.zhihu.com/question/54895548/answer/923987542?clicktime=1579081979)
8. 整个项目高并发，怎么保证业务可用性
9. 分布式事务：[资料1](https://blog.51cto.com/lijianjun/1945516), [资料2](https://juejin.im/post/5d2616256fb9a07eef6a3619)
10. [什么是中台](https://www.zhihu.com/question/57717433)
11. [什么是引擎](https://blog.csdn.net/shenpanzhimao/article/details/84500521)
12. 短链服务设计: [资料1](https://www.jianshu.com/p/bae7796d3215), [资料2](https://blog.csdn.net/liuxinghao/article/details/107754046)
13. [消息总线架构](https://segmentfault.com/a/1190000017212260)

# linux

1. nginx access 日志统计访问前十的ip：其实算是对linux命令的一个综合测试，这一个命令就考察了linux中awk, sort, uniq, head 这4个命令的考察(cat nginx-access.log | awk -F , '{print $4}' | sort | uniq -c | sort -rn -k 1 | head -n 10)
2. [sort命令](https://www.cnblogs.com/51linux/archive/2012/05/23/2515299.html)

# 网络

1. [TCP/IP](https://www.cnblogs.com/onepixel/p/7092302.html)
2. 三次握手 [资料1](https://baijiahao.baidu.com/s?id=1618114723935605183&wfr=spider&for=pc), [资料2](https://networkengineering.stackexchange.com/questions/24068/why-do-we-need-a-3-way-handshake-why-not-just-2-way), [资料3](https://blog.csdn.net/xifeijian/article/details/12777187)
3. [四次挥手](https://blog.csdn.net/xifeijian/article/details/12777187)
4. [拥塞控制的四个过程](https://blog.csdn.net/yechaodechuntian/article/details/25429143)
5. TCP滑动窗口：[资料1](https://www.zhihu.com/question/32255109)，[资料2](https://blog.csdn.net/yao5hed/article/details/81046945)
6. [TCP TIME_WAIT](https://blog.csdn.net/weixin_41966991/article/details/81264095)
7. [http/https的区别](https://juejin.im/entry/58d7635e5c497d0057fae036)
8. [http 1.0 1.1 2.0](https://www.jianshu.com/p/52d86558ca57)
9. [http 2.0新特性](https://www.zhihu.com/question/34074946): (1)多路复用，(2)在http应用层和tcp传输层之间添加二进制分帧层，(3)server push
10. [反向代理与正向代理的区别](https://www.zhihu.com/question/36412304)

# 安全

1. [xss](https://www.freebuf.com/articles/web/185654.html)
2. csrf

# 算法
算法推荐看极客时间覃超的《算法面试40讲》，是视频课，讲的很棒，跟着看完之后再在leetcode上刷四五十题就能应付大部分的算法面试了，最重要的是有解题思路。

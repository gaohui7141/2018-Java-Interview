## 理论
CAP原则又称CAP定理，指的是在一个分布式系统中，Consistency（一致性）、 Availability（可用性）、Partition tolerance（分区容错性），三者不可兼得。

分布式系统的CAP理论：理论首先把分布式系统中的三个特性进行了如下归纳：

* 一致性（C）：在分布式系统中的所有数据备份，在同一时刻是否同样的值。（等同于所有节点访问同一份最新的数据副本）
* 可用性（A）：在集群中一部分节点故障后，集群整体是否还能响应客户端的读写请求。（对数据更新具备高可用性）
* 分区容错性（P）：以实际效果而言，分区相当于对通信的时限要求。系统如果不能在时限内达成数据一致性，就意味着发生了分区的情况，必须就当前操作在C和A之间做出选择。

CAP理论就是说在分布式存储系统中，最多只能实现上面的两点。而由于当前的网络硬件肯定会出现延迟丢包等问题，所以分区容忍性是我们必须需要实现的。

## 个人理解
分区容错性是指能否对分布式系统中对数据不一致的容忍，那么在当前硬件条件下是肯定会出现不一致的情况，所以需要在一致性和可用性中进行选择。

如果选择一致性，则需要将数据同步更新到所有节点上，每次写操作就都要等待全部节点写成功，会导致可用性的降低。  
如果选择可用性，就需要将数据复制到很多个节点，需要复制的数据很多，复制的过程缓慢，会导致一致性的降低

BASE理论的核心思想是：即使无法做到强一致性，但每个应用都可以根据自身业务特点，采用适当的方式来使系统达到最终一致性。

欢迎光临[我的博客](http://www.wangtianyi.top/?utm_source=github&utm_medium=github)，发现更多技术资源~

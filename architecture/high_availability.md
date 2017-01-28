### 高可用系统

#### 涉及哪些方面
1. 软硬件冗余 - 难点在于有状态的结点的数据复制和数据一致性的保证
2. 故障检测和恢复
3. 无法冗余的节点提高可靠性,例如DNS

#### 冗余结点的困难之处
* 如果系统的数据镜像到冗余结点是异步的，那么在failover的时候就会出现数据差异的情况。
* 如果系统在数据镜像到冗余结点是同步的，那么就会导致冗余结点越多性能越慢。

#### 总结一下高可用的设计原理：
* 要做到数据不丢，就必需要持久化
* 要做到服务高可用，就必需要有备用（复本），无论是应用结点还是数据结点
* 要做到复制，就会有数据一致性的问题。
* 我们不可能做到100%的高可用，也就是说，我们能做到几个9个的SLA。
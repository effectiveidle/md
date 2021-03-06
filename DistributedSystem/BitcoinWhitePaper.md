# 1.Introduction

一个基于加密证明的电子支付系统取代原来的基于信任的基础模型

这篇论文提供了一个基于点对点的分布式的时间戳服务器去生成基于时间序列的电子交易证明，从而解决双重支付问题。只要诚实的节点全体所控制的计算能力的总和，大于联合攻击节点的计算能力的总和，该系统就是安全的。

# 2.Transaction

解决DSA，需要关注的只是于本交易之前发生的交易，因此交易信息应当被公开宣布

收款人需要确保在该交易期间，大多数节点都同意该交易是首次出现

# 3.TimeStamp Server

每个时间戳都将前一个时间戳纳入其随机散列值中

# 4.Proof-of-Work

# 难度将采用移动平均目标的方法来确定

# 5.Network

 

# 7

不含交易的区块头大小仅有80Bytes，一年产生4.2MB（80 * 6 * 24 * 365）

 

# 9

一般是之前某个价值较大的交易构成单一输入或者某几个价值较小的交易共同构成的并行输入

但是输出只有两个，一个用于支付，另一个需要找零的话用于找零

# 10

使用者可以让每次交易都生成一个新的地址，以确保这些交易不被追溯到一个共同的所有者。

但是由于并行输入的存在，一定程度上的追溯还是不可避免的，因为并行输入表明这些货币都属于同一个所有者
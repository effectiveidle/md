# CAP

<img src="../img/v2-44e5fb78a506c61d3f03169b8ab43c27_720w.jpg" alt="img" style="zoom: 50%;" />

# Paxos

- 基于**消息传递**的分布式一致性算法，保证一定的可用性的同时，能够对外提供强一致性
- 分布式一致性的根本要求

client对一台服务器提出某种操作的请求后，如何使得其它所有服务器也同意，并一起执行这个操作

- 前置假设：消息不会被篡改，但可能延迟或丢失
- Paxos算法通过一个决议分为两个阶段

![通过一个决议的流程](../img/v2-a6cd35d4045134b703f9d125b1ce9671_r.jpg)

每条消息的描述如下：

- **Prepare**：Proposer生成全局唯一且递增的Proposal ID
- **Promise**：Acceptors收到Prepare请求后，做出两个承诺，一个应答

 两个承诺：

1. 不再接收Proposal ID ≤ 当前请求的Prepare请求
2. 不再接收Proposal ID < 当前请求的Propose请求

一个应答：

回复已经Accept过的提案中Proposal ID最大的那个提案的value和Proposal ID
## 合约实例执行

单点合约单点执行，集群合约则在该集群的所有节点上执行

## Http接口

`http://xxx.xxx.xxx.xxx:8080/SCIDE/SCManager` 为提供Http接口服务的服务器

参数：`?action=`

调用合约：

| 字段                 | 值                          |
| -------------------- | --------------------------- |
| action               | executeContract             |
| contractID           | 合约ID                      |
| *withDynamicAnalysis | true/false 是否进行动态分析 |
| operation            | 调用合约的方法名            |
| arg                  | 调用合约的参数              |
| *pubkey              | 可选，调用者公钥            |
| *signature           | 可选，签名                  |

`sm2.doSignature("action—pubkey", "privateKey");`

##  YJS

结构：变量、函数、事件

### 变量

全局变量和局部变量，所有变量都是动态类型、

### 函数

普通函数和用export关键字修饰的exported函数


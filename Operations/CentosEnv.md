- ## Env

- vscode-RemoteSSH重新配置一个服务器时清空known_hosts文件的内容

- centos-version-7.4-152.136.255.208

- ## GO-1.15.6

- ### 安装、解压

- 目录：/root/work

- wget https://studygolang.com/dl/golang/go1.10.6.linux-amd64.tar.gz

- tar -zxvf go1.12.5.linux-amd64.tar.gz 

- ### 配置go环境变量

- vi /etc/profile

- 在最后添加

- \#go setting

- export GOROOT=/root/work/go

- export GOPATH=/root/work/gopath

- export PATH=$PATH:$GOROOT/bin

- 保存退出，执行 source /etc/profile让环境变量生效

- 新建/root/work/gopath/src/hello目录，vim写hello.go运行

- ### iris框架-11.2.0

- ## MySQL-5.6.50

- 目录：/usr/local/src

- ### 卸载系统自带的mariadb

- rpm -qa | grep mariadb

- rpm -e --nodeps mariadb-libs-5.5.65-1.el7.x86_64

- ### 安装mysql

- wget http://repo.mysql.com/mysql57-community-release-el7-8.noarch.rpm

- rpm -ivh mysql57-community-release-el7-8.noarch.rpm，下载mysql所有依赖

- yum -y install mysql-server

- 回到~目录，service mysqld restart ，重新启动mysql

- grep "password" /var/log/mysqld.log，**查看初始密码**

- mysql -u root -p ……登录

- set PASSWORD=PASSWORD('newPassword')修改密码Ssyhy949.

- flush privileges**刷新权限**

- ## RabbitMQ-3.6.10

- 下载、安装erlang

- wget http://www.rabbitmq.com/releases/erlang/erlang-19.0.4-1.el7.centos.x86_64.rpm

- rpm -ivh erlang-19.0.4-1.el7.centos.x86_64.rpm

- 下载、安装RabbitMQ

- wget http://www.rabbitmq.com/releases/rabbitmq-server/v3.6.10/rabbitmq-server-3.6.10-1.el7.noarch.rpm

- yum install socat

- rpm -ivh rabbitmq-server-3.6.10-1.el7.noarch.rpm

- 启动：systemctl start rabbitmq-server

- 修改配置文件：

- cd /etc/rabbitmq/，vim rabbitmq.config，添加[{rabbit, [{loopback_users, []}]}].

- /sbin/rabbitmq-plugins enable rabbitmq_management，安装插件

- service rabbitmq-server restart

- 默认账号密码：guest

- 进入：152.136.255.208:15672

- ## Git-1.8.3.1

- yum -y install git

- 将git加入Path中

-  
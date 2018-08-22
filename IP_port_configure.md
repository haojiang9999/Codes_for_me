####打开端口这个配置外网连接好用
```
sudo iptables -A INPUT -m state --state NEW -m tcp -p tcp --dport 8787 -j ACCEPT
```
####nmap工具检测开放端口
https://www.cnblogs.com/kerrycode/p/5609010.html

nmap是一款网络扫描和主机检测的工具。nmap的安装非常简单，如下所示rpm安装所示。
```
sudo rpm -vhU https://nmap.org/dist/nmap-7.70-1.x86_64.rpm
```
关于nmap的使用，都可以长篇大写特写，这里不做展开。如下所示，nmap 127.0.0.1 查看本机开放的端口，会扫描所有端口。 当然也可以扫描其它服务器端口。
```
[root@DB-Server Server]# nmap 127.0.0.1

Starting Nmap 4.11 ( http://www.insecure.org/nmap/ ) at 2016-06-22 15:46 CST
Interesting ports on localhost.localdomain (127.0.0.1):
Not shown: 1674 closed ports
PORT     STATE SERVICE
22/tcp   open  ssh
25/tcp   open  smtp
111/tcp  open  rpcbind
631/tcp  open  ipp
1011/tcp open  unknown
3306/tcp open  mysql
```
####netcat工具检测端口是否开放。
```
[root@DB-Server ~]# nc -vv 192.168.42.128 1521
Connection to 192.168.42.128 1521 port [tcp/ncube-lm] succeeded!
[root@DB-Server ~]# nc -z 192.168.42.128 1521; echo $?
Connection to 192.168.42.128 1521 port [tcp/ncube-lm] succeeded!
0
[root@DB-Server ~]#  nc -vv 192.168.42.128 1433
nc: connect to 192.168.42.128 port 1433 (tcp) failed: No route to host
```
wget检测端口
```
[root@DB-Server ~]# wget 192.168.42.128:1433

```
#####端口命令

1.开放端口命令：
https://www.cnblogs.com/gudi/p/7841912.html
```
iptables -I INPUT -p tcp --dport 8080 -j ACCEPT
```
2.查看端口是否开放：
```
iptables -L -n
netstat -an | grep 8881
```
3：lsof 工具检测开放端口
有没有开放状态不一样
```
[root@DB-Server Server]# service mysql start
Starting MySQL......[  OK  ]
[root@DB-Server Server]# lsof -i:3306
COMMAND  PID  USER   FD   TYPE DEVICE SIZE NODE NAME
mysqld  7860 mysql   15u  IPv6  44714       TCP *:mysql (LISTEN)
[root@DB-Server Server]# service mysql stop
Shutting down MySQL..[  OK  ]
[root@DB-Server Server]# lsof -i:3306
[root@DB-Server Server]#
```
3.保存：

```
/etc/rc.d/init.d/iptables save
```
3.重启服务：/etc/init.d/iptables restart

4.查看端口是否开放：/sbin/iptables -L -n

####想要外部电脑连接还需要对路由器进行端口投射
路由器 端口转发
https://www.192ly.com/qiu-zhu/r-dkys.html

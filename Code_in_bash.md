### 关于在bash中写代码的注意事项
1.关于while循环
https://blog.csdn.net/feixiaohuijava/article/details/53129413
Shell中while循环的done 后接一个重定向<

利用重定向符<
```
while read LINE
do
    echo $LINE
done < /sites/linuxpig.com.txt
done <$1 #我的是这个样子的
```
2.vim的用法
```
:set ff=unix #转换为unix格式
:wq #保存、退出
:set invlist #即可以将不可见的字符显示出来
:set nolist #可以回到正常的模式。
```
3.字符串截取命令
https://www.cnblogs.com/fetty/p/4857158.html
```
# 号截取，删除左边字符，保留右边字符。
echo ${var#*//}
其中 var 是变量名，# 号是运算符，*// 表示从左边开始删除第一个 // 号及左边的所有字符
即删除 http://
结果是 ：www.google.com/test.htm
```
4.kill命令如何一次杀死多个进程
https://segmentfault.com/q/1010000007245878?_ea=1283719
```
ps aux|grep php|grep -v grep|awk '{print $2}'|xargs kill -9
#如果进程中有斜杠的话可以转义

ps aux|grep task\/crond|grep -v grep|awk '{print $2}'|xargs kill -9
```
5. find 的使用方法
https://www.cnblogs.com/archoncap/p/6144369.html
```
find ./ -name *.gz |xargs ls|wc -l
```
6. 列出特定大小文件
https://stackoverflow.com/questions/13282786/list-files-over-a-specific-size-in-current-directory-and-all-subdirectories
```
#找到大于0k 的文件
find . -size +0k -name '*separate.sh.log'|xargs ls -lh|wc -l 
```
7.scp 考本本机带进度条
http://www.veryhuo.com/a/view/18239.html
```
scp -vr /mnt/yidong2/full20100526.tar.gz root@127.0.0.1:/mnt/yidong1/ 
```
8.查看系统配置
https://www.cnblogs.com/alwu007/p/6024631.html
```
#lscpu：显示cpu架构信息
[xxx@localhost ~]$ lscpu
#cat /proc/cpuinfo：查看CPU详细信息
[xxx@localhost ~]$ cat /proc/cpuinfo 
#内存
free -h
```
9.top的各种用法
https://www.cnblogs.com/zhoug2020/p/6336453.html
```
top 运行中可以通过 top 的内部命令对进程的显示方式进行控制。内部命令如下：
s – 改变画面更新频率
l – 关闭或开启第一部分第一行 top 信息的表示
t – 关闭或开启第一部分第二行 Tasks 和第三行 Cpus 信息的表示
m – 关闭或开启第一部分第四行 Mem 和 第五行 Swap 信息的表示
N – 以 PID 的大小的顺序排列表示进程列表
P – 以 CPU 占用率大小的顺序排列进程列表
M – 以内存占用率大小的顺序排列进程列表
h – 显示帮助
n – 设置在进程列表所显示进程的数量
q – 退出 top
s – 改变画面更新周期
```

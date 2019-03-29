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

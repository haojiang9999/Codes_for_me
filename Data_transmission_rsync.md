#### 服务器间数据传递
https://www.cnblogs.com/noxy/p/8986164.html
https://blog.csdn.net/a351945755/article/details/38089349
https://blog.csdn.net/loophome/article/details/45767345
rsync 命令
rsync 是一个功能非常强大的工具，其命令也有很多功能选项。rsync 的命令格式为：

1）本地使用：
rsync [OPTION...] SRC... [DEST]

2）通过远程 Shell 使用：
```
拉: rsync [OPTION...] [USER@]HOST:SRC... [DEST]
推: rsync [OPTION...] SRC... [USER@]HOST:DEST
```
3）访问 rsync 服务器:
```
拉: rsync [OPTION...] [USER@]HOST::SRC... [DEST]
推: rsync [OPTION...] SRC... [USER@]HOST::DEST
拉: rsync [OPTION...] rsync://[USER@]HOST[:PORT]/SRC... [DEST]
推: rsync [OPTION...] SRC... rsync://[USER@]HOST[:PORT]/DEST
```

从别的服务器拷贝到本地文件
```
rsync -rv --progress --exclude=HCA/Rawdata [user]@[ip]:[path] [path]
```

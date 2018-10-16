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

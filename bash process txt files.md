#### txt 文件读取
https://www.cnblogs.com/wangbaihan/p/9262296.html
```
#普通文档
cat testMet100.txt | awk -F ' ' '{print $10}'|sort| uniq -c
#压缩文档
zcat testMet100.txt.gz | awk -F ' ' '{print $10}'|sort| uniq -c
```

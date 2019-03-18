#### txt 文件读取
https://www.cnblogs.com/wangbaihan/p/9262296.html
```
#普通文档
cat testMet100.txt | awk -F ' ' '{print $10}'|sort| uniq -c
#压缩文档
zcat testMet100.txt.gz | awk -F ' ' '{print $10}'|sort| uniq -c
```
#### txt 文件处理
https://www.cnblogs.com/emanlee/p/3327576.html
```
awk '/101/'    file      显示文件file中包含101的匹配行。 
awk '/101/,/105/'  file 
awk '$1 == 5'    file 
awk '$1 == "CT"'    file    注意必须带双引号 
awk '$1 * $2 >100 '   file  
awk '$2 >5 && $2<=15'  file
```

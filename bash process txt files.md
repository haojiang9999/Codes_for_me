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
awk '/101/'    file      # 显示文件file中包含101的匹配行。 
awk '/101/,/105/'  file 
awk '$1 == 5'    file       #数字可以不用带
awk '$1 == "CT"'    file    # 字符注意必须带双引号 
awk '$1 * $2 >100 '   file  
awk '$2 >5 && $2<=15'  file
```
#### 统计文本行数的方法
https://www.cnblogs.com/mikasama/p/8032389.html
```
awk 'END{print NR}' test1.txt
```
#### 只输出文本第一列
https://www.unix.com/unix-for-dummies-questions-and-answers/122496-select-first-column-file.html
```
cut -f 1 < output > otherfile
awk '{ print $1 }' output > otherfile
```
#### Linux：cut命令详解
https://www.cnblogs.com/Spiro-K/p/6361646.html
```
#使用 -d 选项指定字段分隔符：
cut -f2 -d";" test2.txt
```


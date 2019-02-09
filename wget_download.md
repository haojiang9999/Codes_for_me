####download files frome http
https://www.cnblogs.com/semonxv/p/3816366.html

#####14、使用wget -r -A下载指定格式文件 
可以在以下情况使用该功能 

下载一个网站的所有图片 

下载一个网站的所有视频 

下载一个网站的所有PDF文件 
```
wget -r -A.pdf url 
```
这个命令会把该网站所有类型文件下载下来所以不能用！！！

修改下
```
wget -A .gz -np -r -nd http://fantom.gsc.riken.jp/5/suppl/Hon_et_al_2016/data/assembly/lv3_robust/
```
这样就行了~
#### 使用wget -i下载多个文件 
首先，保存一份下载链接文件 

cat > filelist.txt 
url1 
url2 
url3 
url4 
接着使用这个文件和参数-i下载 
```
wget -i filelist.txt 
```
#### 检查文件并继续
https://unix.stackexchange.com/questions/165875/resume-failed-download-using-linux-command-line-tool
```
wget -nc http://example.com/pic.png
#检查文件列表
wget -nc -i GSE103154.sra.list
```
#### 查看文件夹占用空间大小
https://www.cnblogs.com/justforcon/archive/2017/12/02/7954481.html
```
$ du -sh ./*
```

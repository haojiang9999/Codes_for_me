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
wget -A .gz -np -r http://fantom.gsc.riken.jp/5/suppl/Hon_et_al_2016/data/assembly/lv3_robust/
```
这样就行了，不过是下载在了每一级文件夹里！！

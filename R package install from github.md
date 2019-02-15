###R 包的本地安装 从github上下载packeges.zip解压后

很重要的一点就是如果提示had non-zero exit status
一定把依赖的包安装完才行
```
install.packages("/home/jianghao/BioTools/seurat-release-3.0", repos = NULL, type = "source",dependencies = c("Depends", "Suggests", "Imports"))
```

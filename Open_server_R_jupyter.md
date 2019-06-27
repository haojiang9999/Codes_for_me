#### Open screen for server
screen -S NAME

#### 指定jupyter note开启位置
```
jupyter notebook --no-browser --port 8881 --ip=192.168.1.103
```

#### Rstudio server can not start !!
```
sudo rm -rf /var/lib/rstudio-server
sudo rm -rf /etc/rstudio
```
https://community.rstudio.com/t/cant-start-rstudio-server-ubuntu-18-0-4-bionic/11835/7
#### After update
In my case, it sufficed with killing rserver:

1.Stop RStudio server: $ sudo rstudio-server stop

2.Find the pid that has rserver running: ps -aux | grep rserver

3.Kill all those processes: $ sudo kill -9 [pid]

4.Start RStudio server: $ sudo rstudio-server start

5.sudo rstudio-server online

HIH

https://support.rstudio.com/hc/en-us/community/posts/201681013-Rstudio-V0-98-1028-spawning-port-error
#### start Rstudio in conda env
https://stackoverflow.com/questions/52381661/how-can-i-use-anaconda-environments-with-rstudio-server
```
/usr/lib/rstudio-server/bin/rserver    --server-daemonize=0    --www-port 8788    --rsession-which-r=/home/jianghao/anaconda3/envs/R3.5.1/bin/R    --rsession-ld-library-path=$CONDA_PREFIX/lib
```
#### add R to jupyter notebook 
https://github.com/IRkernel/IRkernel
```
install.packages('IRkernel')
IRkernel::installspec()  # to register the kernel in the current R installation
# in R 3.3
IRkernel::installspec(name = 'ir33', displayname = 'R 3.3')
# in R 3.2
IRkernel::installspec(name = 'ir32', displayname = 'R 3.2')
```

####Open screen for server
screen -S NAME

####指定jupyter note开启位置
```
jupyter notebook --no-browser --port 8881 --ip=192.168.1.103
```

####Rstudio server can not start !!
```
sudo rm -rf /var/lib/rstudio-server
sudo rm -rf /etc/rstudio
```
https://community.rstudio.com/t/cant-start-rstudio-server-ubuntu-18-0-4-bionic/11835/7
In my case, it sufficed with killing rserver:

1.Stop RStudio server: $ sudo rstudio-server stop

2.Find the pid that has rserver running: ps -aux | grep rserver

3.Kill all those processes: $ sudo kill -9 [pid]

4.Start RStudio server: $ sudo rstudio-server start

HIH

https://support.rstudio.com/hc/en-us/community/posts/201681013-Rstudio-V0-98-1028-spawning-port-error

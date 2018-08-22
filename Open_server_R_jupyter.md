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

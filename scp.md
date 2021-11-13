# SCP
## 向 Linux 云服务器上传文件
```shell 
scp 本地文件地址 云服务器帐号@云服务器实例公网 IP/域名:云服务器文件地址
```
例如
```shell 
 scp "C:/Users/simon/Downloads/Miniconda3-latest-Linux-x86_64.sh" woodsheep@82.157.55.59:~/download/Miniconda3-latest-Linux-x86_64.sh
```

## 将 Linux 云服务器上的文件下载至本地
```shell 
scp 云服务器帐号@云服务器实例公网 IP/域名:云服务器文件地址 本地文件地址
```
例如，您需要将 IP 地址为 `129.20.0.2` 的云服务器文件 `/home/lnmp0.4.tar.gz` 下载至本地对应目录下，则执行的命令如下
```shell
scp root@129.20.0.2:/home/Inmp0.4.tar.gz /home/Inmp0.4.tar.gz
```
# SCP
## 向 Linux 云服务器上传文件
```shell 
scp 本地文件地址 云服务器帐号@云服务器实例公网 IP/域名:云服务器文件地址
```
例如
```shell 
 scp "C:/Users/simon/Downloads/Miniconda3-latest-Linux-x86_64.sh" woodsheep@82.157.55.59:~/download/Miniconda3-latest-Linux-x86_64.sh
```
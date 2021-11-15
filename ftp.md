# FTP
## CVM 端
### 安装 vsftpd
1. 执行以下命令，安装 vsftpd
```shell
yum install -y vsftpd
```

2. 执行以下命令，设置 vsftpd 开机自启动
```shell
systemctl enable vsftpd
```

3. 执行以下命令，启动 FTP 服务
```shell
systemctl start vsftpd
```

4. 执行以下命令，确认服务是否启动
```shell
netstat -antup | grep ftp
```

### 配置 vsftpd
1. 执行以下命令，为 FTP 服务创建一个 Linux 用户，本文以 `ftpuser` 为例
```shell
useradd ftpuser
```

2. 执行以下命令，设置 `ftpuser` 用户的密码
```shell
passwd ftpuser
```

3. 输入密码后请按 `Enter` 确认设置，密码默认不显示，本文以 `tf7295TFY` 为例


4. 执行以下命令，创建 FTP 服务使用的文件目录，本文以 `/var/ftp/test` 为例
```shell
mkdir /var/ftp/test
```

5. 执行以下命令，修改目录权限
```shell
chown -R ftpuser:ftpuser /var/ftp/test
```

6. 执行以下命令，打开 vsftpd.conf 文件。
```shell
vim /etc/vsftpd/vsftpd.conf
```

7. 主动模式需修改的配置如下，其余配置保持默认设置
```vim
anonymous_enable=NO      #禁止匿名用户登录
local_enable=YES         #支持本地用户登录
chroot_local_user=YES    #全部用户被限制在主目录
chroot_list_enable=YES   #启用例外用户名单
chroot_list_file=/etc/vsftpd/chroot_list  #指定用户列表文件，该列表中的用户不被锁定在主目录
listen=YES               #监听IPv4 sockets
#在行首添加#注释掉以下参数
#listen_ipv6=YES         #关闭监听IPv6 sockets
#添加下列参数
allow_writeable_chroot=YES
local_root=/var/ftp/test #设置本地用户登录后所在的目录
```
按 `Esc` 后输入 `:wq` 保存后退出

8. 执行以下命令，创建并编辑 `chroot_list` 文件
```shell
vim /etc/vsftpd/chroot_list
```

9. 按 `i` 进入编辑模式，输入用户名，一个用户名占据一行，设置完成按 `Esc` 并输入 `:wq` 保存后退出
设置的用户将不会被锁定在主目录，您若没有设置例外用户的需求，可跳过此步骤，输入 `:wq` 退出文件

10. 执行以下命令，重启 FTP 服务
```shell
systemctl restart vsftpd
```

## 本地端
### 连接云服务器
1. 执行以下命令，安装 ftp
```shell
yum -y install ftp
```

2. 执行以下命令，在本地机器上连接云服务器，并根据界面提示，输入 FTP 服务的用户名和密码
```shell
ftp 云服务器的 IP 地址
```

### 上传文件
执行以下命令，将本地文件上传至云服务器中
```shell
put local-file [remote-file]
```
例如，将本地文件 `/home/1.txt` 上传到云服务器
```shell
put /home/1.txt 1.txt
```

### 下载文件
执行以下命令，将云服务器中的文件下载至本地
```shell
get [remote-file] [local-file]
```

例如，将云服务器中的 A.txt 文件下载到本地的 `/home` 目录下
```shell
get A.txt /home/A.txt
```

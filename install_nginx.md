# install nginx on centos
## Nginx安装
1. 添加Nginx到yum源
``` bash
sudo yum install -y epel-release
```

2. 安装nginx
``` bash
yum install -y nginx
```

3. 启动nginx
``` bash
systemctl start nginx.service
```

4. 设置开机启动
``` bash
systemctl enable nginx.service
```

5. 停止开机自启动
``` bash
systemctl disable nginx.service
```

6. 查看服务当前状态
``` bash
systemctl status nginx.service
```

7. 重启Nginx服务
``` bash
systemctl restart nginx.service
```

8. 查看所有已启动的服务
``` bash
systemctl list-units --type=service
```

# Linux - create new user and set access

1. 登录root
2. 新建用户并创建 home directory
> sudo useradd -d /home/woodsheep -m woodsheep

3. 更改 shell 为 bash
> sudo usermod -s /bin/bash woodsheep

4. 设置密码
> sudo passwd woodsheep

5. 设置sudo权限
> sudo chmod u+w /etc/sudoers
> sudo vi /etc/sudoers

在root底下添加下面一行
vi命令: i(nsert), esc, :wq
> woodsheep ALL=(ALL:ALL) ALL

> sudo chmod u-w /etc/sudoers

6. 设置文件所有者
> [root@VM-24-4-centos home]# chown woodsheep woodsheep

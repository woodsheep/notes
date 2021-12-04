# uwsgi setup
## uwsgi.ini
``` shell
[uwsgi]

# 项目目录
chdir = /home/woodsheep/shibian

wsgi-file = /home/woodsheep/shibian/main.py

# 指定sock的文件路径（nginx使用）
socket = 127.0.0.1:4444

# 进程个数（processess一样效果）
workers = 2

# 指定启动时的pid文件路径
pidfile = /home/woodsheep/shibian/etc/uwsgi.pid

# 指定ip及端口（配置nginx就不需要单独启动uwsgi需要填写）
#http=172.16.0.4:8001

# 指定静态文件（配置nginx不需要，单独启动uwsgi加载静态文件）
#static-map=/static=/var/www/orange_web/static

# 启用主进程
master = true

# 启用线程
enable-threads = true

threads = 2

# 自动移除unix Socket和pid文件当服务停止的时候
vacuum = true

# 设置日志目录
daemonize = /home/woodsheep/shibian/logs/uwsgi.log

#不记录信息日志，只记录错误以及uwsgi内部消息
disable-logging = false

# 序列化接受的内容，如果可能的话
thunder-lock = true
```

## commends
### run with config 
``` bash
uwsgi --ini ~/shibian/etc/uwsgiconfig.ini
```

### stop uwsgi
``` bash
uwsgi --stop ~/shibian/etc/uwsgi.pid
```
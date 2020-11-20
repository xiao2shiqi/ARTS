很多程序员都会在本地通过 docker 虚拟化开发环境，如果机器重启，每次都需要重新启动容器会很麻烦，我们需要把容器设置为自启动就可以解决这个问题

关于自启动常用的命令有以下 3 条：

1. 运行容器时保证容器的自重启：docker run --restart=always
2. 设置已有容器自启动：docker update --restart=always <CONTAINER ID>
3. 取消容器的自启动：docker update –restart=no <CONTAINER ID>
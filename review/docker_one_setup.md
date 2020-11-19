## Review

##### Docker：Orientaion and setup
###### Docker Concepts
Dokcer is platform for developers and sysadmins to develop ,and run application with containers<br>
The usr of Linux containers to deploy applications is called containerization.<br>
Containers are not new, but their use for easily deploying applications is.<br>
<br>

###### Containerization is increasingly popualr because containers are
1. Flexible：Even the most complex application can be containerized
2. Lightweight：Containers leverage and share the host kernel
3. Interchangeable：You can deploy updates and upgrades on-the-fly
4. Portable：You can build locally, deploy to the cloud, and run anywhere
5. Scalable：You can increase and automatically distribute container replicas
6. Stackable：You can stack services vertically and on-the-fly

###### Images and container
1. A container is launched by running an image.
2. An image is an executable package that includes everything needed to run an application the code, a runtime, libraries, environment variables, and configuration files
3. A container is a runtime instance of an image--what the image becomes in memory when executed，that is, an image with state, or a user process
4. You can see a list of your running containers with the command, "docker ps", just as you would in Linux

###### Containers and virtual machines
1. A container runs natively on Linux and shares the kernel of the host machine with other containers
2. It runs a discrete process, takeing no more memory than any other executable, making it lightweight
3. By contrast, a virtual machine(VM) runs a full-blown "guest" operating system with vitual access to host resources through a hypervisor
4. In general, VMs provide an environment with more resources than most applications need

###### Conclusion
- containerization makes CI/CD seamless. For example
- applications have no system dependencies
- updates can be pushed to any part of a distributed application
- resource density can be optimized
- with docker, scaling your application is a matter of spinning up new executables, not running heavy VM hosts.

中文个人理解翻译版（请轻喷）
##### Docker容器：定位和设置
###### 概念
Docker 是一个为开发者和系统管理员开发，部署和运行应用程序使用的容器平台，
使用Linux容器部署应用程序成为“容器化”，容器不是新技术，他们的优势是让部署应用程序变的非常容易

###### 容器化越来越受欢迎，是因为
1. 灵活：即使是非常复杂的应用程序都可以做成容器化
2. 轻量级：容器利用并共享主机内核
3. 可交替：你可以即时部署更新和升级运行中的应用
4. 可便携：你可以在本地构建，部署到云，和任何地方
5. 可扩展：你可以增加并且自动发布容器的副本
6. 可叠加：你可以垂直的堆叠正在运行中的应用服务

###### 镜像和容器
1. 容器是通过启动镜像来运行的
2. 镜像是一个可执行包，包含运行应用程序需要的所有内容：代码，运行时，库，环境变量和配置文件
3. 容器是一个镜像运行时的实例，容器是镜像执行时在内存中如何执行，系统的状态和用户进程的展现
4. 你可以使用命令 docker ps 看到正在运行的容器列表，就像使用Linux命令
 
###### 容器和虚拟机
1. 容器运行在本地的Linux上，并且和其他容器共享主机内核
2. 它运行在一个独立的进程中，不占用其他执行文件的资源和内存，使它更加轻量级
3. 相比之下，虚拟机运行完整的客户操作系统，虚拟机通过管理程序使用主机资源
4. 通常情况，VM提供的环境使用相比大多数应用要使用更多的资源
 
###### 总结
- 为你的应用制作容器化可以和CI/CD无缝集成
- 应用程序没有系统依赖性
- 可以将部分更新推送分布式系统应用
- 资源密度可以优化
- 使用Docker，扩展你应用的是一个可执行文件，不是繁重的虚拟主机
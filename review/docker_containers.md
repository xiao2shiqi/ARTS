## Review

最近唯一读的英文就是Docker的官方文档，就勉强拿自己翻译的官方文档来交作业吧
##### Containers
###### Prerequisites
* Install Docker version 1.13 or higher
* Read the orientation in Part 1
* Give your environment a quick test run to make sure you're all set up

###### Introduction（介绍）
It's time to begin building an app the Docker way We start at the buttom of the hierarchy of such app, a container, which this page covers Above this level is a service, which defines how containers behave in production, covered in Part 3 Finally, at the top level is the stack，defining the interactions of all the services, covered in Part 5

###### You new  development environment
In the past, if you were to start writing a Python app, your first order of business was to install a Python runtime onto your machine. But, that creates a situation where the environment on your machine needs to be perfect for your app to run as expected, and also needs to match your production environment With Docker, you can just grab a portable Python runtime as an image, no installation necessary Then, your build can include the base Python image right alongside your app, its dependencies, and the runtime, all travel together
 These portable images are defined by something called a Dockerfile.

###### Define a container with Dockerfile
Dockerfile defines what goes on in the environment inside your container Access to resources like networking interfaces and disk drives is virtualized inside this environment, which is isolated from the rest of your system So you nedd to map ports to the outside world, and be specific about what files you want to "copy in" to that environment.However, after doing that, you can expect that the build of your app defined in this Dockerfile behaves exactly the same wherever it runs.

###### Conclusion
* In the next section, we learn how to scale our application by running this container in a service.

##### 容器
###### 先决条件

* 安装Docker版本1.13或者更高
* 阅读第1部分：定位
* 给你的环境设置快速测试运行，确保你完成所有设置

###### 介绍
现在是时候开始使用Docker的方式构建应用程序了,我们从应用程序层次的底部开始，这个页面包含一个容器，高于容器级别的是一项服务，它定义了容器在生产中的行为方式，参考第3部分，最后，最高等级是Stack，定义所有服务的交互，参考第5部分

###### 新的开发环境
在过去，如果你开始编写Python应用，你的第一件事就是在你机器上安装Pythod运行时，但是，这会导致你的应用非常依赖你机器的环境运行，而且还需要匹配你的生产环境，使用Docker，你只需要拉取一个Python运行时镜像，无需安装，然后，你可以在构建的应用代码旁边包含基本Python镜像，确保你的应用，其依赖项和运行时，一起运行，这些可移植的镜像由一个叫Dockerfile的东西定义

###### 使用Dockerfile定义容器
Dockerfile定义在容器环境内发生的事情，对网络接口和磁盘驱动器等资源的访问是在虚拟化环境中进行的，这和你的系统是隔离开的，所以你需要讲容器内的映射端口到系统的外部，并且具体说明你要“复制”到该环境的文件，但是，这样做以后，你可以预期在Dockerfile定义的应用可以在任何环境运行

###### 总结
下一节中，我们学习如何通过在服务中运行容器来扩展我们的应用
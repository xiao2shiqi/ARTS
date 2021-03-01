##### 为什么要用 snippets（代码段）？

不管你使用何种编程语言，在我们日常的编码工作中，都会存在有大量的重复代码编写，例如：

* 日志打印： `console.log，log.info('...')`
* 输出到控制台：`System.out.println("....")， fmt.Println("...")`
* 循环：`switch(...){}，for(i := 0, i <= len, i++)，for...i ` 等等



这种模板代码在 java，go 中静态语言会比较多，实际上，平时除了 **模板代码**，还有很多**模板文件**，也是存在很多重复编码的工作，例如：vue文件，html文件，xml文件，里面的很多标签，方法，属性基本都是固定的，我平时遇到比较多的还是 java，go 里面的模板文件和代码，关于重复代码不胜枚举，这里就不过多概述了。



写这些模板代码和模板文件，实际上除了练习你的打字速度外，**不会给你带来任何技能上的提升**，是属于 **重复而且低价值的事情**，比如就算你把 "hello world" 练习一千遍，你也不会成为高手一样，

那么作为一个高效的程序员，要懂利用如何节省自己的时间，**把有限的精力投资在高价值，高回报的事情上**，对于这些无法逃避的重复的编码工作，我们需要用技术和工具来把他们解决就好，所以 VSCode 提供的 user snippets 用户代码段（在 jetbrains 家族中也称为 Live templates ）就是用来做这个事情的



##### 怎么使用 snippets ？

知道了为什么要用代码段，我们来说说 VSCode 中的 snippets 的具体作用

熟悉 Jetbrains 家族产品的同学应该知道 [Live Templates](https://www.jetbrains.com/help/idea/using-live-templates.html) 功能非常好用，其实 VSCode snippets 就是类型 Jetbrains 的 Live Templates 功能，他们解决的是相同的问题。

VSCode 官方对于 snippets 的描述如下：

> Code snippets are templates that make it easier to enter repeating code patterns, such as loops or conditional-statements.

简单翻译就是：

**代码段是一种模板，可以更容易地输入重复的代码模式，例如循环或条件语句**



使用 `snippeets` 代码段对 javascript 中的 ajax 的重复代码进行封装，只需要输入关键字：ajax，就可以把整个代码段带出来，非常的高效，具体参见下面来自官方的示例：

![ajax snippet](https://code.visualstudio.com/assets/docs/editor/userdefinedsnippets/ajax-snippet.gif)



##### 查看已有的 snippets 

其实 VSCode 对于每种语言都有默认初始化的 snippets，能够满足日常的使用，在 VSCode 打开命令行界面输入：**insert snippets**  即可查看当前可以用的 snippets，如图：

<img src="https://pcloud-1258173945.cos.ap-guangzhou.myqcloud.com/uPic/l5aEXH.png" alt="JavaScript 内置的 snippets" style="zoom:50%;" />

以上是在  JavaScript 语言环境下看到的 snippets （目前内置对 JavaScript 支持比较友好）

当我切换到 golang 的时候，查看的 snippets 如下（未安装语言包的情况下）：

<img src="https://pcloud-1258173945.cos.ap-guangzhou.myqcloud.com/uPic/GHBBY1.png" alt="VSCode 初始化内置的 snipptes" style="zoom:50%;" />

这么少的 snippets 肯定是不够用的，好在 VSCode 的丰富插件为我们提供了扩展的可能性，通常相关联的语言工具包都内置的大量常用的 snippets，我们通常只要安装即可。



在 VSCode 的扩展使用：`@category:snippets` 过滤搜索安装对应的工具即可，如图：

<img src="https://pcloud-1258173945.cos.ap-guangzhou.myqcloud.com/uPic/18gJTC.png" alt="18gJTC" style="zoom:50%;" />



安装语言包完成后，在 VSCode Command 页面输入：**insert snippets** 即可看到新增的大量的 snippets ：

<img src="https://pcloud-1258173945.cos.ap-guangzhou.myqcloud.com/uPic/J6Hz0r.png" alt="J6Hz0r" style="zoom:50%;" />

熟练使用语言包内置的 snippets 可以满足 80%  场景。

但是可能还是无法满足和覆盖所有场景，

这样场景下我们需要创建自己的 snippets 来完全解决代码重复的问题。



##### 创建你自己的 snippets

在 VSCode 中创建 snippets 是非常简单的事情（无需安装任何扩展），有两种方法实现：

1. 在 macOS 中选择：Code -> Preferencts -> User Snippets 选项
2. 或者在 VSCode Command 中输入：configure user snippets 即可



如果是创建 snipperts 选择 选择 **New Global Snippets file** ，输入你要创面的 snipperts name 即可进入配置

snipperts 文件是 JSON 风格，刚创建后的默认格式内容如下：

<img src="https://pcloud-1258173945.cos.ap-guangzhou.myqcloud.com/uPic/SpCk5J.png" alt="SpCk5J" style="zoom:50%;" />

我简单描述的一下属性的作用：

* scope：限定代码段的作用域，例如 go 语言的代码段不会出现在 js 中，反之亦然
* prefix：是快捷关键字，当 VSCode 检测到代码中出现 prefix 关键字就会在编辑器中替换为 body 的内容
* body：是重复的代码模板内容，通常是程序员想要自动化的一些重复，模板代码，录入在这里
* description：顾名思义就是对这段 snippets 的具体描述

这里值得再提一下的就是， body 里面的 `$1` 关键字是模板代码替换后鼠标光标的所在位置，当出现多个 `$1`，`$2` 的时候，可以通过键盘 `TAB` 按键快速切换鼠标光标所在位置，用于提高效率，这块就不具体深入描述了，有兴趣的小伙伴可以自行去探索。



关于 snipperts 配置文件的细节还有很多，这里就不深究了，

有兴趣深入研究的伙伴可以 VSCode Snippets 官方的相关的文档，里面解释的非常详细。



参考资料：

* [Snippets in Visual Studio Code
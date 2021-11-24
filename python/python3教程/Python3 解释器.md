# Python3 解释器

Linux/Unix的系统上，一般默认的 python 版本为 2.x，我们可以将 python3.x 安装在 **/usr/local/python3** 目录中。

安装完成后，我们可以将路径 **/usr/local/python3/bin** 添加到您的 Linux/Unix 操作系统的环境变量中，这样您就可以通过 shell 终端输入下面的命令来启动 Python3 。

$ PATH=$PATH:/usr/local/python3/bin/python3 # 设置环境变量 $ python3 --version Python 3.4.0

在Window系统下你可以通过以下命令来设置Python的环境变量，假设你的Python安装在 C:\Python34 下:

set path=%path%;C:\python34

---

## 交互式编程

我们可以在命令提示符中输入"Python"命令来启动Python解释器：

$ python3

执行以上命令后，出现如下窗口信息：

$ python3 Python 3.4.0 (default, Apr 11 2014, 13:05:11) [GCC 4.8.2] on linux Type "help", "copyright", "credits" or "license" for more information. >>> 

在 python 提示符中输入以下语句，然后按回车键查看运行效果：

print ("Hello, Python!");

以上命令执行结果如下：

Hello, Python!

当键入一个多行结构时，续行是必须的。我们可以看下如下 if 语句：

>>> flag = True >>> if flag : ... print("flag 条件为 True!") ... flag 条件为 True!

---

## 脚本式编程

将如下代码拷贝至 **hello.py**文件中：

print ("Hello, Python!");

通过以下命令执行该脚本：

python3 hello.py

输出结果为：

Hello, Python!

在Linux/Unix系统中，你可以在脚本顶部添加以下命令让Python脚本可以像SHELL脚本一样可直接执行：

#! /usr/bin/env python3

然后修改脚本权限，使其有执行权限，命令如下：

$ chmod +x hello.py

执行以下命令：

./hello.py

输出结果为：

Hello, Python!

[](https://www.runoob.com/python3/python3-data-type.html) [Python3 基本数据类型](https://www.runoob.com/python3/python3-data-type.html " Python3 基本数据类型")

[Python3 注释](https://www.runoob.com/python3/python3-comment.html "Python3 注释") [](https://www.runoob.com/python3/python3-comment.html)

## 

2 篇笔记 写笔记

1.     chendu
    
      987***757@qq.com
    
    366
    
    Python 解释器可不止一种哦，有 CPython、IPython、Jython、PyPy 等。
    
    顾名思义，CPython 就是用 C 语言开发的了，是官方标准实现，拥有良好的生态，所以应用也就最为广泛了。
    
    而 IPython 是在 CPython 的基础之上在交互式方面得到增强的解释器（[http://ipython.org/](http://ipython.org/)）。
    
    Jython 是专为 Java 平台设计的 Python 解释器（[http://www.jython.org/](http://www.jython.org/)），它把 Python 代码编译成 Java 字节码执行。
    
    PyPy 是 Python 语言（2.7.13和3.5.3）的一种快速、兼容的替代实现（[http://pypy.org/](http://pypy.org/)），以速度快著称。
    
    [chendu](javascript:;)
    
       chendu
    
      987***757@qq.com
    
    3年前 (2018-05-15)
    
2.     爱奇奇
    
      767***953@qq.com
    
      [参考地址](https://www.jianshu.com/p/47d245dd672d)
    
    447
    
    **$ python test.py 运行失败**
    
    在 cmd 窗口输入 $ python test.py，得到运行错误的提示：
    
    ![](https://static.runoob.com/images/mix/8683310-bb7e51c85c2ad748.webp)
    
    -   Python 的实际工作场景往往是 Unix 或者 Linux。而代码开头的 `$` 表示 UNIX 或 Mac OS 操作系统命令提示符。`$`的意思就是 “提示用户输入命令行”，`$` 本身不在输入的命令语句中。`$` 是不需要输入的。
    -   Python 的编程模式分为两种：**交互式**，**脚本式**。
    -   交互式编程，需要我们打开 cmd 窗口（命令提示符窗口），在窗口中键入`python`,回车，这样就进入了交互式编程。此时我们直接输入 python 语句，就可以得到运行的结果： ![](https://static.runoob.com/images/mix/8683310-9291d88f53fd5b44.webp)
    -   脚本式编程，就是我们先把 python 语句写好，保存在后缀为 .py 的文件里，然后从外部调用这个文件。它也可以使用 cmd 窗口进行调用，**与交互式编程不同的是，不要在cmd窗口内输入python加回车来进入交互模式**
    -   如果我们要在cmd窗口调用test.py文件，只需要将**cmd路径目录转入test.py所在的文件夹，然后输入命令即可**
    -   假设我们的test.py文件放在D盘，路径为：D:\Python27\Mytest\test.py 那么要在cmd窗口调用这个文件，我们需要将目录路径切换到D:\Python27\Mytest。使用**cd命令**即可做到。  
        ![](https://static.runoob.com/images/mix/8683310-d74ba3bfcab55d17.webp)
    
    以下是简单的补充：  
    cmd 窗口打开方式：右键开始菜单，选择‘命令提示符（管理员）’即可。或者从开始菜单->运行->输入cmd，回车。  
    关于 cd 命令：用于改变当前目录路径。使用方式：cd[空格][路径]  
    例如 cd d:/Python27/Mytest 转到该路径下  
    注意：如果当前盘符不是 D 盘，需要先转到 D 盘，输入 d: 回车即可。然后才可以使用 cd d:/Python27/Mytest
    
    ![](https://static.runoob.com/images/mix/8683310-d9297c7283d814e2.webp)
    
    [爱奇奇](javascript:;)
    
       爱奇奇
    
      767***953@qq.com
    
      [参考地址](https://www.jianshu.com/p/47d245dd672d)
    
    3年前 (2018-11-25)
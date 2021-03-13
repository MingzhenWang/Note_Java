## 第2章 Java程序设计环境

#### 目录
##### [2.1 安装Java开发工具包](#anchor21)
##### [2.2 使用命令行工具](#anchor22)
##### [2.3 使用集成开发环境](#anchor23)

### <span id="anchor21">2.1 安装Java开发工具包</span>
（1）安装JDK
需要到Oracle官网下载需要的JDK安装包
具体术语如下所示
![](/Java/001-Java核心技术%20卷一/Pictures/2001.png)

可以同时在一个电脑上安装多个版本的JDK，具体教程如下所示：
https://app.yinxiang.com/fx/b666f764-67c1-4845-8913-fc248b8c04c3

（2）安装库源文件和文档

**库源文件**在JDK中以一个压缩文件src.zip的形式发布，必须解压后才能访问源代码，操作如下：
（1）确保JDK已安装，且jdk/bin目录在执行路径中
（2）在主目录（jdk目录下）新建javasrc文件夹
（3）将主目录文件夹下的src.zip文件解压缩到javasrc目录
```cmd
jar xvf jdk/javasrc
```

文档是一个独立于JDK的压缩文件，需要到官网下载然后解压缩。

### <span id="anchor22">2.2 使用命令行工具</span>
**javac程序**是一个Java编译器，将Welcome.java文件编译成welcome.class
```cmd
javac Welcome.java
```
**java程序**启动Java虚拟机,虚拟机执行编译器放在class文件中的字节码
```cmd
java Welcome.class
```

### <span id="anchor23">2.3 使用集成开发环境</span>
常见的有Eclipse和Intellij IDEA，推荐使用Intellij IDEA
<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [第2章 Java程序设计环境](#%E7%AC%AC2%E7%AB%A0-java%E7%A8%8B%E5%BA%8F%E8%AE%BE%E8%AE%A1%E7%8E%AF%E5%A2%83)
  - [2.1 安装Java开发工具包](#21-%E5%AE%89%E8%A3%85java%E5%BC%80%E5%8F%91%E5%B7%A5%E5%85%B7%E5%8C%85)
  - [2.2 使用命令行工具](#22-%E4%BD%BF%E7%94%A8%E5%91%BD%E4%BB%A4%E8%A1%8C%E5%B7%A5%E5%85%B7)
  - [2.3 使用集成开发环境](#23-%E4%BD%BF%E7%94%A8%E9%9B%86%E6%88%90%E5%BC%80%E5%8F%91%E7%8E%AF%E5%A2%83)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## 第2章 Java程序设计环境

### 2.1 安装Java开发工具包
（1）安装JDK
需要到Oracle官网下载需要的JDK安装包
具体术语如下所示
![](/001-Java核心技术_卷一/Pictures/2001.png)

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

### 2.2 使用命令行工具
**javac程序**是一个Java编译器，将Welcome.java文件编译成welcome.class
```cmd
javac Welcome.java
```
**java程序**启动Java虚拟机,虚拟机执行编译器放在class文件中的字节码
```cmd
java Welcome.class
```

### 2.3 使用集成开发环境
常见的有Eclipse和Intellij IDEA，推荐使用Intellij IDEA
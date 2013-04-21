---
layout: post
title: 搭建Nexus仓库
---
###Nexus是什么？
Nexus是Maven仓库管理器，用来搭建一个本地仓库服务器，这样做便于管理，节省网络资源，速度快！

###Nexus安装
进入http://nexus.sonatype.org/downloads/ 后，有两个选择一个收费的高级版，这里我们选择基本版就行了(DOWNLOAD NEXUS OSS),下载Nexus 2.3.1 WAR 来安装，这样需要Tomcat支持的，或者选择boundle版本，内置jetty服务器，可独立运行。下载后的大小是25.57Mb。将其上传到Tomcat的webapps目录下，会自动解压。

由于我的mbl内存太小 安装失败！ 寻找其他解决方法。
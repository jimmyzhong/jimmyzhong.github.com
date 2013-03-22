---
layout: post
title: MBL安装wordpress
---

##MBL安装wordpress

#首先打开ssh管理窗口。

安装mysql，apt-get install mysql,mysql-server.会提示安装一堆东西，全部安装上，期间会提示输入mysql的root密码。

mysql –u root  -p  登入，会提示输入root的密码。

安装成功。

#下载wordpres，我下载的是wordpress-3.5.1，解压备用。也可以直接使用apt-get install wordpress，不过可能是老版本。将wordpress上传到/var/www/下。

创建wordpress使用的数据库，

mysql –u root  -p  登入mysql，

mysql > create database wordpress;

mysql > grant all on wordpress.* to wordpress@localhost;

mysql > use mysql;

mysql > update user set password=PASSWORD(“test”) where user=”wordpress”;

mysql > flush privileges;

mysql > quit;退出。

输入IP访问http://10.0.0.5/wordpress/wp-admin/install.php，提示这个错误Your PHP installation appears to be missing the MySQL extension which is required by WordPress.

apt-get install php5-mysql,遇到包冲突使用下面命令强制安装，记得先备份。

dpkg  -i –force-overwrite /var/cache/apt/archives/php5-common_5.3.3-7+squeeze14_powerpc.deb

重启apache，/etc/init.d/apache restart

重新访问http://10.0.0.5/wordpress/wp-admin/install.php，成功看到wordpress的安装页面了。

 

点击创建配置文件试试吧

数据名称：wordpress

用户名：wordpress

密码：test

主机：localhost

表前缀：wp_

继续submit

下面还需要填写一些信息，就开始安装了。

登陆后出现管理页面啦。

接下来添加一篇文章。

点击左上角的New，输入标题，内容。Publish。
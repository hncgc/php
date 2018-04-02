# php
php资源

[Laravel](https://github.com/hncgc/php/blob/master/Laravel.md)  

[Ubuntu](https://github.com/hncgc/php/blob/master/Ubuntu.md)  

[PhpStorm](https://github.com/hncgc/php/blob/master/PhpStorm.md)  

[PHP 标准规范中文版](https://psr.phphub.org/)  

[PHP必读](https://laravel-china.github.io/php-the-right-way/)  

[使用命名空间：别名/导入](http://php.net/manual/zh/language.namespaces.importing.php)  

[命名空间概述](http://php.net/manual/zh/language.namespaces.rationale.php)  


-----------------------

Laragon
---

> 现在如果你是win系统，想学laravel，我觉得你裸机只需要装两样东西，laragon+phpstorm，三分钟内开始一个laravel项目~

[Laragon ：推荐的 Windows Laravel 集成环境](https://zhuanlan.zhihu.com/p/27924430)  

[Laravel-Laragon学院](http://laravelacademy.org/tags/laragon)  

[[ Laravel 5.5 文档 ] 快速入门 —— 使用 Laragon 在 Windows 中搭建 Laravel 开发环境](http://laravelacademy.org/post/7754.html)  
```
Laragon 具备以下优秀的特性：
- 自动创建虚拟主机（Virtual Host，Valet 也有这样的功能）
- 邮件接收和发送
- 非常方便地切换 PHP、Apache、MySQL 的不同版本
- 轻松创建框架应用，如 Laravel、Symfony、WordPress、Joomla 等
- 基于自己的需求为不同的环境设置不同的配置
```
下载 Laragon：https://sourceforge.net/projects/laragon/  
> Powerful tool for modern apps: Django, Rails, Laravel, Node, Go, Java  
laragon-wamp.exe
https://jaist.dl.sourceforge.net/project/laragon/releases/3.1/laragon-wamp.exe
共 115 MB


[Laragon的中文官网下载](http://www.laragon.com.cn/laragon-china/)  

[Laragon，简单便携迅速的WAMP工具，Laravel一站式创建和运行](http://www.prefershare.com/laragon-wamp-laravel)  

[laragon环境更新安装新的php版本操作方法](https://blog.csdn.net/hj960511/article/details/51693225)  

[laravel简单的laragon环境搭建不需要composer一键集成](https://blog.csdn.net/hj960511/article/details/51441990)  


[Laragon 让你在 Windows 下愉快的编码](https://laravel-china.org/articles/3994/laragon-allows-you-to-happy-coding-under-windows)  

[laravel开发神器laragon的使用方法](http://www.wangjingxian.cn/laravel/52.html)  

laragon官方网站: https://laragon.org/

laragon的中文官网: http://www.laragon.com.cn/

laragon社区: http://forum.laragon.org/

[Laravel](http://www.wangjingxian.cn/category/16)  

[敬贤博客](http://www.wangjingxian.cn/)  

-------------

php包管理工具Composer
---
Composer  
https://getcomposer.org  
https://packagist.org  

[中国全量镜像](https://pkg.phpcomposer.com/)  

[Composer速查表](https://nai8.me/composer/index.html)  


[Composer 中文网 / Packagist 中国全量镜像](https://www.phpcomposer.com/)  

[Composer 中文文档](http://docs.phpcomposer.com/00-intro.html)  
https://github.com/5-say/composer-doc-cn  

[Composer  中文文档 - 简介](http://docs.phpcomposer.com/00-intro.html)  

```
下载 Composer 的可执行文件
php -r "readfile('https://getcomposer.org/installer');" | php

C:\laragon\www
λ php -r "readfile('https://getcomposer.org/installer');" | php
All settings correct for using Composer
Downloading...

Composer (version 1.6.3) successfully installed to: C:\laragon\www\composer.phar
Use it: php composer.phar


C:\laragon\www
λ


C:\laragon\www\composer.phar      1819KB

安装Laragon时已安装
C:\laragon\bin\composer\composer.phar 1,794KB

C:\laragon\www  
λ composer -v   
   ______                                           
  / ____/___  ____ ___  ____  ____  ________  _____ 
 / /   / __ \/ __ `__ \/ __ \/ __ \/ ___/ _ \/ ___/ 
/ /___/ /_/ / / / / / / /_/ / /_/ (__  )  __/ /     
\____/\____/_/ /_/ /_/ .___/\____/____/\___/_/      
                    /_/                             
Composer version 1.4.1 2017-03-10 09:29:45          

安装 - Windows
使用安装程序
这是将 Composer 安装在你机器上的最简单的方法。
下载并且运行 Composer-Setup.exe，它将安装最新版本的 Composer ，并设置好系统的环境变量，因此你可以在任何目录下直接使用 composer 命令。

C:\laragon\bin\composer\composer.bat
@ECHO OFF
php "%~dp0composer.phar" %*

php composer.phar
```

[Composer  中文文档 - 基本用法](http://docs.phpcomposer.com/01-basic-usage.html)  

[PHP 开发者该知道的 5 个 Composer 小技巧](https://www.phpcomposer.com/5-features-to-know-about-composer-php/)  

[使用composer新建一个laravel项目](https://blog.csdn.net/qiqiaiairen/article/details/51233703)  

--------


Homestead
---------

laravel Homestead window安装过程
https://www.jianshu.com/p/c57cac7ce1e8

Mac - laravel使用 -- Homestead环境搭建【VPN】
https://www.jianshu.com/p/b7ad926b326a

------------------

----------------------

VMware Workstation
---

```
VMware Workstation，是一款功能强大的桌面虚拟计算机软件，提供用户可在单一的桌面上同时运行不同的操作系统，和进行开发、测试 、部署新的应用程序的最佳解决方案。
VMware Workstation 可在一部实体机器上模拟完整的网络环境，以及可便于携带的虚拟机器，其更好的灵活性与先进的技术胜过了市面上其他的虚拟计算机软件。对于企业的 IT开发人员和系统管理员而言，VMware 在虚拟网路，实时快照，拖曳共享文件夹，支持 PXE 等方面的特点使它成为必不可少的工具
开发商：VMware,Inc.
软件官网： http://www.vmware.com/cn
```

[VMware Workstation 12.5.9 Pro虚拟机软件中文版](http://www.epinv.com/post/6304.html)  

[VMware Workstation最新官方版下载_百度软件中心](http://rj.baidu.com/soft/detail/13808.html?ald)  

[VMware Pro v14.1.1 官方版本及激活密钥](http://www.zdfans.com/5928.html)  
```
激活密钥

VMware 2017 v14.x 永久许可证激活密钥
FF31K-AHZD1-H8ETZ-8WWEZ-WUUVA
CV7T2-6WY5Q-48EWP-ZXY7X-QGUWD
```

VirtualBox
---

[VirtualBox](https://baike.baidu.com/item/VirtualBox/5842786?fr=aladdin)  

[VirtualBox安装部署Ubuntu 16.04 图文详解](https://www.linuxidc.com/Linux/2016-08/134580.htm)  

[基于VirtualBox虚拟机安装Ubuntu图文教程](https://blog.csdn.net/u012732259/article/details/70172704)  

[使用Virtualbox在Windows下安装Ubuntu系统](https://blog.csdn.net/CCSUXWZ/article/details/55805456)  

[linux学习第一篇：在VirtualBox下安装linux操作系统](https://blog.csdn.net/yuchao2015/article/details/52132270)  




--------

Redis
---

[Redis 教程 | 菜鸟教程](http://www.runoob.com/redis/redis-tutorial.html)  

[Redis中文网](http://www.redis.cn/)  

[PHP-redis中文文档](http://bbs.redis.cn/forum.php?mod=viewthread&tid=481)  

--------

yii2
---

[Yii2速查表（中文版）](https://nai8.me/tool-sc.html)  

[Yii 2.0 权威指南](http://www.yiichina.com/doc/guide/2.0)  

[Yii中文网](http://www.yiichina.com/)  











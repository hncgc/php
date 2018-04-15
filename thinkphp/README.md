# Thinkphp

[2017年最新的10个thinkphp视频教程推荐](http://www.php.cn/toutiao-362455.html)  

## 最新ThinkPHP 5.1

[最新ThinkPHP 5.1全球首发视频教程(60天成就PHP大牛线上培训班课)](http://www.php.cn/course/812.html)  

[第1章 ThinkPHP安装与运行流程](http://www.php.cn/code/24861.html)  


Composer安装ThinkPHP  

Composer全局安装：使composer命名在任何目录下都可以使用  
    Composer中文网：http://www.phpcomposer.com
    在Composer中文网选择“入门指南” -> 全局安装（on OSX）
    安装 - Windows  
        使用安装程序
        手动安装
安装中国全量镜像：大幅提升国内访问速度  
    在Composer中文网选择“中国镜像”
    打开https://pkg.phpcomposer.com/
    Packagist 镜像使用方法
    打开命令行窗口（windows用户）或控制台（Linux、Mac 用户）并执行如下命令：
    方法一： 修改 composer 的全局配置文件（推荐方式）
    composer config -g repo.packagist composer https://packagist.phpcomposer.com
    方法二： 修改当前项目的 composer.json 配置文件：
    打开命令行窗口（windows用户）或控制台（Linux、Mac 用户），进入你的项目的根目录（也就是 composer.json 文件所在目录），执行如下命令：
    composer config repo.packagist composer https://packagist.phpcomposer.com
    上述命令将会在当前项目中的 composer.json 文件的末尾自动添加镜像的配置信息（你也可以自己手工添加）：
    "repositories": {
        "packagist": {
            "type": "composer",
            "url": "https://packagist.phpcomposer.com"
        }
    }

搜索ThinkPHP安装包：https://packagist.org  
    在Composer中文网点击“安装包列表”打开https://packagist.org/，搜索“topthink”
    最新为“topthink/think”,单击链接打开后有安装命令：
    composer create-project topthink/think
    在www下建立目录tp5,终端中运行：
    composer create-project topthink/think tp5
创建虚拟主机：必须将访问入口解析到public目录下  
    127.0.0.1 tp5.com
```
C:\laragon\www\laravelapp (master)
λ cd ..
C:\laragon\www
λ mkdir tp5

C:\laragon\www
λ composer create-project topthink/think tp5
Installing topthink/think (v5.1.8)
  - Installing topthink/think (v5.1.8): Downloading (100%)
Created project in tp5
Loading composer repositories with package information
Updating dependencies (including require-dev)
Package operations: 2 installs, 0 updates, 0 removals
  - Installing topthink/think-installer (v1.0.12): Downloading (100%)
  - Installing topthink/framework (v5.1.9): Downloading (100%)
Writing lock file
Generating autoload files

C:\laragon\www
λ
```


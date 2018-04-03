Laravel
---

[Laravel 5.6 版本正式发布](http://www.golaravel.com/post/laravel-5-6-is-now-released/)  

[Laravel学院](http://laravelacademy.org/)  

[Laravel文档](https://docs.golaravel.com/)  

[Laravel5.0文档](https://docs.golaravel.com/docs/5.0/installation/)  

[Laravel 5.6 中文文档](http://laravelacademy.org/docs/laravel-5_6)  
http://laravelacademy.org/laravel-docs-5_6  

[Laravel 完整开源项目大全](http://laravelacademy.org/laravel-project)  

[Laravel Cchina社区](https://laravel-china.org/)

[Laravel Homestead](https://laravel-china.org/docs/laravel/5.1/homestead)  

[Homestead 安装需要知道的一些信息]()  

[Homestead 2.0 安装笔记](https://laravel-china.org/topics/491/homestead-2-installation-notes)  

[Laravel 安装指南](https://docs.golaravel.com/docs/5.0/installation/)  


[Laravel 5.1 LTS 速查表](https://cs.laravel-china.org/)  

[《Laravel 入门教程 - 从零到部署上线》](https://laravel-china.org/topics/3383/laravel-the-first-chinese-new-book-laravel-tutorial)  

[《Laravel 进阶课程 - 从零开始构建论坛系统》](https://laravel-china.org/topics/6592/laravel-tutorial-series-book-second-web-developer-combat-advanced-began-to-build-the-forum-system-from-zero)  

[《Laravel 教程实战高级 - 构架 API 服务器》](https://laravel-china.org/topics/7657/laravel-tutorial-series-third-the-first-edition-of-the-laravel-tutorial-advanced-architecture-api-server)  

--------------------------------------------------------------

[Swoole-PHP高级Web开发框架](http://www.imooc.com/topic/phpframe?mc_marking=61a66083a0886828f2b6d3ccad93756f&mc_channel=bdphpkj)  
```
Laravel-简洁、优雅的PHP 框架
ThinkPHP框架
Yii最有效率PHP框架之一
```

[为什么 Laravel 5 这么好一个框架，国人都不去用？](https://www.zhihu.com/question/30622752)  
https://github.com/summerblue/phphub  
https://github.com/summerblue/phphub5  


[PHP Laravel Vue.js 视频教程](https://www.codecasts.com/)  

[Laravel 5.1 视频基础教程](https://www.codecasts.com/series/laravel-5-basic)  

------

[Laravel 5 系列入门教程（一）](http://www.golaravel.com/post/laravel-5-getting-started-part-1/)  
https://lvwenhan.com/laravel/432.html  
https://github.com/golaravel/laravel-versions


[Laravel 创建项目步骤](https://www.jianshu.com/p/388f0e79b4a5)  
> 通过克隆GitHub仓库到本地来安装：  
> https://github.com/laravel/quickstart-basic  
```
git clone https://github.com/laravel/quickstart-basic quickstart
cd quickstart
composer install
php artisan migrate
```
[使用composer新建一个laravel项目](https://blog.csdn.net/qiqiaiairen/article/details/51233703)  
```
C:\laragon\www
λ composer create-project laravel/laravel laravelapp --prefer-dist

运行
http://localhost/laravelapp/public/index.php
http://localhost:63342/laravelapp/public/index.php?_ijt=jnuq8a7p9afd15rjb1uq7molvi
http://localhost/laravelapp/server.php
```
[用Laravel创建项目](https://blog.csdn.net/xhanfei/article/details/51763617)  
```
用laraval new 创建项目
C:\laragon\www
λ laravel new laravel56
```

[Laravel 框架目录结构](https://www.jianshu.com/p/909a650a240f)  
```
C:\laragon\www\laravelapp\composer.json
```

[Laravel项目目录结构说明](http://www.mamicode.com/info-detail-1669639.html)  
```
laravel中文手册：https://cs.laravel-china.org/  
PHP 标准规范中文版: https://psr.phphub.org/  
http://www.php-fig.org/  
env环境设置类： https://github.com/vlucas/phpdotenv  
```


[php artisan常用方法](https://my.oschina.net/u/1186749/blog/643850)  
```
1、生成控制器
php artisan make:controller PhotoController
2、使用RESTFUL生成控制器
php artisan make:controller PhotoController --resource
Route::resource('photo', 'PhotoController');
3、生成模型
php artisan make:model User -m
```
[laravel artisan工具的使用](https://blog.csdn.net/booljiaoyu/article/details/56011599)  
> artisan工具是一个php文件,它放在laravel框架的根目录  
> C:\laragon\www\laravelapp\artisan  
> C:\laragon\www\laravelapp  
> λ php artisan  
> Laravel Framework 5.6.15  
>   
> Usage:  
>  command [options] [arguments]  

[Laravel5.0 HTTP 路由](https://docs.golaravel.com/docs/5.0/routing/)  

[laravel 5.5 -- router](https://blog.csdn.net/OneGoal/article/details/77825781)  

[[ Laravel 5.2 文档 ] 基础 —— HTTP 路由](http://laravelacademy.org/post/2784.html)  

[[ Laravel 5.6 文档 ] 基础组件 —— 路由](http://laravelacademy.org/post/8731.html)  

------

[从零开始学Laravel](https://segmentfault.com/blog/zhoujiping)  

[1. Laravel的初始化安装 - Laravel从零开始教程](https://segmentfault.com/a/1190000007442208)  
```
先安装起来composer, 使用下面两条命令即可
curl -sS https://getcomposer.org/installer | php     # 下载composer.phar
mv composer.phar /usr/local/bin/composer             # 移动composer.phar 并更名为composer,让composer可以全局使用

使用composer global require "laravel/installer" 来安装Laravel安装器了

安装位置：C:/Users/Administrator/AppData/Roaming/Composer

用laraval new 创建项目
C:\laragon\www
λ laravel new laravel56
```












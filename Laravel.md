Laravel
---

[Laravel 精选资源大全](https://blog.csdn.net/qq_30002351/article/details/78215821)  

[Laravel 5.6 版本正式发布](http://www.golaravel.com/post/laravel-5-6-is-now-released/)  

[Laravel学院](http://laravelacademy.org/)  

[Laravel5.0文档](https://docs.golaravel.com/docs/5.0/installation/)  

[Laravel 5.6 官方文档](https://laravel.com/docs/5.6/)  

[Laravel5.6官方文档](https://docs.golaravel.com/)  

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

Laravel视频教程
---

[PHP Laravel Vue.js 视频教程](https://www.codecasts.com/)  

[Laravel 5.1 视频基础教程](https://www.codecasts.com/series/laravel-5-basic)  

[2017年最新的五个Laravel视频教程推荐](http://www.php.cn/toutiao-362426.html)  

[[慕课网]轻松学会Laravel-基础篇(视频)](http://www.imooc.com/learn/697)  

[[慕课网]轻松学会Laravel-表单篇(视频)](http://www.imooc.com/learn/699)  

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

运行:
C:\laragon\www\laravel56
λ php artisan serve
Laravel development server started: <http://127.0.0.1:8000>

laravel\framework位置：
C:\laragon\www\laravelapp\vendor\laravel\framework
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

php artisan make:controller StaticPagesController --plain
--plain不生成预定义方法

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

[PHP Laravel命令行创建](https://blog.csdn.net/u013954399/article/details/54583165)  

[Laravel5.0 HTTP 路由](https://docs.golaravel.com/docs/5.0/routing/)  

[laravel 5.5 -- router](https://blog.csdn.net/OneGoal/article/details/77825781)  

[[ Laravel 5.2 文档 ] 基础 —— HTTP 路由](http://laravelacademy.org/post/2784.html)  

[[ Laravel 5.6 文档 ] 基础组件 —— 路由](http://laravelacademy.org/post/8731.html)  


Laravel Blade
---

[PHP laravel系列之Blade模版](https://blog.csdn.net/u014665013/article/details/77801111)  

[Laravel Blade 模板用法](https://segmentfault.com/a/1190000010864876)  

> 向视图传递变量
> return view('sites.about')->with("name", $name);
```
         return view("about")->with([
             'name'=>$name,
             'date'=>$date
         ]);
         
         return view("about", compact('name', 'date'));
         
         @data = [...];
         return view("about", $data);
```

[laravel blade 模版 常用 演示用法](https://blog.csdn.net/lijingshan34/article/details/62890277)  

[blade模板使用总结1](https://blog.csdn.net/qq_37788558/article/details/75331572)  

[laravel compact的用法](https://blog.csdn.net/fjnjxr/article/details/73608610)  

[laravel的blade模板笔记](https://blog.csdn.net/beyond__devil/article/details/52712810)  

[Blade模板变量使用集锦](https://blog.csdn.net/fationyyk/article/details/51505157)  

[Laravel-Blade模板引擎](https://blog.csdn.net/ks3ks/article/details/54942830)  

------

Laravel Migration
---

[Database: Migrations](https://laravel.com/docs/5.6/migrations)  

[[ Laravel 5.6 文档 ] 快速入门 —— 安装配置](http://laravelacademy.org/post/8650.html#toc_5)  

[[ Laravel 5.6 文档 ] 数据库操作 —— 快速入门](http://laravelacademy.org/post/8830.html)  

[laravel之Migration的操作](https://segmentfault.com/a/1190000008659390)  

```
检查根目录的.env文件
//查看框架版本
php artisan --version
//创建表 
php artisan make:migration create_table_users --create=users;
//查看创建表语句 
php artisan migrate --pretend 
//回滚操作 撤销
php artisan migrate:rollback
//数据库建立
php artisan migrate
表的操作 
表单字段的设计 ：
Schema::create('users', function (Blueprint $table) {
       //调用相关的方法  即可自动的创建字段 更加灵活更加方便 
            $table->increments('id');
            $table->string('username')->unique();
            $table->string('email')->unique()->nullable();
          //手机考虑到无符号 与区别 与未来的发展趋势 考虑用string  
            $table->string('phone')->unique()->nullable();
            $table->text('avatar_url')->nullable();
            //$table->string('country_code')->default('+86');
            $table->string('password');
            $table->text('intro')->nullable();
            $table->timestamps();
        });
创建完可以使用 php artisan migrate --pretend查看数据表创建语句
添加表字段
php artisan make:migrate add_intro_column_to_user --table=users
up():
   $table->string('intro');

down():
    $table->dropColumn('intro');

字段修改要下载doctrine/dbal：
composer require doctrine/dbal

字段修改：
$table->string('name',50)->nullable()->change;
字段改名：
$table->renameColumn('from', 'to');
参见：https://laravel.com/docs/5.6/migrations
```

[php中环境变量$_ENV与getenv](https://blog.csdn.net/zhezhebie/article/details/72734590)  

[Laravel数据库迁移（Database Migration）操作实例](https://blog.csdn.net/lgyaxx/article/details/61615351)  
```
Migration看作一种数据库的VCS（Version Control System），即版本控制系统。可以通过Laravel的artisan命令快速创建或还原Migration文件，来进行数据库的构架
```

[Laravel 利用migrate 创建数据表](https://blog.csdn.net/incloud_anke/article/details/53033161)  

[Laravel- 使用migration 创建数据库](https://blog.csdn.net/iong_l/article/details/69391250)  

----------------

Laravel Eloquent ORM
---

[Laravel Eloquent](https://laravel.com/docs/5.6/eloquent)  

[[ Laravel 5.6 文档 ] Eloquent ORM —— 快速入门](http://laravelacademy.org/post/8855.html)  
```
定义模型
创建模型实例最简单的办法就是使用 Artisan 命令 make:model：
php artisan make:model User

如果你想要在生成模型时生成数据库迁移，可以使用 --migration 或 -m 选项：
php artisan make:model User --migration
php artisan make:model User -m
php artisan make:model Article
```

[使用 Php Artisan Tinker 来调试你的 Laravel](https://www.jianshu.com/p/9cc3d8df614f)  

```
php artisan tinker
>>>$article = new App\Artilc;
>>>$article->title = "My first title";
>>>$article->published_at = Carbon\Carbon::now();
>>>$article->save();
>>>$article->toArray();
>>>$first=App\Article::find(1);
>>>$first->title="Update";
>>>$first->save();
>>>$second=App\Article::where('content','=','content')->get();
>>>$second=App\Article::where('content','content')->get();
>>>$second=App\Article::where('content','contenr')->first();
>>>$article=App\Article::create(['title'=>'Second Title','content'=>'Second Content','published_at'=>Carbom\Carbon::new()]);
出错

不能直接填充，在Article的model中设置：
class Article extends Model
{
    protected $fillable=['title','content','published_ad'];
}
退出tinker
重启tinker:
>>>$article=App\Article::create(['title'=>'Second Title','content'=>'Second Content','published_at'=>Carbom\Carbon::new()]);
>>>$article->update('title'=>'Change Second Title');

>>>$first = App\Article::find(1);
>>>$first->delete();

Laravel Eloquent
https://laravel.com/docs/5.6/eloquent

```
[Read–Eval–Print Loop (REPL)](https://en.wikipedia.org/wiki/Read%E2%80%93eval%E2%80%93print_loop)  

[Laravel入门实战之一（打造一个PHP REPL）](https://blog.csdn.net/xuxiuning/article/details/78549759)  

[使用 Php Artisan Tinker 来调试你的 Laravel](https://www.jianshu.com/p/9cc3d8df614f)  

[使用 Php Artisan Tinker 来调试你的 Laravel](http://laravelacademy.org/post/4935.html)  

-------------------

Laravel Forms
---

[Laravel 5系列教程六：表单 Forms](https://www.cnblogs.com/grimm/p/5423108.html)  
blog-css-js：https://github.com/JellyBool/blog-css-js  

[Laravel 5系列教程六：表单 Forms](https://segmentfault.com/a/1190000003693675)  

[Laravel Form-builder使用}(https://blog.csdn.net/qq_33808550/article/details/53884561)  

Laravel Vuejs
---

[vuejs官网 - Vue.js](https://vuejs.org/)  

[Vue:Vue.js专业中文社区](https://www.vue-js.com/)  

[Vue.js教程](http://laravelacademy.org/tutorials/vuejs)  

[基于 Laravel 的 Vue.js 中文学习教程 —— 入门篇](http://laravelacademy.org/post/5538.html)  

[基于 Laravel 的 Vue.js 中文学习教程 —— 概览篇：数据绑定与组件系统](http://laravelacademy.org/post/5578.html)  

[基于 Laravel 的 Vue.js 中文学习教程 —— Vue实例](http://laravelacademy.org/post/5606.html)  

[基于 Laravel 的 Vue.js 中文学习教程 —— 数据绑定语法](http://laravelacademy.org/post/5621.html)  

[基于 Laravel 的 Vue.js 中文学习教程 —— 计算属性](http://laravelacademy.org/post/5637.html)  

[基于 Laravel 的 Vue.js 中文学习教程 —— Class 与 Style 绑定](http://laravelacademy.org/post/5725.html)  

[基于 Laravel 的 Vue.js 中文学习教程 —— 条件渲染](http://laravelacademy.org/post/5760.html)  

[Laravel Vuejs 实战视频：开发知乎](https://www.codecasts.com/series/build-a-zhihu-website-with-laravel)  
Laravel + Vue.js 开发知乎视频：https://github.com/JellyBool/zhihu-app  

[Vue.js 教程 | 菜鸟教程](http://www.runoob.com/vue2/vue-tutorial.html)  
```
<!DOCTYPE html>
<html>
<head>
<meta charset="utf-8">
<title>Vue 测试实例 - 菜鸟教程(runoob.com)</title>
<script src="https://cdn.bootcss.com/vue/2.4.2/vue.min.js"></script>
</head>
<body>
<div id="app">
  <p>{{ message }}</p>
</div>

<script>
new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue.js!'
  }
})
</script>
</body>
</html>
```

[Webpack 入门教程](http://www.runoob.com/w3cnote/webpack-tutorial.html)  

[淘宝 NPM 镜像](http://npm.taobao.org/)  

[Node.js 教程 | 菜鸟教程](http://www.runoob.com/nodejs/nodejs-tutorial.html)  

[node.js](https://nodejs.org/en/)  

Laravel 富文本编辑
---

[Laravel-使用富文本编辑器UEditor](https://blog.csdn.net/wlzx120/article/details/77480662)  

[Laravel 框架集成 UEditor 编辑器的方法](https://blog.csdn.net/u011415782/article/details/78909750)  

[Laravel 富文本编辑框overtrue/laravel-ueditor](https://blog.csdn.net/cominglately/article/details/79773563)  

Laravel Redis
---

[Laravel中如何使用Redis](https://blog.csdn.net/json_ligege/article/details/54617452)  

[Laravel 中使用 Redis 数据库](https://blog.csdn.net/json_vip/article/details/54646122)  

[Laravel 使用Redis 笔记](https://blog.csdn.net/windwolfer/article/details/50247419)  

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

[2. Laravel视图View和路由Route初探 - Laravel从零开始教程](https://segmentfault.com/a/1190000007442260)  

[3. 视图数据View Data和Balde模版 - Laravel从零开始教程](https://segmentfault.com/a/1190000007442328)  

[4. 路由到控制器 - Laravel从零开始教程](https://segmentfault.com/a/1190000007556269)  

[5. Balde模版的布局文件 layout.blade.php - 从零开始学Laravel](https://segmentfault.com/a/1190000007582361)  

[6. 管理你的css和js文件 - 从零开始学Laravel](https://segmentfault.com/a/1190000007582395)  

[7. 从数据库获取数据- 从零开始学Laravel](https://segmentfault.com/a/1190000007596634)  

[8. 使用Elequent建立表与表之间的关系](https://segmentfault.com/blog/zhoujiping)  

[9. 表单 - 从零开始学Laravel](https://segmentfault.com/a/1190000007609708)  

[10. 更新数据及渴求式加载Eager Loading - 从零开始学Laravel](https://segmentfault.com/a/1190000007616066)  

-------

## laravel的项目

[Laravel5 入门小项目详细教程](https://blog.csdn.net/sqzhao/article/details/46791207)  
https://github.com/RryLee/StuGradeWithLaravel5  

[Laravel入门教程: 实现简单的AJAX的CRUD页面](https://blog.csdn.net/netcan_noah/article/details/52237929)  
https://github.com/netcan/Laravel_AJAX_CRUD  
HFUT_ChemLab：https://github.com/netcan/HFUT_ChemLab  

[☆首发☆非常适合学习理解laravel的项目--图书管理系统](https://blog.csdn.net/w786572258/article/details/52799555)  
https://www.github.com/786572258/laravel-bookmg  

[Laravel 完整开源项目大全](https://blog.csdn.net/qq_38568388/article/details/79384078)  
https://blog.csdn.net/qq_25600055/article/details/52451138  

[laravel 5.5整个项目](https://download.csdn.net/download/onegoal/10237383)  

-------

[Laravel Documentation](https://laravel.com/docs)  

[Laravel Laracasts](https://laracasts.com)  

[Laravel New](https://laravel-news.com)  

[Laravel Forge](https://forge.laravel.com)  

[Laravel GitHub](https://github.com/laravel/laravel)  

[Laravel framework](https://github.com/laravel/framework)  

[Laravel docs](https://github.com/laravel/docs)  

---------------------------




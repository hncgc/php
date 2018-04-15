# Laravel基础学习笔记

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
> 创建表
> php artisan make:migration create_table_users --create=users
```
检查根目录的.env文件
//查看框架版本
php artisan --version
//创建表 
php artisan make:migration create_table_users --create=users
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
php artisan make:migration add_intro_column_to_user --table=users
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
[Eloquent: Getting Started](https://laravel.com/docs/5.6/eloquent)  
https://laravel.com/docs/5.1/eloquent  

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

[PsySH：PHP交互运行环境-云栖社区-阿里云](https://yq.aliyun.com/articles/33523)  

[PsySH——PHP交互式控制台](http://blog.jobbole.com/99110/)  
- [PsySH官网](http://psysh.org/)  
- [GitHub](https://github.com/bobthecow/psysh)  
- [Packagist](https://packagist.org/packages/psy/psysh)  

[laravel Carbon函数](https://blog.csdn.net/lbwo001/article/details/53063867)  

[日期及时间处理包 Carbon 在 Laravel 中的简单使用](https://blog.csdn.net/gengfu_php/article/details/78307950)  

[laravel carbon 使用](https://blog.csdn.net/zhezhebie/article/details/79386051)  

-------------------

Laravel Forms
---

[Laravel 5系列教程六：表单 Forms](https://www.cnblogs.com/grimm/p/5423108.html)  
blog-css-js：https://github.com/JellyBool/blog-css-js  

[Laravel 5系列教程六：表单 Forms](https://segmentfault.com/a/1190000003693675)  

[Laravel Form-builder使用](https://blog.csdn.net/qq_33808550/article/details/53884561)  

[Laravel教程 六：表单 Forms](https://laravist.com/article/14)  
https://www.codecasts.com/blog/post/programming-with-laravel-5-laravel-forms-input  
```
laravel 5.2 之后请使用 laravelcollective/html 替换 illuminate/html

首先到https://github.com/JellyBool/blog-css-js得到静态文件，然后分别修改下面三个文件：
1. app.blade.php
2. articles/index.blade.php
3. articles/show.blade.php
下面的视图代码的修改部分，如果你偷懒，你可以使用ctrl+c大法。
在app.blade.php中：将原来@yield('content')的代码替换成下面的代码：
<body>
    <div class="container">
            <section class="content">
                <div class="pad group">
                    @yield('content')
                </div>
            </section>
        </div>
</body>
就是在外面多加了个div和一个section。
再引入这两个css文件：
<link rel='stylesheet' href="/css/bootstrap.min.css" type='text/css' media='all'/>
<link rel='stylesheet' href="/css/all.css" type='text/css' media='all'/>
一个是bootstrap，一个是自定义的。
在articles/index.blade.php文件中，我们将每个$article放在<article>标签中：
```

> laravel 5.2 之后请使用 laravelcollective/html 替换 illuminate/html

[Laravel 组件之 Forms & HTML 组件 (laravelcollective/html)](https://segmentfault.com/a/1190000011580448)  
```
    "require": {
        "php": "^7.1.3",
        "fideloper/proxy": "^4.0",
        "illuminate/html": "^5.0",
        "laravel/framework": "5.6.*",
        "laravel/tinker": "^1.0",
        "nesbot/carbon": "^1.25"
    },

"illuminate/html": "^5.0",改为： （"laravelcollective/html": "5.1.*"失败）"laravelcollective/html": "5.6",
"require": {
    ......
    "laravelcollective/html": "5.6"
    ......
}

    "require": {
        "php": "^7.1.3",
        "fideloper/proxy": "^4.0",
        "illuminate/html": "^5.0",
        "laravel/framework": "5.6.*",
        "laravel/tinker": "^1.0",
        "laravelcollective/html": "^5.6",
        "nesbot/carbon": "^1.25"
    },

接下来从命令行更新 composer :(不能安装laravelcollective/html)
composer update -vvv
C:\laragon\www\laravelapp (master)
λ composer update -vvv
......
以下方法安装laravelcollective/html成功

C:\laragon\www\laravelapp (master)
λ composer require laravelcollective/html
Using version ^5.6 for laravelcollective/html
./composer.json has been updated
Loading composer repositories with package information
Updating dependencies (including require-dev)
Package operations: 1 install, 0 updates, 0 removals
  - Installing laravelcollective/html (v5.6.5): Downloading (100%)
Package illuminate/html is abandoned, you should avoid using it. Use laravelcollective/html instead.
Writing lock file
Generating optimized autoload files
> Illuminate\Foundation\ComposerScripts::postAutoloadDump
> @php artisan package:discover
Discovered Package: fideloper/proxy
Discovered Package: laravel/tinker
Discovered Package: nunomaduro/collision
Discovered Package: laravelcollective/html
Package manifest generated successfully.

C:\laragon\www\laravelapp (master)
λ
接下来添加 provider 到 config/app.php 的 providers 数组:

'providers' => [
    // ...
    Collective\Html\HtmlServiceProvider::class,
    // ...
],
最后 添加两个类链接到 config/app.php 的 aliases 数组:

'aliases' => [
    // ...
    'Form' => Collective\Html\FormFacade::class,
    'Html' => Collective\Html\HtmlFacade::class,
    // ...
],

C:\laragon\www\laravelapp\config\app.php
```


创建数据表单
---

```
C:\laragon\www\laravelapp\routes\web.php

Route::get('articles/{id}', 'ArticlesController@show');
Route::get('articles/create', 'ArticlesController@create');

C:\laragon\www\laravelapp\app\Http\Controllers\ArticlesController.php
    public function create(){
        return view('articles.create');
    }

C:\laragon\www\laravelapp\resources\views\articles\create.blade.php
@extends('layouts.app')
@section('content')
    <h1>撰写新文章</h1>
@endsection

http://127.0.0.1:8000/articles/create
Sorry, the page you are looking for could not be f
原因：先匹配articles/{id}

修改路由：
Route::get('articles/create', 'ArticlesController@create');
Route::get('articles/{id}', 'ArticlesController@show');

安装illuminate/html
composer require illuminate/html
https://github.com/illuminate/html


    {!! Form::open() !!}

    {!! Form::close() !!}
生成：
    <form method="POST" action="http://127.0.0.1:8000/articles/create" accept-charset="UTF-8"><input name="_token" type="hidden" value="kPWdeSIcCbcaWWSvQQhGk5mUSFBHrI7d3d3x31uM">

    </form>
```
## 创建表单并保存  
```
C:\laragon\www\laravelapp\resources\views\articles\create.blade.php
@extends('layouts.app')
@section('content')
    <h1>撰写新文章</h1>
    {!! Form::open(['url' => 'articles']) !!}
    <div class="form-group">
        {!! Form::label('title') !!}
        {!! Form::text('title', null, ['class' => 'form-control']) !!}
    </div>
    <!--- Content Field --->
    <div class='form-group'>
        {!! Form::label('content', 'Content:') !!}
        {!! Form::textarea('content', null, ['class' => 'form-control']) !!}
    </div>
    {!! Form::submit('发表文章', ['class' => 'btn btn-primary form-control']) !!}
    {!! Form::close() !!}
@endsection

C:\laragon\www\laravelapp\app\Http\Controllers\ArticlesController.php
    public function index()
    {
        //$articles = Article::all();
        $articles = Article::latest()->get();
        return view('articles.index', compact('articles'));
    }

    /**
     * 保存表单数据
     * @param Request $request
     */
    public function store(Request $request)
    {
        //接收post过来的数据
        //存入数据库
        //重定向
        //dd($request->get('title'));
        $input = $request->all();
        $input['published_at'] = Carbon::now();
        Article::create($input);
        return redirect('/articles');
    }

C:\laragon\www\laravelapp\routes\web.php

Route::get('articles', 'ArticlesController@index');
Route::get('articles/create', 'ArticlesController@create');
Route::get('articles/{id}', 'ArticlesController@show');
Route::post('articles', 'ArticlesController@store');

```

[视频：queryScope和setAttribute用法](https://www.codecasts.com/series/laravel-5-basic/episodes/10)  

[Laravel 5系列教程八：queryScope 和 setAttribute](https://www.codecasts.com/blog/post/programming-with-laravel-5-queryscope-and-set-attribute)  
http://www.360doc.com/content/16/1220/14/29401987_616271752.shtml  

#### 在表单中添加published_at  
```
C:\laragon\www\laravelapp\resources\views\articles\create.blade.php

    <!-- published_at Field -->
    <div class="form-group">
        {!! Form::label('published_at', 'Published_at: ') !!}
        {!! Form::input('date', 'published_at', Date('Y-m-d'), ['class' => 'form-control']) !!}
    </div>
```
#### 在model中设置published_at作为Carbon对象，预处理published_at，限定显示的条件scopePublished()在Controller中用published()调用
```
C:\laragon\www\laravelapp\app\Article.php
class Article extends Model
{
    protected $fillable = ['title', 'content', 'published_at'];

    //作为Carbon对象的字段
    protected $dates = ['published_at'];

    //预处理published_at
    public function setPublishedAtAttribute($date){
        //$this->attributes['published_at'] = date('Y-m-d H:i:s',$date->getTimestamp());
        $this->attributes['published_at'] = Carbon::createFromFormat('Y-m-d',$date);
    }

    /**
     * 在Controller中用在限定显示的条件，用published()调用
     * @param $query
     */
    public function scopePublished($query){
        $query->where('published_at', '<=', Carbon::now());
    }
}
```

#### 在ArticlesController中保存时在model中预处理published_at
```
C:\laragon\www\laravelapp\app\Http\Controllers\ArticlesController.php
    public function store(Request $request)
    {
        //接收post过来的数据
        //存入数据库
        //重定向
        //dd($request->get('title'));
        //$input = $request->all();
        //$input['published_at'] = Carbon::now();
        //Article::create($input);
        Article::create($request->all()); //在model中预处理published_at
        return redirect('/articles');
    }
```

#### 一条记录字段的属性及日期格式的多种显示
```
C:\laragon\www\laravelapp\app\Http\Controllers\ArticlesController.php
     */
    public function show($id)
    {
        $article = Article::findOrFail($id);
        //dd($article);
        dd($article->created_at);
        dd($article->created_at->year);
        dd($article->created_at->diffForHumans());
        if (is_null($article)) {
            abort('404');
        }
        return view('articles.show', compact('article'));
    }
```

#### 以友好的方式显示
```
$article->published_at->diffForHumans()
"50 minutes ago"
```
--------

Laravel 表单验证 Validation
---
[Laravel 表单验证 视频](https://www.codecasts.com/series/laravel-5-basic/episodes/11)  

[Laravel教程 七:表单验证 Validation](https://www.codecasts.com/blog/post/programming-with-laravel-5-form-request-and-validation)  

[Laravel Validation规则](https://laravel.com/docs/5.1/validation)  
https://laravel.com/docs/5.6/validation  

[如何使用 Laravel 框架的 validator](https://www.jianshu.com/p/27bc0eedc954)  

[Laravel 中 validation 验证 返回中文提示 全局设置](https://www.cnblogs.com/wlphp/p/8094027.html)  

[laravel 基础教程 —— 验证](https://www.jianshu.com/p/9ce7d0fa780d)  

[Laravel Http层--验证](https://www.jianshu.com/p/737fc3eace74)  

[Laravel-自定义验证规则](https://blog.csdn.net/wlzx120/article/details/76997844)  

[Laravel-自定义验证规则](https://blog.csdn.net/wlzx120/article/details/76997844)  
```
安装中文验证包以及项目本地化：
使用 Composer 来安装 laravel-lang。
$ composer require "overtrue/laravel-lang:~3.0"
自定义验证码规则，自定义一条验证规则
实现方法：
1、服务提供者 AppServiceProvider-boot方法下添加代码：
use Illuminate\Support\Facades\Validator;
public function boot()
    {
        //自定义验证码规则
        Validator::extend('yzmgz', function($attribute, $value, $parameters){
            return $value == session('milkcaptcha');
        });
    }
zh-CN/validation.php 验证规则中文包最后添加一条：
'yzmgz' => '验证码错误！',
使用
$this->validate($request,[  
            'name' => 'required|unique:users|max:60',  
            'email' => 'required|email',  
            'password' => 'required|min:6',  
            'yzm' => 'required|string|yzmgz',  
        ]);  
```

[laravel validator 表单验证](https://blog.csdn.net/xiaosevenliang/article/details/44464073)  

```
C:\laragon\www\laravelapp (master)
λ php -S localhost:8000
PHP 7.1.14 Development Server started at Sun Apr  8 23:08:53 2018
Listening on http://localhost:8000
Document root is C:\laragon\www\laravelapp
Press Ctrl-C to quit.

http://localhost:8000/server.php/articles

两种方式的表单验证：Request和validate
php artisan make:request CreateArticleRequest
                                                
C:\laragon\www\laravelapp (master)              
λ php artisan make:request CreateArticleRequest 
Request created successfully.                   
                                                
C:\laragon\www\laravelapp (master)              

C:\laragon\www\laravelapp\app\Http\Requests\CreateArticleRequest.php

class CreateArticleRequest extends FormRequest
{
    
    public function authorize()
    {
        return true;
    }


    public function rules()
    {
        return [
            'title' => 'required|min:3',
            'content' => 'required',
            'published_at' => 'required'
        ];
    }


   //Request验证
    public function store(Requests\CreateArticleRequest $request){
        Article::create($request->all()); //在model中预处理published_at
        return redirect('/articles');
    }
    
    //validate验证
    public function store(Request $request)
    {
        //接收post过来的数据
        //存入数据库
        //重定向
        //dd($request->get('title'));
        //$input = $request->all();
        //$input['published_at'] = Carbon::now();
        //Article::create($input);
        $this->validate($request, ['title'=>'required|min:3', 'content'=>'required', 'published_at'=>'required']);
        Article::create($request->all()); //在model中预处理published_at
        return redirect('/articles');
    }

表单修改
C:\laragon\www\laravelapp\resources\views\articles\create.blade.php
add:
    @if($errors->any())
        <ul class="list-group">
            @foreach($errors->all() as $error)
                <li class="list-group-item list-group-item-danger">{{ $error }}</li>
            @endforeach
        </ul>
    @endif
```

--------

Laravel Form-Model-Binding
---

[Form-Model-Binding 视频](https://www.codecasts.com/series/laravel-5-basic/episodes/12)  

[Laravel教程 十：实现文章的修改](https://www.codecasts.com/blog/post/programming-with-laravel-5-blade-how-to-edit-article)  

#### 建立路由
> Route::get('/articles/{id})/edit', 'ArticlesController@edit'); 
> 或：
> Route::get('/articles)/edit/{id}', 'ArticlesController@edit');

#### 路由列表
> php artisan route:list
```
C:\laragon\www\laravelapp (master)
λ php artisan route:list
+--------+----------+--------------------+-------+------------------------------------------------+--------------+
| Domain | Method   | URI                | Name  | Action                                         | Middleware   |
+--------+----------+--------------------+-------+------------------------------------------------+--------------+
|        | GET|HEAD | /                  |       | Closure                                        | web          |
|        | GET|HEAD | about              | about | App\Http\Controllers\AboutController@index     | web          |
|        | GET|HEAD | api/user           |       | Closure                                        | api,auth:api |
|        | GET|HEAD | articles           |       | App\Http\Controllers\ArticlesController@index  | web          |
|        | POST     | articles           |       | App\Http\Controllers\ArticlesController@store  | web          |
|        | GET|HEAD | articles/create    |       | App\Http\Controllers\ArticlesController@create | web          |
|        | GET|HEAD | articles/{id}      |       | App\Http\Controllers\ArticlesController@show   | web          |
|        | GET|HEAD | articles/{id}/edit |       | App\Http\Controllers\ArticlesController@edit   | web          |
|        | GET|HEAD | myabout            |       | Closure                                        | web          |
+--------+----------+--------------------+-------+------------------------------------------------+--------------+
```
#### 由控件器直接生成路由
> Route::resource('articles','ArticlesController');
```
C:\laragon\www\laravelapp\routes\web.php

/*
Route::get('articles', 'ArticlesController@index');
Route::get('articles/create', 'ArticlesController@create');
Route::get('articles/{id}', 'ArticlesController@show');
Route::post('articles', 'ArticlesController@store');
Route::get('articles/{id}/edit','ArticlesController@edit');
*/
Route::resource('articles','ArticlesController');
```
#### 路由列表
```
C:\laragon\www\laravelapp (master)
λ php artisan route:list
+--------+-----------+-------------------------+------------------+-------------------------------------------------+--------------+
| Domain | Method    | URI                     | Name             | Action                                          | Middleware   |
+--------+-----------+-------------------------+------------------+-------------------------------------------------+--------------+
|        | GET|HEAD  | /                       |                  | Closure                                         | web          |
|        | GET|HEAD  | about                   | about            | App\Http\Controllers\AboutController@index      | web          |
|        | GET|HEAD  | api/user                |                  | Closure                                         | api,auth:api |
|        | GET|HEAD  | articles                | articles.index   | App\Http\Controllers\ArticlesController@index   | web          |
|        | POST      | articles                | articles.store   | App\Http\Controllers\ArticlesController@store   | web          |
|        | GET|HEAD  | articles/create         | articles.create  | App\Http\Controllers\ArticlesController@create  | web          |
|        | GET|HEAD  | articles/{article}      | articles.show    | App\Http\Controllers\ArticlesController@show    | web          |
|        | PUT|PATCH | articles/{article}      | articles.update  | App\Http\Controllers\ArticlesController@update  | web          |
|        | DELETE    | articles/{article}      | articles.destroy | App\Http\Controllers\ArticlesController@destroy | web          |
|        | GET|HEAD  | articles/{article}/edit | articles.edit    | App\Http\Controllers\ArticlesController@edit    | web          |
|        | GET|HEAD  | myabout                 |                  | Closure                                         | web          |
+--------+-----------+-------------------------+------------------+-------------------------------------------------+--------------+
```
#### 控件器修改
> C:\laragon\www\laravelapp\app\Http\Controllers\ArticlesController.php
```
    public function edit($id)
    {
        $article = Article::findOrFail($id);
        return view('articles.edit', compact('article'));
    }
    /*
    public function update(Request $request, $id) //未验证
    {
        $article = Article::findOrFail($id);
        $article->update($request->all());
        return redirect('/articles');
    }
    */
    public function update(Requests\CreateArticleRequest $request, $id)
    {
        $article = Article::findOrFail($id);
        $article->update($request->all());
        return redirect('/articles');
    }

C:\laragon\www\laravelapp\app\Http\Requests\CreateArticleRequest.php
    public function rules()
    {
        return [
            'title' => 'required|min:3',
            'content' => 'required',
            'published_at' => 'required'
        ];
    }
```
#### 添加规则
> C:\laragon\www\laravelapp\app\Http\Requests\CreateArticleRequest.php
```
    public function rules()
    {
        $rules = [
            'title' => 'required|min:3',
            'content' => 'required',
            'published_at' => 'required'
        ];
//        if(isEdit()){
//            $rules['something'] = 'required';
//        }
        return $rules;
    }
```
#### 建立修改表单
> C:\laragon\www\laravelapp\resources\views\articles\form.blade.php
```
<div class="form-group">
    {!! Form::label('title', 'Titel:') !!}
    {!! Form::text('title', null, ['class' => 'form-control']) !!}
</div>
<!--- Content Field --->
<div class='form-group'>
    {!! Form::label('content', 'Content:') !!}
    {!! Form::textarea('content', null, ['class' => 'form-control']) !!}
</div>
<!-- published_at Field -->
<div class="form-group">
    {!! Form::label('published_at', '发布日期: ') !!}
    {!! Form::input('date', 'published_at', Date('Y-m-d'), ['class' => 'form-control']) !!}
</div>
{!! Form::submit('发表文章', ['class' => 'btn btn-primary form-control']) !!}

C:\laragon\www\laravelapp\resources\views\errors\list.blade.php
@if($errors->any())
    <ul class="list-group">
        @foreach($errors->all() as $error)
            <li class="list-group-item list-group-item-danger">{{ $error }}</li>
        @endforeach
    </ul>
@endif

C:\laragon\www\laravelapp\resources\views\articles\create.blade.php
@extends('layouts.app')
@section('content')
    <h1>撰写新文章</h1>
    {!! Form::open(['url' => 'articles']) !!}
    @include('articles.form');
    {!! Form::close() !!}
    @include('errors.list')
@endsection

C:\laragon\www\laravelapp\resources\views\articles\edit.blade.php
@extends('layouts.app')
@section('content')
    <h1>修改文章</h1>
    {!! Form::model($article, ['method' => 'PATCH', 'url'=>'/articles/'.$article->id]) !!}
    @include('articles.form')
    {!! Form::close() !!}
    @include('errors.list')
@endsection
```


用户注册和登录--Laravel 5.1
---

Laravel 5.1 视频基础教程 >> 用户注册和登录
https://www.codecasts.com/series/laravel-5-basic/episodes/13

#### 注册路由
```
Laravel 5.1:
Route::get('auth/login', 'Auth\AuthController@getLogin');
Route::post('auth/login', 'Auth\AuthController@postLogin');
Route::get('auth/register', 'Auth\AuthController@getRegister');
Route::post('auth/register', 'Auth\AuthController@postRegister');
Route::get('auth/logout', 'Auth\AuthController@getLogout');

Laravel 5.6.3:
Auth::routes();
Route::get('/home', 'HomeController@index')->name('home');
Route::get('/logout', 'Auth\LoginController@logout');
```
#### 登录表单
```
C:\laragon\www\laravelapp\resources\views\auth\login.blade.php
@extends('layouts.app')
@section('content')
    <div class="col-md-4 col-md-offset-4">
        {!! Form::open(['url'=>'/auth/login']) !!}
        <!-- Email Field -->
        <div class="form-group">
            {!! Form::label('email', 'Email:') !!}
            {!! Form::email('email', null, ['class' => 'form-control']) !!}
        </div>
        <!-- Password Field -->
        <div class="form-group">
            {!! Form::label('password', 'Password:') !!}
            {!! Form::password('password', ['class' => 'form-control']) !!}
        </div>
        {!! Form::submit('登录', ['class'=>'btn btn-primary form-control']
        {!! Form::close() !!}
    </div>
@stop
```
#### 注册表单
```
C:\laragon\www\laravelapp\resources\views\auth\register.blade.php
@extends('layouts.app')
@section('content')
    <div class="col-md-4 col-md-offset-4">
        {!! Form::open(['url'=>'/auth/register']) !!}
        <!-- Email Field -->
        <div class="form-group">
            {!! Form::label('name', 'Name:') !!}
            {!! Form::email('name', null, ['class' => 'form-control']) !!}
        </div>
        <div class="form-group">
            {!! Form::label('email', 'Email:') !!}
            {!! Form::email('email', null, ['class' => 'form-control']) !!}
        </div>
        <!-- Password Field -->
        <div class="form-group">
            {!! Form::label('password', 'Password:') !!}
            {!! Form::password('password', ['class' => 'form-control']) !!}
        </div>
        <!-- Password_confirmation Field -->
        <div class="form-group">
            {!! Form::label('password_confirmation', 'Password confirmation:') !!}
            {!! Form::password('password_confirmation', ['class' => 'form-control']) !!}
        </div>
        {!! Form::submit('注册', ['class'=>'btn btn-primary form-control']
        {!! Form::close() !!}
    </div>
@stop
```
> 注册成功后跳到 http://localhost:8000/home 出错，原因是没有这个路由

#### 修复错误
```
在AuthController中添加：

    protected $redirectTo = '/articles';
```
----------------

用户注册和登录 -- Lavarel 5.6.3
---

Laravel 5.1用户认证（一） —— 使用Laravel内置组件快速实现注册登录
http://laravelacademy.org/post/1258.html

[Laravel 5.2]二、注册、登陆及用户认证
https://blog.csdn.net/scargtt/article/details/51428141

laravel 5.3 单用户登录简单实现
https://blog.csdn.net/qq_35059693/article/details/54943485

Laravel 5.3 不同用户表登录认证
https://blog.csdn.net/realghost/article/details/52512268

Laravel 5.3 使用内置的 Auth 组件实现多用户认证功能以及登陆才能访问后台的功能的一种实现方法
https://blog.csdn.net/kevinbai_cn/article/details/54341779

laravel身份验证-Auth的使用
https://blog.csdn.net/li_haijiang/article/details/71603994

laravel的Auth认证，登录、注册后的页面回跳
https://blog.csdn.net/beyond__devil/article/details/76212267

Laravel 重写用户登录
https://blog.csdn.net/hxx_yang/article/details/51891336

Laravel5.4注册登录解析及使用教程
https://blog.csdn.net/gu_wen_jie/article/details/77428484

Middleware


```
C:\laragon\www\laravelapp (master)
λ php artisan make:auth

 The [layouts/app.blade.php] view already exists. Do you want to replace it? (yes/no) [no]:
 > no

Authentication scaffolding generated successfully.

C:\laragon\www\laravelapp (master)
λ

生成：
C:\laragon\www\laravelapp\app\Http\Controllers\HomeController.php

C:\laragon\www\laravelapp\resources\views\auth
C:\laragon\www\laravelapp\resources\views\auth\login.blade.php
C:\laragon\www\laravelapp\resources\views\auth\register.blade.php
C:\laragon\www\laravelapp\resources\views\auth\passwords
C:\laragon\www\laravelapp\resources\views\auth\passwords\email.blade.php
C:\laragon\www\laravelapp\resources\views\auth\passwords\reset.blade.php
C:\laragon\www\laravelapp\resources\views\home.blade.php

C:\laragon\www\laravelapp\routes\web.php

增加：

Auth::routes();

Route::get('/home', 'HomeController@index')->name('home');

        new file:   app/Http/Controllers/HomeController.php
        new file:   resources/views/auth/login.blade.php
        new file:   resources/views/auth/passwords/email.blade.php
        new file:   resources/views/auth/passwords/reset.blade.php
        new file:   resources/views/auth/register.blade.php
        new file:   resources/views/home.blade.php
        modified:   resources/views/welcome.blade.php

C:\laragon\www\laravelapp (master)
λ php artisan serve
Laravel development server started: <http://127.0.0.1:8000>
[Wed Apr 11 01:40:49 2018] 127.0.0.1:58825 [200]: /favicon.ico

C:\laragon\www\laravelapp\resources\views\welcome.blade.php

                @auth
                    <a href="{{ url('/home') }}">Home</a>
                @else
                    <a href="{{ route('login') }}">Login</a>
                    <a href="{{ route('register') }}">Register</a>
                @endauth


http://127.0.0.1:8000
http://127.0.0.1:8000/home
http://127.0.0.1:8000/login
http://127.0.0.1:8000/register
http://127.0.0.1:8000/home
Dashboard
You are logged in!    

注销
http://127.0.0.1:8000/logout
Symfony \ Component \ HttpKernel \ Exception \ MethodNotAllowedHttpException 

C:\laragon\www\laravelapp\routes\web.php

Auth::routes();
Route::get('/home', 'HomeController@index')->name('home');
Route::get('/logout', 'Auth\LoginController@logout');

C:\laragon\www\laravelapp\app\Http\Controllers\Auth\LoginController.php
    use AuthenticatesUsers;

    /**
     * Where to redirect users after login.
     * 登录成功后跳转地址
     * @var string
     */
    protected $redirectTo = '/home';
    // 退出后跳转地址
    protected $redirectAfterLogout = '/login';
    /**
     * Create a new controller instance.
     *
     * @return void
     */
    public function __construct()
    {
        $this->middleware('guest')->except('logout');
    }

Auth::routes(); 
定义在vendor/laravel/framework/src/Illuminate/Support/Facades/Auth.php文件中

C:\laragon\www\laravelapp\vendor\laravel\framework\src\Illuminate\Support\Facades\Auth.php

    /**
     * Register the typical authentication routes for an application.
     *
     * @return void
     */
    public static function routes()
    {
        static::$app->make('router')->auth();
    }

C:\laragon\www\laravelapp\vendor\laravel\framework\src\Illuminate\Routing\Router.php

   public function auth()
    {
        // Authentication Routes...
        $this->get('login', 'Auth\LoginController@showLoginForm')->name('login');
        $this->post('login', 'Auth\LoginController@login');
        $this->post('logout', 'Auth\LoginController@logout')->name('logout');

        // Registration Routes...
        $this->get('register', 'Auth\RegisterController@showRegistrationForm')->name('register');
        $this->post('register', 'Auth\RegisterController@register');

        // Password Reset Routes...
        $this->get('password/reset', 'Auth\ForgotPasswordController@showLinkRequestForm')->name('password.request');
        $this->post('password/email', 'Auth\ForgotPasswordController@sendResetLinkEmail')->name('password.email');
        $this->get('password/reset/{token}', 'Auth\ResetPasswordController@showResetForm')->name('password.reset');
        $this->post('password/reset', 'Auth\ResetPasswordController@reset');
    }


C:\laragon\www\laravelapp\vendor\laravel\framework\src\Illuminate\Foundation\Auth\AuthenticatesUsers.php

    public function logout(Request $request)
    {
        $this->guard()->logout();

        $request->session()->invalidate();

        return redirect('/');
    }

```

[Laravel5.2 Auth认证退出失效](https://blog.csdn.net/fationyyk/article/details/51514366)  

[Laravel自带的anth认证中logout无效](https://blog.csdn.net/darry_zhao/article/details/52689623)  
```
laravel5.6注销路由：成功 
Route::get('/logout', 'Auth\LoginController@logout'); 
```
[Laravel5.4的应用目录结构](https://blog.csdn.net/gu_wen_jie/article/details/59518376)  

## Eloquent Relationship

[Laravel教程 九：Eloquent Relationship](https://www.codecasts.com/blog/post/programming-with-laravel-5-eloquent-relatiosnhsip-many-to-many)  

添加标签
---

#### 创建表
```
php artisan make:migration create_table_tags --create=tags 

C:\laragon\www\laravelapp (master)
λ php artisan make:migration create_table_tags --create=tags
Created Migration: 2018_04_14_200052_create_table_tags
```
#### 增加name字段
```
C:\laragon\www\laravelapp\database\migrations\2018_04_14_200052_create_table_tags.php
    public function up()
    {
        Schema::create('tags', function (Blueprint $table) {
            $table->increments('id');
            $table->string('namw');			//应为name
            $table->timestamps();
        });
    }

C:\laragon\www\laravelapp (master)
λ php artisan migrate
Migrating: 2018_04_14_200052_create_table_tags
Migrated:  2018_04_14_200052_create_table_tags
```
#### 为tags表创建一个Tag模型:
```
php artisan make:model Tag
C:\laragon\www\laravelapp (master)
λ php artisan make:model Tag
Model created successfully.

C:\laragon\www\laravelapp (master)
λ
C:\laragon\www\laravelapp\app\Tag.php

class Tag extends Model
{
    protected $fillable = ['name'];
}
```
#### 创建关系表article_tag
```
这个表只存tag_id和article_id
php artisan make:migration create-article_tag-table  --create=article_tag
C:\laragon\www\laravelapp (master)
λ php artisan make:migration create-article_tag-table  --create=article_tag
Created Migration: 2018_04_14_202340_create-article_tag-table

C:\laragon\www\laravelapp\database\migrations\2018_04_14_202340_create-article_tag-table.php
    /**
     * Run the migrations.
     *
     * @return void
     */
    public function up()
    {
        Schema::create('article_tag', function (Blueprint $table) {
            $table->increments('id');
            $table->integer('article_id')->unsigned()->index();
            $table->foreign('article_id')->references('id')->on('articles')->onDelete('cascade');	//外键
            $table->integer('tag_id')->unsigned()->index();
            $table->foreign('tag_id')->references('id')->on('tags')->onDelete('cascade');               //外键
            $table->timestamps();
        });

C:\laragon\www\laravelapp (master)
λ php artisan migrate
Migrating: 2018_04_14_202340_create-article_tag-table
Migrated:  2018_04_14_202340_create-article_tag-table
```
#### 发现tags表字段name误写成了namw,2次回滾：
```
C:\laragon\www\laravelapp (master)
λ php artisan migrate:rollback
Rolling back: 2018_04_14_202340_create-article_tag-table
Rolled back:  2018_04_14_202340_create-article_tag-table

C:\laragon\www\laravelapp (master)
λ php artisan migrate:rollback
Rolling back: 2018_04_14_200052_create_table_tags
Rolled back:  2018_04_14_200052_create_table_tags

C:\laragon\www\laravelapp\database\migrations\2018_04_14_200052_create_table_tags.php
    public function up()
    {
        Schema::create('tags', function (Blueprint $table) {
            $table->increments('id');
            $table->string('name');       //namw改为name
            $table->timestamps();
        });
    }

C:\laragon\www\laravelapp (master)
λ php artisan migrate
Migrating: 2018_04_14_200052_create_table_tags
Migrated:  2018_04_14_200052_create_table_tags
Migrating: 2018_04_14_202340_create-article_tag-table
Migrated:  2018_04_14_202340_create-article_tag-table
```
声明Eloquent的关系
---
```
Articles 和 Tags 是多对多的关系，在Article.php中声明下面的关系：
C:\laragon\www\laravelapp\app\Article.php
public function tags()
{
    return $this->belongsToMany('App\Tag');
}

在Tag.php，也同样：
C:\laragon\www\laravelapp\app\Tag.php
public function articles()
{
    return $this->belongsToMany('App\Article');
}

使用$this->belongsToMany()来表明Eloquent的关系，这里需要注意的是如果你的外键并不是article_id和tag_id，你需要在第三个参数进行设置，写成类似下面这样：
public function articles()
{
    return $this->belongsToMany('App\Article','conversation_id');
}
```

利用tinker在表Tags中插入数据
---

```
C:\laragon\www\laravelapp (master)
λ php artisan tinker
Psy Shell v0.8.18 (PHP 7.1.14 — cli) by Justin Hileman
>>> $tag = new App\Tag;
=> App\Tag {#780}
>>> $tag['name'] = 'Java';
=> "Java"
>>> $tag->save();
>>> $tag = new App\Tag;
=> App\Tag {#776}
>>> $tag['name'] = 'Php';
=> "Php"
>>> $tag->save();
=> true
>>> $tag = new App\Tag;
=> App\Tag {#780}
>>> $tag['name'] = 'Python';
=> "Python"
>>> $tag->save();
=> true
>>> $tag = new App\Tag;
=> App\Tag {#776}
>>> $tag['name'] = 'C';
=> "C"
>>> $tag->save();
=> true
>>> $tag = new App\Tag;
=> App\Tag {#780}
>>> $tag['name'] = 'C++';
=> "C++"
>>> $tag->save();
=> true
>>>
```

使用Select2
---

官网：http://select2.github.io/ 

https://github.com/select2

[Select2 下载](https://github.com/select2/select2/releases)  
https://github.com/select2/select2/archive/3.5.3.zip 

[Select2 用法](https://select2.github.io/examples.html)  

[Select2 3.5.3文档](http://select2.github.io/select2/)  

[select2 使用教程（简）](https://blog.csdn.net/jiangeeq/article/details/53116791)  

[Select2使用方法汇总](https://www.cnblogs.com/zevfang/p/7641904.html)  

[Select2下拉框总结](https://www.cnblogs.com/liuxiaobo93/p/5112993.html)  

[select2 使用笔记](https://blog.csdn.net/u014388408/article/details/50587405)  

[jquery下载](https://jquery.com/download/)  
https://github.com/jquery/jquery
[jquery-2.1.0.min.js微盘下载](http://vdisk.weibo.com/s/sX83nX3JAfFM5)  
```
下载select2:https://github.com/select2/select2/archive/3.5.3.zip 
解压后将select2.css、select2.min.js、jquery-2.1.0.min.js拷入项目
C:\laragon\www\laravelapp\public\css\select2.css
C:\laragon\www\laravelapp\public\js\select2.min.js
C:\laragon\www\laravelapp\public\js\jquery-2.1.0.min.js
```
在app.blade.php引入Select2的css文件和js文件
---
```
C:\laragon\www\laravelapp\resources\views\layouts\app.blade.php

<link rel='stylesheet' href="/css/select2.css" type='text/css' media='all'/>
<script src="/js/jquery-2.1.0.min.js"></script>
<script src="/js/select2.min.js"></script>

articles/create.blade.php文件，在published_at下面添加一个输入表单：

C:\laragon\www\laravelapp\resources\views\articles\form.blade.php

<div class="form-group">
    {!! Form::label('tag_list','选择标签') !!}
    {!! Form::select('tag_list[]',$tags,null,['class'=>'form-control js-example-basic-multiple','multiple'=>'multiple']) !!}
</div>

tag_list[]，如果我们只是使用tag_list,就只能选到一个标签，如果我们需要选择多个，我们需要已数组的形式来储存我们的标签，还有一个就是指定一下'multiple'=>'multiple'，就是开启支持多选模式。然后$tags就是我们需要从数据库获tags表取到得数据，所以自然而然，我们到ArticleController中的create()方法中，稍微修改一下代码：
C:\laragon\www\laravelapp\app\Http\Controllers\ArticlesController.php

use App\Tag;
...
    public function create()
    {
        //return view('articles.create');
        $tags = Tag::lists('name', 'id');
        //为了在界面中显示标签name，id为了在保存文章的时候使用。
        return view('articles.create',compact('tags'));
    }

运行创建文章出错：

Method Illuminate\Database\Query\Builder::lists does not exist.
```
[Laravel 5.3 没有 lists 方法了吗？](https://laravel-china.org/topics/2867/laravel-53-no-lists-method-yet)  
```
从 Laravel 5.3 起，lists 方法会废弃，使用 pluck 方法作为替换：
Model::orderBy('created_at')->pluck('id');
```

```
ArticlesController.php 修改为：
    public function create()
    {
        //return view('articles.create');
        //$tags = Tag::all();
        //$tags = Tag::list('name', 'id');  //lists 在5.3中弃用
        $tags = Tag::orderBy('id')->pluck('name', 'id');
        //为了在界面中显示标签name，id为了在保存文章的时候使用。
        return view('articles.create',compact('tags'));
    }


运行后发表文章选择TAG源码HTML：
<div class="form-group">
    <label for="tag_list">选择标签</label>
    <select class="form-control js-example-basic-multiple" multiple="multiple" name="tag_list[]"><option value="1">Java</option><option value="2">Php</option><option value="3">Python</option><option value="4">C</option><option value="5">C++</option></select>
</div>


这时候我们发现，样式并没有Select2那么好看，那是因为我们还没有初始化Select2，所以我们在create.blade.php写几行简单地js代码：

C:\laragon\www\laravelapp\resources\views\articles\create.blade.php
......
    <script type="text/javascript">
        $(function() {
            $(".js-example-basic-multiple").select2({
                placeholder: "添加标签"
            });
        });
    </script>
@endsection

很完美，我们将整个UI完善得还不错，我们用dd();来看看我们表单提交过来的是什么，在ArticleController中的store()方法中添加一行代码：

dd($request->all());
我们来看看效果：

array:5 [▼
  "_token" => "X9GJVfYmquEQIgK9xZymXOB2sVUSpMq1T945VdEV"
  "title" => "中国人最伟大"
  "content" => "文章内容部分"
  "published_at" => "2018-04-15"
  "tag_list" => array:3 [▼
    0 => "2"
    1 => "3"
    2 => "5"
  ]
]

得tag_list数组，里面的值是标签的id，可以使用laravel提供的attach()来添加标签，attach()接受一个id的数组,稍微来修改一下store()方法：
    public function store(Requests\CreateArticleRequest $request){
        //dd($request->all());
        Article::create($request->all()); //在model中预处理published_at
        return redirect('/articles');
    }
改为：
    public function store(Requests\CreateArticleRequest $request){
        //dd($request->all());
        //Article::create($request->all()); //在model中预处理published_at
        $input = $request->all();
        $article = Article::create($input);
        $article->tags()->attach($request->input('tag_list'));
        return redirect('/articles');
    }

首先将Article::create($input)赋予$article变量(Eloquent对象)，然后使用$article->tags()->attach()来添加标签，并将我们的标签数组传给attach()方法

article_tag表中created_at和updated_at有点问题，我们来修复一下，在Article.php中的tags()方法中：

    public function tags()
    {
        //return $this->belongsToMany('App\Tag');
        return $this->belongsToMany('App\Tag')->withTimestamps();
    }
```
在视图中显示tags
---
```
在articles/index.blade.php中，我们来将文件的标签输出一下：

<h2 class="post-title pad">
<a href="/articles/{{ $article->id }}"> {{ $article->title }}</a>
</h2>
<ul class="post-meta pad group">
<li><i class="fa fa-clock-o"></i>{{ $article->published_at->diffForHumans() }}</li>
@if($article->tags)
    @foreach($article->tags as $tag)
        <li><i class="fa fa-tag"></i>{{ $tag->name }}</li>
    @endforeach
@endif
</ul>
```
时间改为中文
---
```
多少分钟之前都是英文，是因为没有设置Carbon，修复一下，在app/Providers/AppServiceProvider.php中的boot()方法添加下面这一行：
C:\laragon\www\laravelapp\app\Providers\AppServiceProvider.php

\Carbon\Carbon::setLocale('zh');
```





























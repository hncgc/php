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
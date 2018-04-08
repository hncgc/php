PhpStorm
---

[PhpStorm 2017.3.6 (强大的PHP开发环境) 附注册方法](http://www.oyksoft.com/soft/40722.html?pc=1)  
```
phpstorm已经升级到2017.3.6，原注册码失效，2017.3.5注册方法：
注册时选择“License server”输入 
点击“OK”快速激活JetBrains系列产品
直接用浏览器打开 http://idea.lanyus.com/ ，点击页面中的“获得注册码”，然后在注册时切换至Activation Code选项，输入获得的注册码一长串字符串，便可以注册成功了！（推荐用这种方式）
注册码有效期为2017年10月15日至2018年10月14日
使用前请将“0.0.0.0 account.jetbrains.com”添加到hosts文件中
```

[超详细搭建PhpStorm+PhpStudy开发环境](https://blog.csdn.net/u012861467/article/details/54692236)  

[开源社区PhpStorm](https://www.oschina.net/question/tag/phpstorm?nocache=1522600213819)  

[打造漂亮的 PhpStorm 界面](https://laravel-china.org/articles/4172/create-beautiful-phpstorm-interface)  

[jetbrains 系列开发工具 color scheme 配色方案自定义配置](https://blog.csdn.net/baidu_16051437/article/details/51142500)  

[PhpStorm color-scheme配色方案主题](https://github.com/holoto/color-scheme)  

[如何优雅的使用 phpStorm 开发工具](https://lattecake.com/post/20075)  

[超详细搭建PhpStorm+PhpStudy开发环境](https://blog.csdn.net/u012861467/article/details/54692236)  

[优雅地安装、优化64位的PhpStorm，对卡顿问题说再见](http://www.lcgod.com/atc_36)  

[phpstorm 有哪些奇技淫巧？](https://www.zhihu.com/question/29025752)  

[PhpStorm中如何使用database工具，详细操作方法](https://blog.csdn.net/knight_quan/article/details/51983029)  

[PhpStorm中如何使用Xdebug工具，入门级操作方法](https://blog.csdn.net/knight_quan/article/details/51953269)  

[Phpstorm 2017.1+PHPWAMP+Xdebug环境配置以及断点调试](https://blog.csdn.net/WillCold/article/details/68068090)  

[PhpStorm中如何使用FTP功能 详细操作方法](https://blog.csdn.net/knight_quan/article/details/51910102)  

[PhpStorm中如何配置SVN，详细操作方法](https://blog.csdn.net/knight_quan/article/details/51889476)  

[PhpStorm技巧](http://phpstorm.tips/tips)  

[阿北的知识分享](https://nai8.me/)  

------

[phpstorm代码片段使用方法]（https://blog.csdn.net/qq_15766181/article/details/48176845）  

[图解phpstorm常用快捷键]（https://www.cnblogs.com/xp796/p/5718321.html）  
```
#### 查询快捷键
CTRL+N 查找类
CTRL+SHIFT+N 全局搜索文件 ,优先文件名匹配的文件
CTRL+SHIFT+ALT+N 查找php类名/变量名 ,js方法名/变量名, css 选择
CIRL+B 找变量的来源，跳到变量申明处 (CTRL+ 鼠标单击 也可以)
CTRL+ALT+B 找到继承该接口或者父级 的所有子类, 统计所有子类个数
CTRL+SHIFT+B 找变量的类 
CTRL+F 在当前窗口查找文本
CTRL+SHIFT+F 在指定路径查找文本字符
CTRL+R 当前窗口替换文本
CTRL+SHIFT+R 在指定路径替换文本
CTRL+E 最近打开的文件

#### 自动代码
CTRL+J 自动代码提示，自动补全
ALT+回车 导入包,自动修正
CTRL+ALT+L 格式化代码
CTRL+ALT+I 自动缩进
CTRL+ALT+SPACE 类名或接口名提示（与系统冲突） 提示类名关键字 (abstract public ...)
CTRL+P 方法参数提示，显示默认参数
ALT+INSERT 生成代码(如GET,SET方法,构造函数等) , 光标在类中才生效
CTRL+ALT+O 优化导入的类和包 需要配置
CTRL+SHIFT+SPACE 切换窗口
CTRL+SPACE空格 代码自动完成，代码提示,一般与输入法冲突
CTRL+ALT+T 把选中的代码放在TRY{} IF{} ELSE{} 里

#### 复制快捷方式
F5 复制文件/文件夹
CTRL+C 复制
CTRL+V 粘贴
CTRL+X 剪切,删除行
Ctrl + Y 删除行插入符号
CTRL+D 复制行 , 快速分布li标签等
CTRL+SHIFT+V 可以复制多个文本,将前几次复制的文本保存下来了
SHIFT+F2 高亮错误或警告快速定位错误，多个错误循环高亮

#### 本地历史VCS/SVN
Ctrl + K 提交项目VCS
Ctrl + T 更新项目从VCS
Alt + Shift + C 查看项目最近文件版本变化文件 , CTRL+E 只是查看修改过的文件
Alt + ` (table 上面的点) 快速弹出VCS菜单

####其他快捷方式
CTRL+Z 倒退(代码后悔)
CTRL+SHIFT+Z 向前
CTRL+H 显示类层级关系图，继承/实现关系
Ctrl +F12 文件结构弹出 类似 ALT + 7
CTRL+W 块状选中代码，连续按会有其他效果 Ctrl+Shift+W 减少当前选择到以前的状态
CTRL+O 魔术方法, 在php类体中有效
ctrl+shift+i 快速查看变量或方法定义源 , 也可以鼠标按住+CTRL
CTRL+ALT+F12 资源管理器打开文件夹，跳转至当前文件在磁盘上的位置
CTRL+ [] 光标移动到{}[]开头或结尾位置
CTRL+SHIFT+[] 直接选中块代码 = CTRL+W 按好几下
SHIFT+ALT+INSERT 竖编辑模式
CTRL+/ 单行注释/取消注释
CTRL+SHIFT+/ 块状注释/取消块状注释
Ctrl+Shift+U 选中的字符大小写转换
ctrl +
trl + '.': 折叠选中的代码的代码
CTRL+ALT←/→ 返回上次编辑的位置
ALT+←/→ 切换代码视图，标签切换
ALT+↑/↓ 在方法间快速移动定位
Ctrl+Shift+Enter(智能完善代码 如if())
ctrl+shift+up/down (移动行、合并选中行，代码选中区域向上/下移动)
SHIFT+F6 重命名,重构当前区域内变量重命名/重构
不但可以重命名文件名，而且可以命名函数名，函数名可以搜索引用的文件，还可以重命名局部变量。还可以重命名标签名。
alt +'7':显示当前的类/函数结构。类似于eclipse中的outline的效果。试验了一下，要比aptana的给力一些，但还是不能完全显示prototype下面的方法名。
Alt + Shift + I 检查当前文件与当前的配置文件

#### 编辑
Ctrl + Q 快速文档查询
ALT + INSERT 生成的代码...器（getter，setter方法，构造函数）
Ctrl + O 覆盖方法
Ctrl + I 实现方法
Ctrl + J 活动代码提示
Alt + Enter 显示意图的行动和快速修复
Shift + Tab 键缩进/取消缩进选中的行
Ctrl + Shift + J 智能线连接（仅适用于HTML和JavaScript）
Ctrl + Enter 智能线分割（HTML和JavaScript）
Shift + Enter 开始新的生产线
Ctrl + Delete 删除字（word）
Ctrl + Backspace 删除整个字 ,单纯Backspace单个字符删除

#### 运行
Alt + Shift + F10 选择的配置和运行
Ctrl + Shift + X 运行命令行
Alt + Shift + F9 选择配置和调试
Shift + F10 运行
Shift + F9 调试
Ctrl + Shift + F10 运行范围内配置编辑器
Ctrl+Shift+H 方法的层次结构
Ctrl+Alt+H 呼叫层次
CTRL+Q 显示代码注释
ALT+F1 选择当前文件或菜单中的任何视图工具栏
CTRL+UP/DOWN 光标跳转到编辑器显示区第一行或最后一行下
ESC 光标返回编辑框
SHIFT+ESC 光标返回编辑框,关闭无用的窗口
CTRL+F4 关闭当前的编辑器或选项卡
Ctrl + Alt + V引入变量
Ctrl + Alt + F 类似引入变量
Ctrl + Alt + C引入常量
Ctrl + Tab 键切换选项卡和工具窗口
Ctrl + Shift + A 查找快捷键
Alt + ＃[0-9] 打开相应的工具窗口
Ctrl + Shift + F12 切换最大化编辑器
Alt + Shift + F 添加到收藏夹
Ctrl +反引号（`） 快速切换目前的配色/代码方案/快捷键方案/界面方案
Ctrl + Alt + S 打开设置对话框（与QQ冲突）

#### 调试
F8步过
F7步入
Shift + F7智能进入
Shift + F8步骤
ALT + F9运行到光标
Alt + F8计算表达式
F9恢复程序
Ctrl + F8切换断点
Ctrl + Shift + F8查看断点

#### 导航
Shift + Esc键隐藏活动或最后一个激活的窗口
Ctrl + Shift + F4关闭活动运行/消息/ /...选项卡
Ctrl + Shift + Backspace键导航到最后编辑的位置
Ctrl + Alt+B 到实施（S）
Ctrl + Shift+I 打开快速定义查询
Ctrl + U 转到super-method/super-class
Alt + Home 组合显示导航栏

#### 书签
Ctrl + F11切换书签助记符
Ctrl +＃[0-9]转到编号书签
Shift + F11显示书签
Esc键编辑器（从工具窗口）
F1 帮助千万别按,很卡!
F2（Shift+F2） 下/上高亮错误或警告快速定位
F3 向下查找关键字出现位置
F4 查找变量来源
F5 复制文件/文件夹
F6 移动
F11 切换书签
F12 返回到以前的工具窗
```



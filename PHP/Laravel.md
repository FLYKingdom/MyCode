


 [laravel](https://www.golaravel.com/) 
=======

> (Laravel 简洁优雅的PHP开发框架)
  
  [学习路径](https://docs.golaravel.com/docs/4.2/introduction/#where-to-start)：
  
  [安装与配置](#安装配置)->[路由](#路由)->[请求与输入](#请求与输入)->[视图与响应](#视图与响应)
  
  ->[控制器](#控制器)->[配置数据库](#配置数据库)->[查询构造器](#查询构造器)
  
  ->[Eloquent ORM](#Eloquent_ORM)->[身份验证](#身份验证)
  
  ->[Cache](#Cache)->[Session](#Session)->[错误日志](#错误日志)->[单元测试](#单元测试)
  
  #### [安装配置](https://docs.golaravel.com/docs/4.2/quick/#installation)
  
  > 安装4.2:
  
    composer create-project laravel/laravel=4.2 laravelTest --prefer-dist
  
  > 配置：app/conf app.php key（32位）debug（true便于调试 线上配置为false）
        
  > nginx.conf  配置MAMP_VirtualHost_iteration_begin_MAMP 在location/下添加 try_files $uri $uri/ /index.php?$query_string ; 
  
  > 服务器指向路径为/public(内含index.php)
  
  #### [路由](https://docs.golaravel.com/docs/4.2/routing/#route-filters)
  
  > 基本路由 路由参数 路由过滤器 命名路由 路由组 子域名路由 路由前缀 路由与模型绑定 抛出404错误 控制器路由
  
  #### [请求与输入](https://docs.golaravel.com/docs/4.2/requests/)
  
  ##### [IoC 容器](https://docs.golaravel.com/docs/4.2/ioc/) ：设计模式-控制反转
  
  > 解决相互依赖的方法： 闭包回调和自动解析 绑定和注册（单例和已存在实例绑定到容器）
  
  > 注册服务提供器-服务提供器可以注册事件监听器、视图合成器、Artisan命令等等?(服务器用来干什么的)? 
  
  > 容器事件监听 
  
  ##### [请求的生命周期](https://docs.golaravel.com/docs/4.2/lifecycle/#request-lifecycle)：
  
  * 1、客户端请求发送，经网络传输到达服务器处理 传递给index.php文件
  
  * 2、bootstrap/start.php文件创建应用程序application对象并检测环境 
  
  * 3、内部的framework/start.php文件 会配置相关设置并加载服务提供器
  
  * 4、加载应用程序app/start目录下的文件 配置环境参数
  
  * 5、加载app/routes.php文件
  
  * 6、将Request对象发送给应用程序对象，经处理返回Response对象
  
  * 7、将Response对象发送给客户端
  
  ##### [请求与输入](https://docs.golaravel.com/docs/4.2/requests/)
  
  > 基本输入数据 Input::get()等；Cookies 队列等等；form前输入回填；上传文件；请求信息；
  
  #### [视图与响应](https://docs.golaravel.com/docs/4.2/responses/#basic-responses)
  
  > 模版系统：[Blade](https://docs.golaravel.com/docs/4.2/templates/)
  
  > 基本响应-重定向-视图-视图组件-特殊响应-响应宏
  
  #### [控制器](https://docs.golaravel.com/docs/4.2/controllers/#basic-controllers)
  
  > 基本控制器(文件系统/composer.json)-控制器过滤器(请求生命周期阶段处理)-隐式控制器(定义路由)-资源控制器（RESTful风格/Route::resource）-处理缺失的方法
  
  #### [配置数据库](https://docs.golaravel.com/docs/4.2/database/)
  
  > -[数据库基础使用](https://docs.golaravel.com/docs/4.2/database/)（配置/事务/读写链接/日志/多数据库）
  
  > -[查询构造器](https://docs.golaravel.com/docs/4.2/queries)（PDO/查询构造器）
  
  > -[Eloquent ORM](#Eloquent_ORM)(这个东东好多呀/需要单独看基本/高级使用/数据库_模型交互)
  
  > -[结构生成器](https://docs.golaravel.com/docs/4.2/schema/#introduction)（不考虑数据库操作数据库表）
  
  > -[数据迁移和数据填充](https://docs.golaravel.com/docs/4.2/migrations/)(配合结构生成器管理应用程序结构/数据填充生成测试数据)
  
  > -[Redis配置](https://docs.golaravel.com/docs/4.2/redis/)（框架配置、使用和流水线）
  
  #### 查询构造器
  
  something over here！
  
  #### [Eloquent_ORM](https://docs.golaravel.com/docs/4.2/eloquent/#query-scopes)
  
  something over here！
  
  #### [安全](https://docs.golaravel.com/docs/4.2/security/)
  
  > 设定/存储密码 设置auth.php Hash类加密算法
  
  > 用户认证 登录认证以及认证信息、状态处理
  
  > 保护路由 设置认证用户可访问路径链接
  
  > CSRF保护 防止跨站攻击 表单验证
  
  > HTTP简易认证 可设置简易快速认证不需要登录页面/可设置无状态HTTP简易过滤无session或cookie
  
  > 忘记密码和重设密码（快速集成后台认证的功能）
  
  > 加密Crypt::encrypt decrypt（设置随机字符串key app.php）
  
  > 认证驱动 （默认database和eloquent、额外 [认证扩充文件](https://docs.golaravel.com/docs/4.2/extending/#authentication))
  
  说明：users表中的remember_token用于保留用户认证身份/用户sessionID认证后自动重新产生
  
  #### [Cache](https://docs.golaravel.com/docs/4.2/cache/)
  
  > 配置Cache.php
  
  > 缓存使用 Cache::put()...等等
  
  > 缓存标签 Cache::tags() /递增递减
  
  > 数据库缓存 使用 Schema 声明
  
  * [Memcached](#Memcached)
  
  * [Redis](#Redis)
  
  #### [Session](https://docs.golaravel.com/docs/4.2/session/)
  
  > 配置session.php （flash键值关键字避免使用）
  
  > Session使用 Session::put()
  
  > 快闪数据（Flash Data）
  
  > [Session 驱动](https://docs.golaravel.com/docs/4.2/session/#session-drivers)
  
  #### [错误与日志](https://docs.golaravel.com/docs/4.2/errors/)
  
  > 配置文件 (start/global.php文件/[Monolog](https://github.com/seldaek/monolog)日志库 日志等级)
  
  > 错误处理 基本的处理程序和设定处理程序监听不同类型的处理
  
  > HTTP 异常处理 not found 404 未授权401 代码异常500
  
  > 日志 (RFC 5424log Protocol级别:debug, info, notice, warning, error, critical, and alert)(注册日志监听)
 
  #### [单元测试](https://docs.golaravel.com/docs/4.2/testing/)
  
  > Laravel单元测试 （PHPUnit、Symfony HttpKernel、DomCrawler、BrowserKit组件可模拟网页浏览器/app/tests文件）
  
  > 定义与执行 创建测试用例
  
  > 测试环境 默认不操作session cache需要设置新的测试环境并初始化数组
  
  > 测试中调用路由call callSecure获取view- original、 获取响应字符串getContent
  
  > DOM Crawller 通过路由获取实例 检查内容isOk filter方法
  
  > 模拟 Facades（设计模式）？？？
  
  > 框架Assertions 多个Assert组合assertResponseOk assertResponseStatus等
  
  > 辅助方法 快捷使用方法be seed等
  
  > 重置额外绑定 refreshApplication
  
  #### [SSH](https://docs.golaravel.com/docs/4.2/ssh/)
  
  ##### [SSH基础学习](基于应用层的安全协议，用于验证登录 适用UNIX大部分平台)
  
  > 配置文件（config/remote.php文件配置SSH key或密码）
  
  > 基本用法 SSH::run方法 在服务器执行git命令、run闭包里echo捕捉输出
  
  > 任务 define一组命令到任务 task执行
  
  > SFTP下载/SFTP上传 下载文件get/getString、put/putString
  
  > 编辑远程日志 tail追加日志内容 使用artisan命令
  
  > [Envoy](https://docs.golaravel.com/docs/4.2/ssh/#envoy-task-runner) 任务执行 简介轻量的语法执行服务器操作 [Blade](https://docs.golaravel.com/docs/4.2/templates/#blade-templating)风格语法
  
  ### [模版](https://docs.golaravel.com/docs/4.2/templates/#blade-templating)
  
  > Blade模版 定义布局和使用
  
  > 控制结构 @if @endif标签 循环标签
  
  > 扩展Blade 定义自定义控制结构
  
  ### [Facades](https://docs.golaravel.com/docs/4.2/facades/)
  
  > Facades设置模式 静态接口访问注册到loc容器中的类
  
  > 定义facade类 需要实现getFacadeAccesor方法 
  
  > 使用 Cache::get('key')
  
  > 自定义facade （～loc绑定～创建facade类～别名配置）
  
  ### [框架拓展](https://docs.golaravel.com/docs/4.2/extending/)
  
  > 扩展方法 管理者loc容器绑定和工厂模式Manager
  
  > Cache Manger拓展建立自定义缓存驱动(用服务提供者来组织框架扩展是个组织您的代码的好方法)
  
  > Session 需要在start之前扩展 使用服务提供者register方法中 并设置app的providers数组
  
  > 基于loc的扩展 待做 app.php文件中 providers服务提供者清单学习
  
  > 认证 请求 扩展 请求和Session扩展的不同
  
  ### [事件](https://docs.golaravel.com/docs/4.2/events/)
  
  > 基本使用 订阅Event::listen 触发Event::fire
  
  > 通配符监听 foo.* firing方法
  
  > 类作为监听者 handle方法 ‘LoginHandler@onLogin’和‘LoginHandler’
  
  > 事件队列 Event::queue Event::flush('foo')
  
  > 事件订阅者 可以订阅多个事件 subscribe方法
  
  ### [队列](https://docs.golaravel.com/docs/4.2/queues/)
  
  > 设置 config/queue.php配置不同的队列服务链接/队列服务依赖
  
  > 队列闭包 （要让一个组件变量可以在队列闭包中可以使用我们会通过 use 命令，试着传送主键及重复使用的相关模组在您的队列工作中，这可以避免其他的序列化行为）
  
  > 执行队列监听
  
  > 常驻队列处理器
  
  > 推送队列
  
  >  已失败的工作
  
  ### [验证](https://docs.golaravel.com/docs/4.2/validation/#basic-usage)
  
  > 使用Validation简单的数据正确性验证和验证时的错误信息
  
  > 验证错误信息
  
  > 错误信息回传视图 
  
  > 可用验证规则表 Accepted Active URL等
  
  > 添加条件验证规则
  
  > 自定义错误信息
  
  > 自定义验证规则
  
  ### 其他
  
  > [辅助方法](https://docs.golaravel.com/docs/4.2/helpers/)（laravel封装的方法） [计费](https://docs.golaravel.com/docs/4.2/billing/) [表单与HTML](https://docs.golaravel.com/docs/4.2/html/) [本地化](https://docs.golaravel.com/docs/4.2/localization/) [邮件-SwiftMailer](https://docs.golaravel.com/docs/4.2/mail/) [拓展包](https://docs.golaravel.com/docs/4.2/packages/)
  
  拓展阅读：[Nginx学习文档](http://www.nginx.cn/doc/)  Apache .htaccess
  
  拓展关键字：[控制反转](https://baike.baidu.com/item/%E6%8E%A7%E5%88%B6%E5%8F%8D%E8%BD%AC/1158025?fr=aladdin#3) XML Java 反射机制 负载均衡 虚拟机 PHP包发布管理工具([Packagist](http://packagist.org/)、[Composer](http://getcomposer.org/))




#### 视图相关 V170525

1. 视图目录：以控制器名命名

* 视图文件：以控制器方法名命名，``base.html``文件为主继承文件，``base_*.html`` 为辅继承文件，``*``为功能单个单词命名；``mod_*.html``为模块视图引用文件; [更多请参考TP文档](http://www.kancloud.cn/manual/thinkphp5/118003)

* 提倡重复使用的东西一定要分离出来模块或继承文件，已经有了的提倡拿来用，或跟作者协商迭代，而不是复制粘贴，增加将来的维护成本。

* 继承``base.html,base_*.html``文件必须实现的block有 ``author,title,keywords,discription``

* 开源的静态资源提倡引入CDN服务器地址，自主应用最多允许引入2个 css文件和2个js文件，及 global_*.css、page_*.css，common.js、*_*.js

* 当修改和删一个模块的时候，一定同时将CSS一同更新

* iconfont 项目上的字体使用原则是：首先找已经项目中已有的图标，如果确实没有合适的再搜索加入到项目，一旦加入到项目必须使用，否则在确定没有人使用的情况下删除。，字体命名ff(font-family)的缩写，使用图标需添加 ff ff-* 类

* 登陆状态session(SESSION_NAME)来获取 已登录用户信息或其他状态界面开发

* style和link元素坚决不允许在body里出现，应在head内部

* html 的lang值必须是zh-hans

* 渲染模式必须<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">

* img必须具备alt文本描述，src路径不得使用特殊字符

* 非闭合标签必须成对且闭合

* 必须通过 https://validator.w3.org/unicorn/ 验证

* 坚决不允许自己乱填不规范属性到标签，拿不准可查询文档或用data-xxx代替

* 上传的附件必须经过重命名分目录归类存储OSS

* 属性之间必须用单个空格隔开

* ID每个页面必须保持唯一性

* width，height属性坚决不能使用小数点，如需要使用小数点请CSS控制

* 如果属性中包含双引号需转义

* coding过程中不对齐的利用IDE格式化快捷键或插件格式化

* 留空行是有意义的有区分之意，不要一句一留空行

* 当定义或迭代了别的coding后，善用注释留下作者，以便减少后面阅读人的思考时间

* 测试首先是自测，其次是大家测，自己收集建议

* 开发过程中应对（IE9~11\chrome\firefox）做好兼容性调试，切勿开发完在进行调试

* 对于不想暴露出来的团队内部注释请在视图中 ``{/* hello */}`` 用这种方式注释

## 模型层相关 V170525
1. 文件名首字母大写，与相关英文主表命名
2. 方法名驼峰形式命名，动词开头比如 `` getArticleList addArticle ``
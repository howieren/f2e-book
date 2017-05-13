## 视图开发规范

>1. 视图目录：以控制器名命名

>* 视图文件：以控制器方法名命名，``base.html``文件为主继承文件，``base_*.html`` 为辅继承文件，``*``为功能单个单词命名；``mod_*.html``为模块视图引用文件; [更多请参考TP文档](http://www.kancloud.cn/manual/thinkphp5/118003)

>* 提倡重复使用的东西一定要分离出来模块或继承文件，已经有了的提倡拿来用，或跟作者协商迭代，而不是复制粘贴，增加将来的维护成本。

>* 继承``base.html,base_*.html``文件必须实现的block有 ``author,title,keywords,discription``

>* 开源的静态资源提倡引入CDN服务器地址，自主应用最多允许引入2个 css文件和2个js文件，及 global_*.css、page_*.css，common.js、*_*.js

>* 当修改和删一个模块的时候，一定同时将CSS一同更新

>* iconfont 项目上的字体使用原则是：首先找已经项目中已有的图标，如果确实没有合适的再搜索加入到项目，一旦加入到项目必须使用，否则在确定没有人使用的情况下删除。，字体命名ff(font-family)的缩写，使用图标需添加 ff ff-* 类

>* 登陆状态session(SESSION_NAME)来获取 已登录用户信息或其他状态界面开发

me@renhaiwei.cn 2017-03-09

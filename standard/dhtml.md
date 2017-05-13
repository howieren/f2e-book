##第一章：本规范概述

    滨州网是一个非常庞大的互联网生态系统，不同于以往简单的企业站，滨州网生态系统包含的功能众多，相应的展示样式和行为也会变得非常之大。为了仍能有良好用户体验，就要求所有前端人员在开发过程中，要做到代码规范、简洁明了、结构表现和行为分离，样式模块化拼接，兼容性优良，尽可能减少服务器负载，保证最快的解析速度。

    鉴于以上，本规范主要实现的目的：代码一致性和最佳用户体验。通过代码风格的一致性，提高团队协作效率, 便于后台人员添加功能及前端后期优化维护。同时遵守最佳用户体验，确保页面性能得到最佳优化和高效的代码。

    本规范是在开发中积累下来的经验和参考其它规范/指南制定的，它只是起指导作用，不是最后结论，它会随着时间而变化，本文档如有不对或者不合适的地方请及时提出, 经讨论决定后可以更改此文档。但，当本规范文档一经确认, 前端所有开发人员必须按本文档规范进行前台页面开发。

##第二章：执行本规范时建议的流程
    建议使用D(esign)C(oding)D(ebug)V(alidate)R(oundup)，即DCDVR的流程。首先对(X)HTML模板进行规划，然后才开始编码，编码的同时进行Debug，Validate和代码片断的总结，而不是在所有模板都完成后才进行这三个步骤。

##第三章：文件目录开发规范

####静态文件引用原则

· 能用CSS代替的不用图片，必要用图片时将图片上传至OSS相关版本目录
· 禁止和逐渐淘汰程序服务器存放静态文件的做法
· 常规公共静态资源应在项目模板替换变量定义好引用常量
· 尽可能在开放可信任CND服务器上找到的资源引用

##第四章：HTML开发规范

一般规则
· 所有非空元素必须有闭合tag，如 <p>这是一个段落</p>
· 元素名称和属性名称全部小写
· 属性值必须使用双引号包围
· 在某些脚本必要的地方才使用 name 属性，否则一律使用id属性
· 在属性值和元素内容出现的地方，如果有字符 ", &, <, > ，那么应当分别使用 &quot;, &amp;, &lt;, &gt;
样式分离规则
· 样式统一在 head 元素中使用 link 元素引用，不得在 head 元素以外的地方添加样式，不得在元素中使用 style 属性，不应当在元素中使用其他样式属性，如 background 等，不应当使用具有样式特征的元素，如 br, hr 等，其中br元素代表语气停顿，通常用于诗句，但这并不表示任何需要换行的地方就应当使用br元素。
· 可以将样式统一写在 <head> 元素中的 <style> 元素中，但必须保证该样式是当前页面的唯一样式，如果该样式被其他页面同时使用，那么应当考虑抽离出来形成外部文件。
脚本分离规则
· 脚本仅能出现在 head 元素内和 body 元素闭合tag即 </body> 前。不得在任何元素中使用event相关属性，如 onclick 等。
内容模型
· 本规范的内容模型应当遵循HTML 4.01 Strict提供的内容模型，其中的主要规则总结如下。
· 能够包含块级元素和行级元素的元素有 fieldset, div, li, object
· 只能包含行级元素的元素有 h1 - h6, pre, p, address, 其他行级元素如 a 等
· 只能包含块级元素的元素有 noscript, blockquote, form
· 其余元素只能包含一些特定的元素，包括 table, ul, ol, dl, select
TITLE元素
· head 元素中必须包含 title 元素
META元素
· 必须包含 <meta charset="UTF-8"> ，应当使用UTF-8编码
· 必须作为 head 元素的第一个子元素出现
TABLE元素
· 必须显示包含 tbody 元素
A元素
· 不应当使用 name 属性，而用 id 替代
· 当 input 元素的顺序由于样式需要调整时，应当指定 tabindex 属性
· 关键的链接处应当指定 accesskey 属性
IMG元素
· 必须指定 alt 属性且带上src属性
FORM元素
· form中严禁再嵌套form元素
INPUT元素
· 一个form有且只有一个type="submit"的input按钮
· 禁止submit上绑定onclick等事件使用submit方法提交表单
· 当 input 元素的顺序由于样式需要调整时，应当指定 tabindex 属性
· 关键的控件处应当指定 accesskey 属性 可参考的accesskey标准
LABEL元素
· 与控件对应的文本必须使用 label 元素标记，且使用 for 属性指向该控件 id
IFRAME元素
· 尽量不要使用iframe元素
· frame、iframe、img、embed标签必须带上src属性
FLASH元素
· 全页面禁止FLASH
HTML注释
需要注释的内容有
· 文档的作者
· 在跨越很多很多行的包裹元素的闭合标签位置添加 <!--End ElementId-->
HTML书写规范
· DOCTYPE声明和html元素之前不用空格，其余元素均根据父元素的位置缩进一个tab的距离，tab距离可以是4个空格或8个空格。
HTML常见错误举例
· 没有重复ID项，没有名为submit等保留字的ID的元素或者name的元素
代码注解
```
<!DOCTYPE html>
<!-- HTML5 doctype 标准模式（standard mode）的声明，这样能够确保在每个浏览器中拥有一致的展现-->
<html lang="zh-CN">
<!-- 语言属性 有助于语音合成工具确定其所应该采用的发音，有助于翻译工具确定其翻译时所应遵守的规则等等 -->
<head>
    <!-- 字符编码 通过明确声明字符编码，能够确保浏览器快速并容易的判断页面内容的渲染方式 -->
    <meta charset="UTF-8">
    <!-- IE 支持通过特定的 <meta> 标签来确定绘制当前页面所应该采用的 IE 版本。
    除非有强烈的特殊需求，否则最好是设置为 edge mode，从而通知 IE 采用其所支持的最新的模式 -->
    <meta http-equiv="X-UA-Compatible" content="IE=Edge">
    <title>Page title</title>
    <!-- External CSS 根据 HTML5 规范，在引入 CSS 文件时一般不需要指定 type 属性，因为 text/css 是它的默认值 -->
    <link rel="stylesheet" href="code-guide.css">
    <!-- In-document CSS -->
    <style>
    /* ... */
    </style>
    <!-- JavaScript 根据 HTML5 规范，在引入 JavaScript 文件时一般不需要指定 type 属性，因为 text/javascript 是它的默认值 -->
    <script src="code-guide.js"></script>
</head>
<body>
    <!-- 属性顺序 HTML 属性应当按照以下给出的顺序依次排列，确保代码的易读性。
      class
      id, name
      data-*
      src, for, type, href
      title, alt
      aria-*, role
    class 用于标识高度可复用组件，因此应该排在首位。id 用于标识具体组件，应当谨慎使用（例如，页面内的书签），因此排在第二位 -->
    <a class="..." id="..." data-modal="toggle" href="#">
    Example link
</a>
    <input class="form-control" type="text">
    <img src="..." alt="...">
    <!-- 布尔（boolean）型属性 不用赋值 元素的布尔型属性如果有值，就是 true，如果没有值，就是 false -->
    <select>
        <option value="1" selected>1</option>
    </select>
    <!-- JavaScript 放在 body 底部加载可增快页面渲染速度 -->
    <script src="code-guide.js"></script>
</body>
</html>
```

##第五章：CSS开发规范
CSS文件结构设计
CSS文件结构
alice.css（所有项目共用样式）
项目css（文件名为项目名称，如 wow）
          frame（可以简写为f，全站共用样式文件）
                    wow.css
          global（可以简写为g，全站下各子站共用样式文件）
                    home.css
                    account.css
          page（可以简写为p，页面唯一样式文件）
                    home-index.css
                    account-index.css
          skin（可以简写为s，换肤样式文件）
                    skinname.css
•	frame下CSS文件应当使用项目名
•	global下CSS文件使用子站名称
•	page下CSS文件使用子站名-页面名.css的形式
•	该文件结构统一在页面中使用 link 元素引入，不得使用 @import 语句引入外部 CSS
CSS文件注释
•	注释应当使用/*-- --*/的形式
•	可重用的组件使用注释标记出来:
/*-- Module ... --*/
/*-- End Module ... --*/
CSS文件编码
•	文件编码必须使用utf-8，请注意编辑器中的设置
CSS书写规范
•	结构应当符合以下格式，即使声明块中只有一条声明语句也应当如此
body {
        font-size: 0.8em;
        color: red;
}
•	声明块之间应空行
•	声明块内声明语句必须缩进一个tab距离，tab可以是4个或者8个空格
•	在写组件样式时，有父子元素关系的样式可以采用进一步缩进体现，如
ul.nav li {
        float: left;
}

        /*-- 下面的链接是上面的子元素，可以在这里缩进一个tab，显示上下元素的关系 --*/
        ul.nav li a{
                color: red;
                padding: 0 20px;

        }
· 父子之间的关系必须>进行选择，尽可能的避免空格泛选择；
CSS挂钩器的命名习惯
•	以下为CSS挂钩器的关键字，一般CSS挂钩器可以直接使用关键字，也可以使用 关键字 - 语义描述 的形式。如当页面中出现多个侧栏时可以根据语义将不同侧栏命名为 aside-ad 和 aside-nav 分别表示广告侧栏和导航侧栏。有时在语义描述也一致的情况下，可以使用序列号来区分。如 aside-ad-1 和 aside-ad-2。
•	统一使用class，不要使用id
页面结构
•	页头：header
•	侧栏：aside
•	导航：nav
•	子导航：subnav
•	菜单：menu
•	子菜单：submenu
•	页面主体：main
•	页脚：footer
•	容器：wrap
常用全局内容
•	当前导航区域：current
•	列表第一项：first
•	列表最后项：last
•	标签页：tab
•	按钮：btn
•	当前的：current
•	面包屑：breadcrumb
•	提示：tip
•	标志：logo
•	广告：banner
•	版权：copyright
•	搜索：search
•	注意内容：note
•	栏目标题：title
常用页面内容
•	新闻：news
•	登陆：login
•	热点：hot
•	下载：download
•	文章：article
•	服务：service
•	指南：guide
•	注册：regsiter
•	投票：vote
•	合作伙伴：partner
•	加入：joinus
•	状态：status

第六章：JavaScript编码规范

本规范概述
制订此规范的初衷是让所有的代码都变成他人容易阅读,并利于维护的。

命名规则
•	常量及全局变量采用全部大写的形式.
•	变量的命名使用骆驼命名法，例如：
strParsor. maxLength
•	类的命名使用骆驼命名法,其中首字母大写.
AccountInfo, EventHandler
•	方法的命令必须为动词或者是动词短语：
obj.getSomeValue()
•	私有类的成员变量命名前面加下划线（_）。例如：
var MyClass = function(){
  var _buffer;
  this.doSomething = function(){
  };
}
this._somePrivateVariable = statement;
•	前缀为 "is" 的变量应该为布尔值，同理 "has";
•	术语 "initialize" 或者 "init" 作为变量名应为初始化方法;
•	迭代临时变量建议使用 "i", "j", "k" （依次类推）等名称;
•	异常处理类建议在变量名称后加上 "Exception" 或者 "Error";

缩进
采用 TAB 键缩进, 统一为4个字符,
function demo(param){
    var a1 = 1
    …
}
此规则亦适用于函数的参数：
var o = someObject.get(
    Expression1,
    Expression2,
    Expression3
);
注意:
- 变量必须在声明初始化以后才能使用，即便是 NULL 类型;
- 变量名请勿使用系统保留关键字;
- 变量应该尽量保持最小的生存周期,及时销毁防止内存泄露;
- 浮点变量必须指明小数点后一位（即使是 0）;
- 浮点变量必须指明实部，即使为零（使用 0. 开头）。

代码块
普通代码段：
while (!isDone){
doSomething();
isDone = moreToDo();
}
IF 语句：
if (someCondition){
statements;
} else if (someOtherCondition){
statements;
} else {
statements;
}
FOR 语句：
for (initialization; condition; update){
statements;
}
WHILE 语句：
while (!isDone) {
doSomething();
isDone = moreToDo();
}
DO ... WHILE 语句：
do {
statements;
} while (condition);
SWITCH 语句：
switch (condition) {
case ABC:
statements;
break;
default:
statements;
break;
}
TRY ... CATCH 语句 ：
try {
statements;
} catch(e) {
statements;
} finally {
statements;
}
单行的 IF，WHILE 或者 FOR 语句需加入括号 ：
if (condition){ statement; }
while (condition){ statement; }
for (intialization; condition; update){ statement;}
单行的 IF – ELSE 允许不加括号:
if(condition)
Statement;
else
Statement;


空格
•	操作符使用空格隔开（包括三元操作符）,如:
var x = a – b;
var y = result == true ? 1 : 0;
•	逗号（,)与for循环中的封号(;)后添加空格。例如:
var test = Array(), test2;
for(i = 0; i < 100; i++){
    Statements;
}
•	冒号（:)后添加空格
•	逻辑块之间以空行隔开

注释
•	保持良好的注释习惯。
•	类/函数/方法前需添加注释,并注明参数类型,返回值回类型。
例如,
/**
 * 金额大小写转换函数
 * @param Int {number} 数字金额
 * @param Num {number} 数字
 * @return String 大写金额
 */

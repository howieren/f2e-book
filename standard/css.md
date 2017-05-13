##结构目录：

1. 重定义浏览器默认样式
* 全局常用 CSS 样式
* 表单及表单元素
* 页面布局以及通用的区块样式
* 列表样式
* 其他特定功能块
* 拖拽及页面 DIY
*  其他页面专用样式参见 页面样式.css

----------------------------------
CSS 样式模块的格式示例：

    Name:           模块名称
    Level:          级别（Global, Channel, Function）
    Dependent:      依赖关系，该模块必须依赖于何种模块
    Sample:         用法示例，或指出改模块所作用的直接页面
    Explain:        附加说明
    Author:         创建者 日期(两位数年月日时)
    Last Modify:    最终修改者 日期(两位数年月日时)

----------------------------------

CSS 写作注意事项：
    1. 属性写在一行内，属性之间、属性名和值之间以及属性与“{}”之间须有空格，例如：.class { width: 400px; height: 300px; }
    2. 属性的书写顺序：
        2.1. 按照元素模型由外及内，由整体到细节书写，大致分为五组：
            位置：position,left,right,float
            盒模型属性：display,margin,padding,width,height
            边框与背景：border,background
            段落与文本：line-height,text-indent,font,color,text-decoration,...
            其他属性：overflow,cursor,visibility,...
        2.2. 针对特殊浏览器的属性，应写在标准属性之前，例如：-webkit-box-shadow:; -moz-box-shadow:; box-shaow:;
    3. 谨慎添加新的选择符规则，尤其不可滥用 id，尽可能继承和复用已有样式
    4. 选择符、属性、值均用小写（格式的颜色值除外），缩写的选择符名称须说明缩写前的全称，例如 .cl -> Clearfix
    5. 避免使用各种 CSS Hack，如需对 IE 进行特殊定义，请参阅下节“关于 CSS Hack 的说明”
    6. 勿使用冗余低效的 CSS 写法，例如：
        ul li a span { ... }
    7. 慎用 !important
    8. 建议使用在 class/id 名称中的词语
        6.1. 表示状态：a->active
        6.2. 表示结构：h->header,c->content,f->footer
        6.3. 表示区域：mn->main,sd->side,nv-navigation,mu->menu
        6.4. 表示样式：l-list,tab,p_pop
    9. 开发过程中的未定事项，须用 [!] 标出，以便于后续讨论整理

## HTML开发规范 V170525

1. 元素名称和属性名称全部小写

* 属性值必须使用双引号包围

* 在某些脚本必要的地方才使用 name 属性，否则一律使用id属性

* 在属性值和元素内容出现的地方，如果有字符 ``", &, <, > ``，那么应当分别使用 ``&quot;, &amp;, &lt;, &gt``;


## 样式分离规则 V170525

1. 样式统一在 head 元素中使用 link 元素引用，不得在 head 元素以外的地方添加样式，不得在元素中使用 style 属性，不应当在元素中使用其他样式属性，如 background 等，不应当使用具有样式特征的元素，如 br, hr 等，其中br元素代表语气停顿，通常用于诗句，但这并不表示任何需要换行的地方就应当使用br元素。

* 可以将样式统一写在 ``<head>`` 元素中的 ``<style>`` 元素中，但必须保证该样式是当前页面的唯一样式，如果该样式被其他页面同时使用，那么应当考虑抽离出来形成外部文件。


## 脚本分离规则 V170525

1. 脚本仅能出现在 head 元素内和 body 元素闭合tag即 ``</body>`` 前。不得在任何元素中使用event相关属性，如 onclick 等。


## 内容模型 V170525

1. 本规范的内容模型应当遵循HTML 4.01 Strict提供的内容模型，其中的主要规则总结如下。

* 能够包含块级元素和行级元素的元素有 fieldset, div, li, object

* 只能包含行级元素的元素有 h1 - h6, pre, p, address, 其他行级元素如 a 等

* 只能包含块级元素的元素有 noscript, blockquote, form

* 其余元素只能包含一些特定的元素，包括 table, ul, ol, dl, select TITLE元素

* head 元素中必须包含 title 元素

* 必须包含 ``<meta charset="UTF-8">`` ，应当使用UTF-8编码，必须作为 head 元素的第一个子元素出现

* 必须显示包含 tbody 元素

* 不应当使用 name 属性，而用 id 替代

* 当 input 元素的顺序由于样式需要调整时，应当指定 tabindex 属性

* 关键的链接处应当指定 accesskey 属性

* 必须指定 alt 属性且带上src属性

* form中严禁再嵌套form元素

* 一个form有且只有一个type="submit"的input按钮

* 禁止submit上绑定onclick等事件使用submit方法提交表单

* 当 input 元素的顺序由于样式需要调整时，应当指定 tabindex 属性

* 关键的控件处应当指定 accesskey 属性 可参考的accesskey标准

* 与控件对应的文本必须使用 label 元素标记，且使用 for 属性指向该控件 id

* 尽量不要使用iframe元素

* frame、iframe、img、embed标签必须带上src属性

* 全页面禁止FLASH

* 每页应有文档的作者

* 在跨越很多很多行的包裹元素的闭合标签位置添加 ``<!--End ElementId-->``

* DOCTYPE声明和html元素之前不用空格，其余元素均根据父元素的位置缩进一个tab的距离，tab距离可以是4个空格或8个空格。

* 没有重复ID项，没有名为submit等保留字的ID的元素或者name的元素

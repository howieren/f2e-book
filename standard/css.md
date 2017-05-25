## CSS开发规范 V1.2

1. 该文件结构统一在页面中使用 link 元素引入，不得使用 @import 语句引入外部 CSS

* 注释应当使用/*-- --*/的形式

* 可重用的组件使用注释标记出来:``/*-- Module ... --*/ /*-- End Module ... --*/``

* 文件编码必须使用utf-8，请注意编辑器中的设置

* 结构应当符合以下格式，即使声明块中只有一条声明语句也应当如此```
body {
  font-size: 0.8em;
  color: red;
}
```

* 声明块之间应空行

* 声明块内声明语句必须缩进一个tab距离，tab可以是4个或者8个空格
* 在写组件样式时，有父子元素关系的样式可以采用进一步缩进体现，如

```
ul.nav li {
  float: left;
}
	/*-- 下面的链接是上面的子元素，可以在这里缩进一个tab，显示上下元素的关系 --*/
	ul.nav li a{
	        color: red;
	        padding: 0 20px;

	}
```

* 父子之间的关系必须>进行选择，尽可能的避免空格泛选择；

## CSS挂钩器的命名习惯 V1.2

1. 以下为CSS挂钩器的关键字，一般CSS挂钩器可以直接使用关键字，也可以使用 关键字 - 语义描述 的形式。如当页面中出现多个侧栏时可以根据语义将不同侧栏命名为 aside-ad 和 aside-nav 分别表示广告侧栏和导航侧栏。有时在语义描述也一致的情况下，可以使用序列号来区分。如 aside-ad-1 和 aside-ad-2。

* 统一使用class，不要使用id

## 页面结构
1. 页头：header
* 侧栏：aside
* 导航：nav
* 子导航：subnav
* 菜单：menu
* 子菜单：submenu
* 页面主体：main
* 页脚：footer
* 容器：wrap
常用全局内容
* 当前导航区域：current
* 列表第一项：first
* 列表最后项：last
* 标签页：tab
* 按钮：btn
* 当前的：current
* 面包屑：breadcrumb
* 提示：tip
* 标志：logo
* 广告：banner
* 版权：copyright
* 搜索：search
* 注意内容：note
* 栏目标题：title
常用页面内容
* 新闻：news
* 登陆：login
* 热点：hot
* 下载：download
* 文章：article
* 服务：service
* 指南：guide
* 注册：regsiter
* 投票：vote
* 合作伙伴：partner
* 加入：joinus
* 状态：status

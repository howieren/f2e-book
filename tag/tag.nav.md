update 2017-09-07 14:45:17
## Nav标签（关于导航和菜单的标签）

**shortcut：** 获得快捷方式列表标签。可用属性：\*name，\*type（属性是类型解释：1.内容 2.行业 3.服务 4.地区），size，page。栗子：

```
{Nav:shortcut name="nav" type="1" size="10" page="1"}
  {:dump($nav)}
{/Nav:shortcut}
```

**leftnav：** 获得首页左侧导航标签。可用属性：\*name 栗子：

```
{Nav:leftnav name="nav"}
  {:dump($nav)}
{/Nav:leftnav}
```

**tags：** 获得某个领域的标签作为nav。可用属性：\*name，\*field (属性是类型解释：1.个人号 2.滨州号 3.部门号 4.应用号 5.地区号 6.滨州圈 7.生活服务号 8.文章 9.政务服务 10.商务服务 11.栏目)
栗子：

```
{Nav:tags name="nav" field="1"}
  {:dump($nav)}
{/Nav:tags}
```

**headnav：** 取得某个应用号/滨州号 栏目导航标签。可用属性：\*name，\*uid

栗子：

```
{Nav:headnav name="items" uid="189" /}
  {:dump($items)}
```

* **childnav** 根据父标签id获取子标签列表标签。可用属性：\*name，\*tid

**栗子：**

```
{Nav:childnav name="items" tid="287" /}
  {:dump($items)}
```

* **chilidcategory** 根据weibaid获取子栏目。可用属性：\*name，\*uid（用户id） category(栏目id)

**栗子：**

```
{Nav:childcategory name="item" uid="247" category="899"}
  {:dump($item)}
{/Nav:childcategory}
```

* **categoryinfo** 根据栏目id获取栏目信息。可用属性：category
**栗子：**

```
 {Nav:categoryinfo name="item" category="412"/}
 {:dump($item);}

```

* **column** 栏目列表标签。可用属性：name
**栗子：**

```
{Nav:column name="item"/}
  {:dump($item)}
```

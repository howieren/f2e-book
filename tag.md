## 前端视图开发标签使用说明
### 属性解释
* ``*`` 下面带*必填属性，不带*的是可选属性
* ``name`` 获得数据源的名称，仅对本次标签取值使用生效 如：``name="item"``
* ``size`` 数据条数 如：``size="10"``
* ``page`` 页码 如：``page="1"``
* ``href`` 一个相对或绝对url 如：``href="//m.tb.cn/s.css"``
* ``uid`` 用户ID 如：``uid="291"``
* ``category`` 栏目ID 如：``category="257"``
* ``recommend`` 是否推荐到首页 如：``recommend="1"``
* ``hot`` 是否热门 如：``hot="1"``
* ``top`` 是否置顶 如：``top="1"``
* ``date`` 制定一个日期 如：``date="01-03"``
* ``total`` 是否返回总数，如果返回总数将进行二次循环才可以 如：``total="1"``
* ``offset`` 从哪一条数据开始取 如：``offset="0"``
* ``pid`` 文章id
* ``fid`` 被关注人号圈id

### 常用号UID速查
滨州图片 ``251``，专题报道（原滨州发布）``14055``，滨州视频 ``194``，滨州文化 ``176``，滨州亲子 ``247``，滨州教育 ``190``，滨州体育 ``177``，滨州健康 ``219``，滨州旅游 ``178``，滨州直播 ``204``，微直播 ``19560``，滨州特惠 ``188``，区域经济 ``648``，滨州财经 ``174``，农家发布 ``168``，滨州汽车 ``171``，专题 ``201``，滨州法制 ``211``，滨州图库 ``173``，滨州历史 ``244``，滨州人物 ``248``，滨州时评 ``245``，校园足球 ``189``，滨州智库 ``131``，社会民生 ``1844``，滨州政务 ``128``，滨州日报 ``246``，滨州快讯 ``186``，滨州头条 ``184``，天下博览 ``23466``，人事动向 ``23383``


### Nav标签（关于导航和菜单的标签）
* **shortcut：** 获得快捷方式列表标签。可用属性：\*name，\*type（属性是类型解释：1.内容 2.行业 3.服务 4.地区），size，page。**栗子：**

```
{Nav:shortcut name="nav" type="1" size="10" page="1"}
  {:dump($nav)}
{/Nav:shortcut}
```

* **leftnav：** 获得首页左侧导航标签。可用属性：\*name **栗子：**

```
{Nav:leftnav name="nav"}
  {:dump($nav)}
{/Nav:leftnav}
```

* **tags：** 获得某个领域的标签作为nav。可用属性：\*name，\*field (属性是类型解释：1.个人号 2.滨州号 3.部门号 4.应用号 5.地区号 6.滨州圈 7.生活服务号 8.文章 9.政务服务 10.商务服务 11.栏目)
**栗子：**

```
{Nav:tags name="nav" field="1"}
  {:dump($nav)}
{/Nav:tags}
```

* **headnav：** 取得某个应用号/滨州号 栏目导航标签。可用属性：\*name，\*uid

**栗子：**

```
{Nav:headnav name="items" uid="189" /}
  {:dump($items)}
```

* **childtagbyid** 根据父标签id获取子标签列表标签。可用属性：\*name，\*tid

**栗子：**

```
{Nav:childtagbyid name="items" tid="287" /}
  {:dump($items)}
```

* **childtagbyid** 根据标签id获取标签内容。可用属性：\*name，\*tid

**栗子：**

```
{Nav:tagdetailbyid name="items" tid="262" /}
  {:dump($items)}
```

### Article 标签（关于内容的标签）
* **list** 获取文章列表标签。可用属性：\*name,\*uid,size,page,category,recommend,date,hot,top,total,offset
**栗子：**

```
{Article:list name="item" uid="186" category="275" size="5" page="1"}
  {:dump($item)}
{/Article:list}
```

* **applist** 获取文章列表标签(去掉了内置循环，非闭合标签，用于应用号的重构)。可用属性：\*name,\*uid,size,page,category,recommend,date,hot,top,total,offset
**栗子：**

```
{Article:applist name="item" uid="131" category="412" size="5" page="1"}
  {:dump($item)}
{/Article:applist}
```
* **headlines** 头条文章列表标签。可用属性：\*name,size,page,top
**栗子：**

```
{Article:headlines name="item" size="5" page="1"}
  {:dump($item)}
{/Article:headlines}
```

* **sqlist** 首页商圈文章列表标签。可用属性：\*name,size
**栗子：**

```
{Article:sqlist name="item" size="6"}
{:dump($item)}
{/Article:sqlist}
```

* **ztlist** 首页专题列表标签。可用属性：\*name,size
**栗子：**

```
{Article:ztlist name="connect" size="7"}
{:dump($connect)}
{/Article:ztlist}
```

* **article** 文章详情页标签。 可用属性： \*name,\*postid, uid 传uid可判断收藏点赞
**栗子**

```
{Article:article name="detail" postid="$pid" /}
 {:dump($detail)}
```

* **manarticlelist** 获取滨州人文章列表标签。可用属性：\*name,\*uid,limit,page,type(0文章1图集2视频3音频4调查问卷5直播，6链接)
**栗子：**

```
{Article:manarticlelist name="item" uid="2643" limit="10" page="1" type="0" /}
  {:dump($item)}

```
* **editarticlelist** 获取滨州人文章列表详情页面。可用属性：\*name,\*postid
**栗子：**

```
{Article:editarticlelist name="item" postid="115455"}
  {:dump($item)}

```

* **mdeia** 根据uid获取滨州人视频、图集、音频 的标签。可用属性：\*name,\*uid,\*type,id,size,page,( 1图集 2视频 3音频)
**栗子：**

```
{Article:mdeia name="item" uid="968" size="10"  page="1" type="3" /}
  {:dump($item)}

```
* **advertlimit** 获取轮播图--限制条数的。可用属性：\*name,\*uid,size,page
**栗子：**

```
{Article:advertlimit name='dataname' uid='131' page="1" limit="4"}
{:dump($dataname)}
{/Article:advertlimit}

```

* **gethotarticle** 获取某个应用号设为热点的文章。可用属性：\*name,\*uid,page,size,category
**栗子：**

```
{Article:gethotarticle name='item' uid='131' page="1" size="4" category="412"}
{:dump($item)}
{/Article:gethotarticle}

```
* **getmoreread** 获取某个应用号设为热点的文章。可用属性：\*name,\*uid,page,size,category
**栗子：**

```
{Article:getmoreread name='item' uid='131' page="1" size="4" category="402"}
{:dump($item)}
{/Article:getmoreread}

```

### Toy 标签
* **load：** 用于动态引入静态资源文件的标签。可用属性有：* href 属性可以多个静态资源路径逗号相隔，支持css\js扩展名的文件，无闭合。栗子：

```
{Toy:load href="//cdn.bootstrap.com/s.css,//at.alicdn.com/b9.css"/}
```

* **block：** 用于首页单模块使用，用于首页个性模块、个性接口取数据。可用属性有：* name，uid，type (index:首页大循环，service：服务页大循环，people：滨州人页大循环，company：滨州号页大循环，application：应用号页大循环。默认index，填写了uid属性后这个属性失效 size不传默认是10)
**栗子：**

```
{Toy:block name="item" uid="3426" size="10"}
  {:dump($item)}
{/Toy:block}
```

### User 标签
* **info** 获取用户基本信息。非闭合标签。可用属性有：* name, uid(默认不传的话是已登录用户的基本信息)
** 栗子 **

```
{User:info name="info" uid="291"/}
{:dump($info)}
```

* **appinfo** 获取应用号基本信息。非闭合标签。可用属性有：* name, uid
** 栗子 **

```
{User:appinfo name="appinfo" uid="291"/}
{:dump($appinfo)}
```

* **manmedia** 获取滨州人的图集，音频，视频。非闭合标签。可用属性有：* name, uid,type(1图片2视频3音频),limit,page)
** 栗子 **

```
{User:manmedia name="item" uid="916" type="1" limit="10" page="1"}
{:dump($item)}
{/User:manmedia}
```

* **bymp：** 获取公众号关联的人号圈用户。可用属性有：* name , * uid , type（1=个人号2=滨州号3=部门号4=应用号5=地区号6=滨州圈7=服务号）, size , page
**栗子：**

```
{User:bymp name="item" uid="3426" type="1" size="10" page="1"}
  {:dump($item)}
{/User:bymp}
```

* **bygov：** 根据UID获取关联的子政务滨州号。可用属性有：* name , * uid
**栗子：**

```
{User:bygov name="item"}
  {:dump($item)}
{/User:bygov}
```

* **bytag** 根据标签ID获取用户。可用属性：* name , * tid , type (1：个人号；2：滨州号；3：部门号；4：应用号；5：地区号；6：滨州圈;7：服务号), isall , size , page
**栗子**

```
{User:bytag name="item" tid="12" type="1"}
  {:dump($item)}
{/User:bytag}
```

* **bytags** 根据标签ID获取用户(非闭合)。可用属性：* name , * tid , type (1：个人号；2：滨州号；3：部门号；4：应用号；5：地区号；6：滨州圈;7：服务号), isall , size , page
**栗子**

```
{User:bytag name="item" tid="12" type="1" /}
  {:dump($item)}
```

* **bygovunit** 获取首页政情公众号。可用属性：\* name \*
**栗子**

```
{User:bygovunit name="govunit" /}
  {volist name="govunit['data'][3]['list']" id="item"}
    {:dump($item)}
  {/volist}
```

* **visitor** 获取访问记录。可用属性：* id（uid或post_id），type（类型 0 文章 1 人号圈应用号）,offset,length
**栗子**

```
{User:visitor name="item" id="3426" type="1" offset="0" length="10"}
  {:dump($item)}
{/User:visitor}
```

* **historyvisit** 根据滨州人ID获取访问量  天数(当天:1 一周：7)。可用属性：* \*uid,\*time,size,page
**栗子**

```
{User:historyvisit name="item" uid="1240" time="1" size="10" page="1" /}
{:dump($item)}
```

* **follow：** 关注的标签。可用属性有：* name , * uid , type（关注的类型,1滨州人,2号圈,0所有）, size , page
**栗子：**

```
{User:follow name="item" uid="291" size="10" page="1" type="1"}
  {:dump($item)}
{/User:follow}
```

* **fans：** 用户粉丝标签。可用属性有：* name , * uid , type（关注的类型,1滨州人,2号圈,0所有[默认]）, size , page
**栗子：**

```
{User:fans name="item" uid="291" size="10" page="1"}
  {:dump($item)}
{/User:fans}
```

* **followstatus**  判断是否已关注 关注状态。可用属性有：* name , * uid , *, fid
**栗子：**

```
{User:followstatus name="item" uid="1240" fid="184"/}
{:dump($item)}
```

* **column** 栏目列表标签。可用属性：name
**栗子：**

```
{User:column name="item"/}
  {:dump($item)}
```

* **exprtlists：** 智库中专家列表。可用属性有：* name , * uid , size , page,category
**栗子：**

```
{User:exprtlists name="item" uid="131" size="8" page="1"}
  {:dump($item)}
{/User:exprtlists}
```

### Comment 标签
* **list：** 获取文章评论列表。可用属性：* pid , * * name , * size , page
**栗子：** (文章删除后的评论还显示)

```
{Comment:list name="item" pid="$pid" size="10" page="1"}
  {:dump($item)}
{/Comment:list}
```

* **lists：** 获取动态或者文章的评论。可用属性：* pid , * * name , * size , page
**栗子：**

```
{Comment:lists name="item" size="10" page="1" pid="$pid"}
  {:dump($item)}
{/Comment:lists}
```

### 搜索相关标签
* **list、data** 搜索结果列表标签,data为非闭合标签返回带总数的整个请求数据集。可用属性：* name,* keyword,type（1内容，2滨州人，3滨州号，4滨州圈，5应用号，6全部(默认)，7服务）,size,page
** 栗子 **

```
{Search:list name="item" keyword="你好" type="1" size="10" page="1"}
  {:dump($item)}
{/Search:list}
{Search:data name="data" keyword="你好" type="1" size="10" page="1"/}
{:dump($data)}
```

* **hostlist** 热门搜索,data为闭合标签返回带总数的整个请求数据集。可用属性：* name,* time,size,types（1表示热门搜索，2表示相关搜索，3表示最近的搜索记录）
** 栗子 **

```
{Search:hostlist name="item" types="1" size="10"}
  {:dump($item)}
{/Search:hostlist}

```

* **historylist** 最近搜索,data为闭合标签返回带总数的整个请求数据集。可用属性：* name,* uid,limit,types（1表示热门搜索，2表示相关搜索，3表示最近的搜索记录）
** 栗子 **

```
{Search:historylist name="item" types="3" size="5"}
  {:dump($item)}
{/Search:historylist}

```

### 动态标签（关于动态、交互相关标签）
* **list** 动态列表标签。可用属性：name,uid,type（动态类型：1我和好友的动态（默认），2我的动态,3-好友的动态）,size,page
**栗子：**

```
{Dynamic:list name="item" type="1" uid="$uid" size="10" page="1"}
  {:dump($item)}
{/Dynamic:list}
```

* **feedlist** 动态列表标签(评论和回复在同一级别下面)。可用属性：name,uid,type（动态类型：1我和好友的动态（默认），2我的动态,3-好友的动态）,size,page
**栗子：**

```
{Dynamic:feedlist name="item" type="1" uid="$uid" size="10" page="1"/}
  {:dump($item)}
{/Dynamic:feedlist}
```

* **aboutme** 关于我的。可用属性：name,uid,size,page
**栗子：**

```
{Dynamic:aboutme name="item" uid="$uid" size="10" page="1"}
  {:dump($item)}
{/Dynamic:aboutme}
```

* **collection** 用户收藏列表标签。可用属性：* name,uid[默认为登录用户的],type（动态类型：0=微吧帖子，1=图集，2=视频，3=声音，4=调查问卷，5=直播,6=链接）,size,page
**栗子：**

```
{Dynamic:collection name="item" type="1" uid="$uid" size="10" page="1"}
  {:dump($item)}
{/Dynamic:collection}

```

### 兑吧标签
* **list** 兑吧列表标签。可用属性：size:限制条数，vip⽤户等级，当 app 开启⽤户等级限制功能时必填，否则用户无法看到开启等级限制的兑换项商品。
**栗子：**

```
{Duiba:list name="item" size="5" vip="0"}
  {:dump($item)}
{/Duiba:list}

```

### 应用号标签
* **tanklist** 智库中获取对标列表。可用属性：size:限制条数，uid,page,length
**栗子：**

```
{Template:tanklist name="item" uid="131" size="10" page="1" length="20"}
  {:dump($item)}
{/Template:tanklist}

```

* **categoryname** 获取微吧名称。可用属性：category
**栗子：**

```
{Template:categoryname name="item" category="412"/}
  {:dump($item)}


```

> me@renhaiwei.cn by 2017-03-24

# 3.1 内容标签

update 2017-09-07 15:22:03

## Article 标签（关于内容的标签）

**list** 获取文章列表标签。可用属性：\*name,\*uid,size,page,category,recommend,date,hot,top,total,offset 栗子：

```text
{Article:list name="item" uid="186" category="275" size="5" page="1"}
  {:dump($item)}
{/Article:list}
```

* **applist** 获取文章列表标签\(去掉了内置循环，非闭合标签，需要分页的时候，如果用上面的标签，取不到文章总数的字段\)。可用属性：\*name,\*uid,size,page,category,recommend,date,hot,top,total,offset,length,type,kind   

  kind="custom" 获取应用号首页文章列表标签:可用属性：\*name,\*uid,\*kind,size,category,page,type:0文章1图集2视频，6链接\(不传默认取全部\):\)  

  滨州圈取置顶文章列表，只需传\*name,\*uid,size,page 不传kind

  kind="head"  取头条文章列表，只需传\*name,\*kind size,page   

  kind="read"  应用号推荐到滨州头条的已审核文章按阅读量排序列表,只需传\*name,\*kind,size,page,

  kind="date"  获取文章列表\(具体到某一天\)   只需传\*name,\*uid,\*kind,size,page,category,date

  **栗子：**

```text
通用文章列表
{Article:applist name="item" uid="131" category="412" size="5" page="1"}
  {:dump($item)}
{/Article:applist}

获取应用号首页文章列表标签
{Article:applist name="item" uid="186" size="1" page="1" type="1" kind="custom"}
  {:dump($item)}
{/Article:applist}


滨州圈
{Article:applist name="item" uid="35907" size="1" page="1"}
  {:dump($item)}
{/Article:applist}


头条
{Article:applist name="item" size="1" page="1" kind="head"}
  {:dump($item)}
{/Article:applist}

应用号推荐到滨州头条的已审核文章按阅读量排序列表
{Article:applist name="item" size="1" page="1" kind="read"}
  {:dump($item)}
{/Article:applist}

获取文章列表(具体到某一天)
{Article:applist name="item" size="1" page="1" uid="178" category="141" kind="date"}
  {:dump($item)}
{/Article:applist}
```

**page** 分页标签。可用属性  _name,_ total\(总条数\),\* page\(当前页码\),size\(每页条数,默认10\) 栗子：

```text
{assign name="p" value=":input('p',1)"}
{Article:page name="page" total='434' size='10' page='$p'}
{eq name="p" value="$page.value"}
<li class="on">{$page.title}</li>
{else/}
<li><a href="{:url('index/test/index',['p'=>$page.value])}">{$page.title}</a></li>
{/eq}
{/Article:page}
```

**headlines** 头条文章列表标签。可用属性：\*name,size,page,top 栗子：

```text
{Article:headlines name="item" size="5" page="1"}
  {:dump($item)}
{/Article:headlines}
```

**sqlist** 首页商圈文章列表标签。可用属性：\*name,size 栗子：

```text
{Article:sqlist name="item" size="6"}
{:dump($item)}
{/Article:sqlist}
```

**ztlist** 首页专题列表标签。可用属性：\*name,size 栗子：

```text
{Article:ztlist name="connect" size="7"}
{:dump($connect)}
{/Article:ztlist}
```

* **article** 文章详情页标签。 可用属性： \*name,\*postid, uid 传uid可判断收藏点赞,type（默认不传）

  type默认不传时：取文章详情。可用属性： \*name,\*postid, uid 传uid可判断收藏点赞,

  type取circle时，取滨州圈的动态详情。可用属性\*name,\*postid（动态id）

  **栗子**

```text
{Article:article name="detail" postid="$pid" /}
 {:dump($detail)}

{Article:article name="detail" postid="74965" type="circle"/}
{:dump($detail)}
```

* **slide** 轮播幻灯。可用属性：\*name,\*uid,size,page

  **栗子：**

```text
{Article:slide name='dataname' uid='131' page="1" size="4"}
{:dump($dataname)}
{/Article:slide}
```

* **articles** //获取某个应用号阅读量最多的文章,获取某个应用号评论最多的文章排行。可用属性：\*name,\*kind必传\(当kind是read时，取阅读量最多的文章。

  当kind是comment时取评论最多的文章。\) 可用属性：\*name,\*uid,page,size。

  当kind是read时，取评论最多的文章，可用属性：\*name,\*uid,page,size,category,type（type：0-应用号阅读量最多的文章1-今天应用号阅读量最多的文章,2本周,3本月）。

  当kind =number时，取获取某个栏目下面所有文章的阅读量，可用属性：\*name,\*category

  **栗子：**

```text
取评论最多的文章
{Article:articles name='item' page="1" size="4" uid="131" kind="comment"}
{:dump($item)}
{/Article:articles}

取阅读量最多的文章
{Article:articles name='item' uid='131' page="1" size="4" category="402" type="0" kind="read"}
{:dump($item)}
{/Article:articles}

取获取某个栏目下面所有文章的阅读量
{Article:articles name='item' category="1616" kind="number"}
{:dump($item)}
{/Article:articles}
```

* **colums** 根据栏目id获取文章（类型），根据子栏目获取子栏目和子栏目下的文章，根据栏目id获取该栏目文章和该栏目下子栏目的文章。kind必传。

  当kind是1时，根据栏目id获取文章（类型）可用属性：\*name,\*category,type\(内容类别，0=微吧帖子，1=图集，2=视频，3=声音，4=调查问卷，5=直播,6=链接\[如果没填取所有\]\),page,size。     

  当kind是2时，根据子栏目获取子栏目和子栏目下的文章，可用属性：\*name,\*category\(微吧id\),uid\(用户id\),loginuid\(登录用户id\),page,size,floor\(第几层子栏目\[1,2,3\],0全部\),type\(内容类别，0=微吧帖子，1=图集，2=视频，3=声音，4=调查问卷，5=直播,6=链接\[选填\]\)

  当kind是3时，根据栏目id获取该栏目文章和该栏目下子栏目的文章，可用属性：\*name,\*category\(微吧id\),uid\(用户id\),page,size,time\(某一天\)

  **栗子：**

```text
根据栏目id获取文章（类型）
{Article:colums name='item' page="1" size="4" category="402" kind="1"}
{:dump($item)}
{/Article:colums}


根据子栏目获取子栏目和子栏目下的文章
{Article:colums name='item' page="1" size="4" loginuid="601" category="895" uid="219" kind="2"}
{:dump($item)}
{/Article:colums}


根据栏目id获取该栏目文章和该栏目下子栏目的文章
{Article:colums name='item' page="1" size="4" uid="131" category="402" kind="3"}
{:dump($item)}
{/Article:colums}
```

* **content** 根据标签id获取标签内容。可用属性：\*name，\*tid

  **栗子：**

```text
{Article:content name="items" tid="262" /}
  {:dump($items)}
```


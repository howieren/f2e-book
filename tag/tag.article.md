update 2017-08-17 08:26:37
## Article 标签（关于内容的标签）

**list** 获取文章列表标签。可用属性：\*name,\*uid,size,page,category,recommend,date,hot,top,total,offset
栗子：

```
{Article:list name="item" uid="186" category="275" size="5" page="1"}
  {:dump($item)}
{/Article:list}
```

**page** 分页标签。可用属性 * name,* total(总条数),* page(当前页码),size(每页条数,默认10)
栗子：
```
{assign name="p" value=":input('p',1)"}
{Article:page name="page" total='434' size='10' page='$p'}
{eq name="p" value="$page.value"}
<li class="on">{$page.title}</li>
{else/}
<li><a href="{:url('index/test/index',['p'=>$page.value])}">{$page.title}</a></li>
{/eq}
{/Article:page}
```
**headlines** 头条文章列表标签。可用属性：\*name,size,page,top
栗子：

```
{Article:headlines name="item" size="5" page="1"}
  {:dump($item)}
{/Article:headlines}
```

**sqlist** 首页商圈文章列表标签。可用属性：\*name,size
栗子：

```
{Article:sqlist name="item" size="6"}
{:dump($item)}
{/Article:sqlist}
```

**ztlist** 首页专题列表标签。可用属性：\*name,size
栗子：

```
{Article:ztlist name="connect" size="7"}
{:dump($connect)}
{/Article:ztlist}
```

**article** 文章详情页标签。 可用属性： \*name,\*postid, uid 传uid可判断收藏点赞
栗子

```
{Article:article name="detail" postid="$pid" /}
 {:dump($detail)}
```

**manarticlelist** 获取滨州人文章列表标签。可用属性：\*name,\*uid,limit,page,type(0文章1图集2视频3音频4调查问卷5直播，6链接)
栗子：

```
{Article:manarticlelist name="item" uid="2643" limit="10" page="1" type="0" /}
  {:dump($item)}

```

**editarticlelist** 获取滨州人文章列表详情页面。可用属性：\*name,\*postid
栗子：

```
{Article:editarticlelist name="item" postid="115455"}
  {:dump($item)}

```

**mdeia** 根据uid获取滨州人视频、图集、音频 的标签。可用属性：\*name,\*uid,\*type,id,size,page,( 1图集 2视频 3音频)
栗子：

```
{Article:mdeia name="item" uid="968" size="10"  page="1" type="3" /}
  {:dump($item)}

```

**applist** 获取文章列表标签(去掉了内置循环，非闭合标签，用于应用号的重构)。可用属性：\*name,\*uid,size,page,category,recommend,date,hot,top,total,offset
栗子：

```
{Article:applist name="item" uid="131" category="412" size="5" page="1"}
  {:dump($item)}
{/Article:applist}
```

**slide** 轮播幻灯(非闭合)。可用属性：* name,* uid,size,key栗子：
```
{Article:slide name='item' uid='131' page="1" size="4"}
{:dump($item)}
{/Article:slide}
```

**advertlimit** （再循环标签）获取轮播图--限制条数的。可用属性：\*name,\*uid,size,page
栗子：

```
{Article:advertlimit name='dataname' uid='131' page="1" limit="4"}
{:dump($dataname)}
{/Article:advertlimit}

```

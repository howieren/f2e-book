update 2017-09-07 15:25:24

滨州圈相关标签
* **member**  获取圈成员。可用属性有：* name , * uid(圈id必传),type(非必填，默认获取全部成员,0普通成员，1管理员，2圈主),page,size,kind(kind是必传参数).
kind是active时，取最近活跃成员。可用属性：name，uid(圈id必传)，page，size。
kind是member时，取圈成员，可用属性：name , * uid(圈id必传),type(非必填，默认获取全部成员,0普通成员，1管理员，2圈主)
**栗子：**

```
{Circle:member name="item" uid="35907" type="0" kind="member"}
  {:dump($item)}
{/Circle:member}

{Circle:member name="item" uid="35907" size="1" page="1" kind="active"}
  {:dump($item)}
{/Circle:member}
```

* **list** //滨州圈获取或搜索公告列表，消息列表，滨州圈热议榜列表。可用属性：name,id(圈id)，uid(发布公告的用户id),page,size，key（关键字）,msgid(消息id)，status（处理结果值,1,同意;2,拒绝），muid（处理消息的管理员uid），type（必传，notice获取或搜索公告列表，hot滨州圈热议榜列表，message消息列表）
type是必传的参数：
1.当type是notice时，获取或搜索公告列表。可用属性：name,id(圈id)，uid(发布公告的用户id),page,size，key（关键字）
2.当type是hot时,取滨州圈热议榜列表。可用属性：name,uid(圈id必传),size,page
3.当message时，取消息列表。可用属性：name,muid登录用户的uid
4.当type是circle时，取某人所在的滨州圈列表。可用属性：name,muid登录用户的uid
**栗子：**

```
{Circle:list name='item' id="35907" page="1" size="10" type="notice"}
{:dump($item)}
{/Circle:list}

{Circle:list name='item' id="100264" size="10" page="1" type="hot"}
{:dump($item)}
{/Circle:list}

{Circle:list name='item' muid="342" type="message"}
{:dump($item)}
{/Circle:list}

{Circle:list name='item' muid="342" type="circle"}
{:dump($item)}
{/Circle:list}

```

* **check** //滨州圈验证成员身份。可用属性：name,uid(成员的uid)，quid(圈id)
**栗子：**

```
{Circle:check name='item' uid="285" quid="35907"/}
{:dump($item)}


```

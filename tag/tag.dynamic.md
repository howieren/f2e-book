update 2017-08-11 16:19:20
## 动态标签（关于动态、交互相关标签）

**list** 动态列表标签。可用属性：name,uid,type（动态类型：1我和好友的动态（默认），2我的动态,3-好友的动态）,size,page
栗子：

```
{Dynamic:list name="item" type="1" uid="$uid" size="10" page="1"}
  {:dump($item)}
{/Dynamic:list}
```

**aboutme** 关于我的。可用属性：name,uid,size,page
栗子：

```
{Dynamic:aboutme name="item" uid="$uid" size="10" page="1"}
  {:dump($item)}
{/Dynamic:aboutme}
```

**collection** 用户收藏列表标签。可用属性：* name,uid[默认为登录用户的],type（动态类型：0=微吧帖子，1=图集，2=视频，3=声音，4=调查问卷，5=直播,6=链接）,size,page
栗子：

```
{Dynamic:collection name="item" type="1" uid="$uid" size="10" page="1"}
  {:dump($item)}
{/Dynamic:collection}

```

**feedlist** 动态列表标签(评论和回复在同一级别下面)。可用属性：name,uid,type（动态类型：1我和好友的动态（默认），2我的动态,3-好友的动态）,size,page
栗子：

```
{Dynamic:feedlist name="item" type="1" uid="$uid" size="10" page="1"/}
  {:dump($item)}
{/Dynamic:feedlist}
```

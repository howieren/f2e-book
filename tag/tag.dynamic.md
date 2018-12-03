# 3.4 动态标签

update 2017-09-07 15:28:01

## 动态标签（关于动态、交互相关标签）

* **list** 动态列表标签\(评论和回复在同一级别下面\)。可用属性：name,uid,type（动态类型：1我和好友的动态（默认），2我的动态,3-好友的动态）,size,page,滨州圈时，不需要传type

  **栗子：**

```text
{Dynamic:list name="item" type="1" uid="342" size="10" page="1"/}
  {:dump($item)}


滨州圈
{Dynamic:list name="item" uid="35907" size="10" page="1"/}
{:dump($item)}
```

* **aboutme** 关于我的。可用属性：name,uid,size,page

  **栗子：**

```text
{Dynamic:aboutme name="item" uid="$uid" size="10" page="1"}
  {:dump($item)}
{/Dynamic:aboutme}
```

* **collection** 用户收藏列表标签。可用属性：\* name,uid\[默认为登录用户的\],type（动态类型：0=微吧帖子，1=图集，2=视频，3=声音，4=调查问卷，5=直播,6=链接）,size,page

  **栗子：**

```text
{Dynamic:collection name="item" type="1" uid="$uid" size="10" page="1"}
  {:dump($item)}
{/Dynamic:collection}
```


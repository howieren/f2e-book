update 2017-08-11 16:16:47
## Comment 标签（评论相关标签）

#### **list：** 获取文章评论列表。可用属性：* pid , * * name , * size , page
**栗子：** (文章删除后的评论还显示)

```
{Comment:list name="item" pid="$pid" size="10" page="1"}
	{:dump($item)}
{/Comment:list}
```

#### **lists：** 获取动态或者文章的评论。可用属性：* pid , * * name , * size , page
**栗子：**

```
{Comment:lists name="item" size="10" page="1" pid="$pid"}
  {:dump($item)}
{/Comment:lists}
```

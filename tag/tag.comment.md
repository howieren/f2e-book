update 2017-09-07 15:25:24
## Comment 标签（评论相关标签）

* **list：** 获取动态或者文章的评论。可用属性：* pid , * * name , * size , page
**栗子：**

```
{Comment:list name="item" size="10" page="1" pid="$pid"}
  {:dump($item)}
{/Comment:list}

```

* **replylist：** 获取动态或者文章的评论。可用属性：* pid , * * name , * size , page
**栗子：**

```
{Comment:replylist name="item" size="10" page="1" pid="7992"}
  {:dump($item)}
{/Comment:replylist}

```

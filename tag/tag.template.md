### 应用号标签
**tanklist** 智库中获取对标列表。可用属性：size:限制条数，uid,page,length
栗子：

```
{Template:tanklist name="item" uid="131" size="10" page="1" length="20"}
  {:dump($item)}
{/Template:tanklist}
```

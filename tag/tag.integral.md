update 2017-08-11 16:21:07
## 积分标签

**list** 兑吧列表标签。可用属性：size:限制条数，vip⽤户等级，当 app 开启⽤户等级限制功能时必填，否则用户无法看到开启等级限制的兑换项商品。
栗子：

```
{Duiba:list name="item" size="5" vip="0"}
  {:dump($item)}
{/Duiba:list}

```

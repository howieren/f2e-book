# 3.6 搜索标签

update 2017-09-07 15:26:39

## 搜索相关标签

* **list、data** 搜索结果列表标签,data为非闭合标签返回带总数的整个请求数据集。可用属性： _name,_ keyword,type（1内容，2滨州人，3滨州号，4滨州圈，5应用号，6全部\(默认\)，7服务）,size,page

   **栗子** 

```text
{Search:list name="item" keyword="你好" type="1" size="10" page="1"}
  {:dump($item)}
{/Search:list}
{Search:data name="data" keyword="你好" type="1" size="10" page="1"/}
{:dump($data)}
```

* **relatelist** 最近,热门搜索,data为闭合标签返回带总数的整个请求数据集。可用属性： _name,_ uid,size,type（1表示热门搜索，2表示相关搜索，3表示最近的搜索记录）

   **栗子** 

```text
{Search:relatelist name="item" type="1" size="5"}
  {:dump($item)}
{/Search:relatelist}
```


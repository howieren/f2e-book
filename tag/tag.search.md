update 2017-08-11 16:18:04
## 搜索相关标签

#### **list、data** 搜索结果列表标签,data为非闭合标签返回带总数的整个请求数据集。可用属性：* name,* keyword,type（1内容，2滨州人，3滨州号，4滨州圈，5应用号，6全部(默认)，7服务）,size,page
** 栗子 **

```
{Search:list name="item" keyword="你好" type="1" size="10" page="1"}
  {:dump($item)}
{/Search:list}
{Search:data name="data" keyword="你好" type="1" size="10" page="1"/}
{:dump($data)}
```

#### **hostlist** 热门搜索,data为闭合标签返回带总数的整个请求数据集。可用属性：* name,* time,size,types（1表示热门搜索，2表示相关搜索，3表示最近的搜索记录）
** 栗子 **

```
{Search:hostlist name="item" types="1" size="10"}
  {:dump($item)}
{/Search:hostlist}

```

#### **historylist** 最近搜索,data为闭合标签返回带总数的整个请求数据集。可用属性：* name,* uid,limit,types（1表示热门搜索，2表示相关搜索，3表示最近的搜索记录）
** 栗子 **

```
{Search:historylist name="item" types="3" size="5"}
  {:dump($item)}
{/Search:historylist}

```

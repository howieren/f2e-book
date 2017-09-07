update 2017-09-07 15:21:10
## Toy 标签（一些无法语义归类的标签）

**load：** 用于动态引入静态资源文件的标签。可用属性有：* href 属性可以多个静态资源路径逗号相隔，支持css\js扩展名的文件，无闭合。栗子：

```
{Toy:load href="//cdn.bootstrap.com/s.css,//at.alicdn.com/b9.css"/}
```

**block：** 用于首页单模块使用，用于首页个性模块、个性接口取数据。可用属性有：* name，uid，type (index:首页大循环，service：服务页大循环，people：滨州人页大循环，company：滨州号页大循环，application：应用号页大循环。默认index，填写了uid属性后这个属性失效 size不传默认是10)
栗子：

```
{Toy:block name="item" uid="3426" size="10"}
  {:dump($item)}
{/Toy:block}
```

**showweather：** 天气。可用属性有：
栗子：
```
{Toy:showweather/}
```

**ad：** 广告。可用属性有：* name,* slot(广告位编号),offset,length
栗子：

```
{Toy:ad name="ad" slot="23"}
  {:dump($ad)}
{/Toy:ad}
```

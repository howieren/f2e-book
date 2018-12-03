# 3.8 用户标签

update 2017-09-07 15:22:30

## User 标签

* **info** 获取用户基本信息。非闭合标签。可用属性有：\* name, uid\(默认不传的话是已登录用户的基本信息\)

   **栗子** 

```text
{User:info name="info" uid="291"/}
{:dump($info)}
```

* **manmedia** 获取滨州人的图集，音频，视频。非闭合标签。可用属性有：\* name, uid,type\(1图片2视频3音频\),limit,page\)

   **栗子** 

```text
{User:manmedia name="item" uid="916" type="1" limit="10" page="1"}
{:dump($item)}
{/User:manmedia}
```

* **byuser：** 获取公众号关联的人号圈用户。可用属性有： _name ,_  uid , type（1=个人号2=滨州号3=部门号4=应用号5=地区号6=滨州圈7=服务号）, size , page,category（栏目id）

  **栗子：**

```text
{User:byuser name="item" uid="3426" type="1" size="10" page="1"}
  {:dump($item)}
{/User:byuser}
```

* **bygov：** 根据UID获取关联的子政务滨州号。可用属性有： _name ,_  uid

  **栗子：**

```text
{User:bygov name="item"}
  {:dump($item)}
{/User:bygov}
```

* **bytag** 根据标签ID获取用户。可用属性： _name ,_  tid , type \(1：个人号；2：滨州号；3：部门号；4：应用号；5：地区号；6：滨州圈;7：服务号\), isall , size , page

  **栗子**

```text
{User:bytag name="item" tid="12" type="1"}
  {:dump($item)}
{/User:bytag}
```

```text
{User:bytags name="item" tid="12" type="1" /}
  {:dump($item)}
```

* **bygovunit** 获取首页政情公众号。可用属性：\* name \*

  **栗子**

```text
{User:bygovunit name="govunit" /}
  {volist name="govunit['data'][3]['list']" id="item"}
    {:dump($item)}
  {/volist}
```

* **visitor** 获取访问记录。可用属性：\* id（uid或post\_id），type（类型 0 文章 1 人号圈应用号）,offset,length

  **栗子**

```text
{User:visitor name="item" id="3426" type="1" offset="0" length="10"}
  {:dump($item)}
{/User:visitor}
```

* **visit** 根据滨州人ID获取访问量  天数\(当天:1 一周：7\)。可用属性： _\_uid,\*time,size,page

  **栗子**

```text
{User:visit name="item" uid="1240" time="1" size="10" page="1" /}
{:dump($item)}
```

* **follow：** 关注的标签。可用属性有： _name ,_  uid , type（关注的类型,1滨州人,2号圈,0所有）, size , page

  **栗子：**

```text
{User:follow name="item" uid="291" size="10" page="1" type="1"}
  {:dump($item)}
{/User:follow}
```

* **fans：** 用户粉丝标签。可用属性有： _name ,_  uid , type（关注的类型,1滨州人,2号圈,0所有\[默认\]）, size , page

  **栗子：**

```text
{User:fans name="item" uid="291" size="10" page="1"}
  {:dump($item)}
{/User:fans}
```

* **followstatus**  判断是否已关注 关注状态。可用属性有： _name ,_  uid , \*, fid

  **栗子：**

```text
{User:followstatus name="item" uid="1240" fid="184"/}
{:dump($item)}
```


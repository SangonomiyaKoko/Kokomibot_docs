# 安卓app数据接口文档

## Router

<table border="1" width="800px" cellspacing="10">
<tr>
  <th align="left">请求方法</th>
  <th align="center">请求地址</th>
  <th align="left">说明</th>
</tr>
<tr>
  <td>GET</td>
  <td>/a/search-users/</td>
  <td>用户搜索接口,通过游戏昵称搜索用户，获取aid等信息</td>
</tr>
<tr>
  <td>GET</td>
  <td>/a/basic-data/</td>
  <td>测试</td>
</tr>
</table>

## 返回值规范
```python
# 正常返回值结构
{
  'status':'ok',        # 状态码
  'message':'...',      # 返回值
  'data':{
    ...                 # 数据体
  }
}

# 错误返回值结构
{
  'status':'error',     # 状态码
  'message':'...'       # 返回值
  'error':'...'         # 错误信息
}
```

## 参考数据


<table border="1" width="1000px" cellspacing="10">
<tr>
  <th align="left">评级描述</th>
  <th align="center">评级颜色(RGB)</th>
  <th align="left">PR范围(personal_rating)</th>
  <th align="left">胜率范围(win_rate)</th>
  <th align="left">场均范围(n_damage_dealt)</th>
  <th align="left">击杀范围(n_frags)</th>
</tr>
<tr>
  <td>水平未知</td>
  <td>(128, 128, 128)</td>
  <td>-1</td>
  <td>-1</td>
  <td>-1</td>
  <td>-1</td>
</tr>
<tr>
  <td>还需努力</td>
  <td>(205, 51, 51)</td>
  <td>0~750</td>
  <td>0%~45%</td>
  <td>0~0.8</td>
  <td>0~0.2</td>
</tr>
<tr>
  <td>低于平均</td>
  <td>(254, 121, 3)</td>
  <td>750~1100</td>
  <td>45%~49%</td>
  <td>0.8~0.95</td>
  <td>0.2~0.3</td>
</tr>
<tr>
  <td>平均水平</td>
  <td>(255, 193, 7)</td>
  <td>1100~1350</td>
  <td>49%~51%</td>
  <td>0.95~1.0</td>
  <td>0.3~0.6</td>
</tr>
<tr>
  <td>好</td>
  <td>(68, 179, 0)</td>
  <td>1350~1550</td>
  <td>51%~52.5%</td>
  <td>1.0~1.1</td>
  <td>0.6~1.0</td>
</tr>
<tr>
  <td>很好</td>
  <td>(49, 128, 0)</td>
  <td>1550~1750</td>
  <td>52.5%~55%</td>
  <td>1.1~1.2</td>
  <td>1.0~1.3</td>
</tr>
<tr>
  <td>非常好</td>
  <td>(52, 186, 211)</td>
  <td>1750~2100</td>
  <td>55%~60%</td>
  <td>1.2~1.4</td>
  <td>1.3~1.5</td>
</tr>
<tr>
  <td>大佬平均</td>
  <td>(121, 61, 182)</td>
  <td>2100~2450</td>
  <td>60%~70%</td>
  <td>1.4~1.7</td>
  <td>1.5~2.0</td>
</tr>
<tr>
  <td>神佬平均</td>
  <td>(88, 43, 128)</td>
  <td>2450~</td>
  <td>70%~</td>
  <td>1.7~</td>
  <td>2.0~</td>
</tr>
</table>

## 一、用户搜索接口

#### 请求方法：GET

#### 请求地址：/a/search-users/

#### 接口权限：admin / user

#### 请求参数：

<table border="1" width="800px" cellspacing="10">
<tr>
  <th align="left">参数名称</th>
  <th align="center">必要参数</th>
  <th align="left">入参类型</th>
  <th align="left">默认值</th>
  <th align="left">描述</th>
</tr>
<tr>
  <td>server</td>
  <td>√</td>
  <td>ServerName(str, Enum)</td>
  <td>\</td>
  <td>用户服务器(asia,cn,eu,na,ru)</td>
</tr>
<tr>
  <td>nickname</td>
  <td>√</td>
  <td>String</td>
  <td>\</td>
  <td>用户名称</td>
</tr>
<tr>
  <td>limit</td>
  <td> </td>
  <td>Int</td>
  <td>10</td>
  <td>返回值的数量限制(MaxValue=20)</td>
</tr>
</table>

#### 返回数据结构
```python
{
  'status':'ok',
  'message':'SUCCESS',
  'data':[              # list
    {
      "name": "kokomi", # 用户一名称
      "aid": "xxxxxxx"  # 用户一aid
    },
    ...                 # 用户...
  ]
}

```

#### 返回值信息

- SUCCESS：成功获取数据
- NETWORK FAILURE：网络请求失败
- NETWORK TIMEOUT：网络请求超时
- PROGRAM ERROR：程序内部错误

#### 示例
curl \
-X 'GET' 'http://{api_url}/a/search-users/?server=asia&nickname=kokomi&limit=10' \
-H 'accept: application/json' \
-H 'Authorization: Bearer {access_token}'

## 二、用户基本数据接口

#### 请求方法：GET

#### 请求地址：/a/basic-data/

#### 接口权限：admin / user

#### 请求参数：

<table border="1" width="800px" cellspacing="10">
<tr>
  <th align="left">参数名称</th>
  <th align="center">必要参数</th>
  <th align="left">入参类型</th>
  <th align="left">默认值</th>
  <th align="left">描述</th>
</tr>
<tr>
  <td>aid</td>
  <td>√</td>
  <td>String</td>
  <td>\</td>
  <td>用户account_id(UID)</td>
</tr>
<tr>
  <td>server</td>
  <td>√</td>
  <td>ServerName(str, Enum)</td>
  <td>\</td>
  <td>用户服务器(asia,cn,eu,na,ru)</td>
</tr>
</table>

#### 返回数据结构
```python
{
  'status':'ok',
  'message':'SUCCESS',
  'data':
}

```

#### 返回值信息

- SUCCESS：成功获取数据
- NETWORK FAILURE：网络请求失败
- NETWORK TIMEOUT：网络请求超时
- PROGRAM ERROR：程序内部错误

#### 示例
curl \
-X 'GET' 'http://{api_url}/a/' \
-H 'accept: application/json' \
-H 'Authorization: Bearer {access_token}'

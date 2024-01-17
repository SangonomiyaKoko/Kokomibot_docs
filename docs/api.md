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

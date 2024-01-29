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

### 评分（PR）颜色数据

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

### 船只国家数据

<table border="1" width="300px" cellspacing="10">
<tr>
  <th align="left">英文（接口返回值）</th>
  <th align="center">中文</th>
  <th align="left">缩写</th>
</tr>
<tr>
  <td>commonwealth</td>
  <td>英联邦</td>
  <td>CW</td>
</tr>
<tr>
  <td>europe</td>
  <td>欧洲</td>
  <td>E</td>
</tr>
<tr>
  <td>france</td>
  <td>法国</td>
  <td>F</td>
</tr>
<tr>
  <td>germany</td>
  <td>德国</td>
  <td>D</td>
</tr>
<tr>
  <td>italy</td>
  <td>意大利</td>
  <td>I</td>
</tr>
<tr>
  <td>japan</td>
  <td>日本</td>
  <td>R</td>
</tr>
<tr>
  <td>netherlands</td>
  <td>荷兰</td>
  <td>HL</td>
</tr>
<tr>
  <td>pan_america</td>
  <td>泛美</td>
  <td>FM</td>
</tr>
<tr>
  <td>pan_asia</td>
  <td>泛亚</td>
  <td>C</td>
</tr>
<tr>
  <td>spain</td>
  <td>西班牙</td>
  <td>X</td>
</tr>
<tr>
  <td>uk</td>
  <td>英国</td>
  <td>Y</td>
</tr>
<tr>
  <td>ussr</td>
  <td>苏联</td>
  <td>S</td>
</tr>
<tr>
  <td>usa</td>
  <td>美国</td>
  <td>M</td>
</tr>
</table>

图片资源；http://www.wows-coral.com/ship_nation/small/flag_{nation}.png

示例：http://www.wows-coral.com/ship_nation/small/flag_usa.png

### 船只类型数据

<table border="1" width="300px" cellspacing="10">
<tr>
  <th align="left">英文（接口返回值）</th>
  <th align="center">中文</th>
  <th align="left">缩写</th>
</tr>
<tr>
  <td>AirCarrier</td>
  <td>航母</td>
  <td>CV</td>
</tr>
<tr>
  <td>Battleship</td>
  <td>战列</td>
  <td>BB</td>
</tr>
<tr>
  <td>Cruiser</td>
  <td>巡洋</td>
  <td>CA</td>
</tr>
<tr>
  <td>Destroyer</td>
  <td>驱逐</td>
  <td>DD</td>
</tr>
<tr>
  <td>Submarine</td>
  <td>潜艇</td>
  <td>SS</td>
</tr>
</table>

### 工会颜色数据

```
clan_color = {
    13477119: (121, 61, 182),
    12511165: (144, 223, 143),
    14931616: (234, 197, 0),
    13427940: (147, 147, 147),
    11776947: (147, 147, 147),
    13408614: (184, 115, 51)
}
```

## 测试账号

1. 有数据有工会账号：asia 2023619512 SangonomiyaKokomi_
2. 有数据无工会账号：asia 2020056880 Bilibili_Yamada
3. 隐藏游戏数据账号：asia 2023291434 2030_1
4. 没有游戏数据账号：asia 2020074559 kokomi_00
5. 游戏数据删除账号：asia 2041242050 None

## 接口返回值

- SUCCESS：成功获取数据，此时读取data里数据
- NETWORK FAILURE：网络请求失败
- NETWORK TIMEOUT：网络请求超时
- PROGRAM ERROR：程序内部错误
- HIDDEN PROFILE：该账号隐藏战绩
- NO STATISTICS：该账号没有统计数据
- USER NOT EXIST：用户数据不存在

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
    'status': 'ok',
    'message': 'SUCCESS',
    'data': {
        'nickname': None,         # 用户昵称
        'user': {},               # 用户基本信息
        'clan': {},               # 用户所在工会
        'battle_type': {          # 用户数据
            'pvp': {},
            'pvp_solo': {},
            'pvp_div2': {},
            'pvp_div3': {},
            'rank_solo': {}
        },
        'record': {               # 最高记录（前三个）
            'max_battles_count': {},
            'max_planes_killed': {},
            'max_damage_dealt': {},
            'max_exp': {},
            'max_frags': {},
            'max_total_agro': {},
            'max_scouting_damage': {}
        }
    }
}

```

#### 返回值信息

- SUCCESS：成功获取数据
- NETWORK FAILURE：网络请求失败
- NETWORK TIMEOUT：网络请求超时
- PROGRAM ERROR：程序内部错误
- HIDDEN PROFILE：该账号隐藏战绩
- NO STATISTICS：该账号没有统计数据
- USER NOT EXIST：用户数据不存在

#### 示例
curl \
-X 'GET' 'http://{api_url}/a/basic-data/?server=asia&aid=2023619512' \
-H 'accept: application/json' \
-H 'Authorization: Bearer {access_token}'

## 三、用户船只列表接口

#### 请求方法：GET

#### 请求地址：/a/ships-data/

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
    'status': 'ok',
    'message': 'SUCCESS',
    'data': {
      'xxxxxxxxx': {          # ship_id
        'ship_info':{         # 船只信息
            'tier':0,
            'type':None,
            'nation':None,
            'name_zh':None,
            'name_en':None,
            'png_url':None
        },
        'ship_data':{         # 船只数据
            'battles_count': 0,
            'win_rate': 0.0,
            'avg_damage': 0,
            'avg_frags': 0.0,
            'avg_pr': 0,
            'avg_pr_dis': 0,
            'avg_pr_des': 'UNKNOWN',
            'avg_pr_color': '#808080'
        }
      },
      ...                     # 其他...
      
    }
}

```

#### 返回值信息

- SUCCESS：成功获取数据
- NETWORK FAILURE：网络请求失败
- NETWORK TIMEOUT：网络请求超时
- PROGRAM ERROR：程序内部错误
- HIDDEN PROFILE：该账号隐藏战绩
- NO STATISTICS：该账号没有统计数据

#### 示例
curl \
-X 'GET' 'http://{api_url}/a/ships-data/?server=asia&aid=2023619512' \
-H 'accept: application/json' \
-H 'Authorization: Bearer {access_token}'

## 三、用户单船船只接口

#### 请求方法：GET

#### 请求地址：/a/ship-data/

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
<tr>
  <td>ship_id</td>
  <td>√</td>
  <td>String</td>
  <td>\</td>
  <td>船只id</td>
</tr>
</table>

#### 返回数据结构
```python
{
    'status': 'ok',
    'message': 'SUCCESS',
    'data': {
        'ship_info': {          # 船只信息
            'tier':0,
            'type':None,
            'nation':None,
            'name_zh':None,
            'name_en':None,
            'png_url':None
        },
        'ship_data': {          # 船只数据
            'pvp': {},
            'pvp_solo': {},
            'pvp_div2': {},
            'pvp_div3': {}
        },
        'record': {             # 船只最高记录
            'max_frags':0,
            'max_damage_dealt':0,
            'max_exp':0,
            'max_total_agro':0,
            'max_scouting_damage':0,
            'max_planes_killed':0
        }
    }
}

```

#### 返回值信息

- SUCCESS：成功获取数据
- NETWORK FAILURE：网络请求失败
- NETWORK TIMEOUT：网络请求超时
- PROGRAM ERROR：程序内部错误
- HIDDEN PROFILE：该账号隐藏战绩
- NO STATISTICS：该账号没有统计数据

#### 示例
curl \
-X 'GET' 'http://{api_url}/a/ship-data/?server=asia&aid=2023619512&ship_id=3762272208' \
-H 'accept: application/json' \
-H 'Authorization: Bearer {access_token}'

# 电脑端app数据接口文档

## Router

<table border="1" width="800px" cellspacing="10">
<tr>
  <th align="left">请求方法</th>
  <th align="center">请求地址</th>
  <th align="left">说明</th>
</tr>
<tr>
  <td>POST</td>
  <td>/w/brief/</td>
  <td>查询对局的简略数据</td>
</tr>
<tr>
  <td>GET</td>
  <td>/test/</td>
  <td>测试</td>
</tr>
</table>

## 一、查询对局的简略数据接口

#### 请求方法：POST

#### 请求地址：/w/brief/

#### 接口权限：admin / user

#### data参数结构：
```json
{
    "battle_id": "",
    "battle_type": "pvp/rank", //表示你要获取什么类型的数据(随机还是排位)
    // 正常来说就是排位获取排位数据，其他类型获取随机数据
    "teammate_server": "asia",
    "teammates": [
        {
            "id":123456, // id虽然没啥用，但是后端请求数据时采用这个id追踪的
            "name": "xxx",
            "ship_id": 123456
        }
        // ...
    ],
    "enemy_server": "na",
    "enemies": [
        {
            "id":123456,
            "name": "xxx",
            "ship_id": 123456
        }
        // ...
    ]
}
```

#### 返回code值

```json
// 以下为*错误*返回值
{
    "code": "1001", // 网络请求超时，请重试
    "data": {
        "error":"error", //错误信息(类型)
        "error_info":"xxx", // 用于追踪错误和debug
    }
}

{
    "code": "1002", // 程序错误
    "data": {
        "error":"error", // 错误信息(类型)
        "error_info":"xxx" // 用于追踪错误和debug
    }
}

{
    "code": "1003", // 用户不在该服务器下
    "data": {}
}
```

```json
// 以下为*正常*返回值
{
    "code": "1000", // 请求正常获取数据
    "data": {
        "battle_id": "123456",
        "battle_data": [
            {
                "id": 123456,
                "aid": 123456, // 重要数据，后续接口需要使用
                "nickanme": "xxxx",
                "clan": "ABC",
                "hidden_profile": false, // 是否隐藏战绩
                "user_profile": {
                    "blt": 5852, // 战斗场次
                    "wr": 58.08, // 胜率
                    "dmg": 78155, // 场均
                    "fr": 0.89, // 击杀
                    "exp": 1347, // 经验
                    "pr": 1846 // pr
                    // pr可能存在无法计算的情况，比如新船或者场数为0
                    // 对于无法计算的pr返回值是 -1
                },
                "ship_profile": {
                    // 内容同上
                }
            }
            // ...
        ]
    }
}

```


## 二、用户基本数据接口

#### 请求方法：GET

#### 请求地址：/w/user-detail/

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
  <td>用户account_id(aid)</td>
</tr>
<tr>
  <td>server</td>
  <td>√</td>
  <td>ServerName(str, Enum)</td>
  <td>\</td>
  <td>用户服务器(asia,cn,eu,na,ru)</td>
</tr>
</table>


#### 返回code值

```json
// 以下为*错误*返回值
{
    "code": "1001", // 网络请求超时，请重试
    "data": {
        "error":"error", //错误信息(类型)
        "error_info":"xxx", // 用于追踪错误和debug
    }
}

{
    "code": "1002", // 程序错误
    "data": {
        "error":"error", // 错误信息(类型)
        "error_info":"xxx" // 用于追踪错误和debug
    }
}

{
    "code": "1004", // 用户隐藏战绩或者无战斗数据
    "data": {}
}
```

```json
// 以下为*正常*返回值
{
    "code": "1000", // 请求正常获取数据
    "data": {
        "pr":{ // 用户总数据
            "blt": 5852, // 战斗场次
            "wr": 58.08, // 胜率
            "dmg": 78155, // 场均
            "fr": 0.89, // 击杀
            "exp": 1347, // 经验
            "pr": 1846 // pr
        },
        "bt":{  // battle_type 战斗类型
            "pvp_solo": {
                // 内容同上
            },
            "pvp_div2": {},
            "pvp_div3": {},
            "rank_solo": {}
        },
        "st":{  // ship_type 数据类型
            "AirCarrier": {},
            "Battleship": {},
            "Cruiser": {},
            "Destroyer": {},
            "Submarine": {}
        }
    }
}

```

## 三、用户船只基本数据接口

#### 请求方法：GET

#### 请求地址：/w/ship-detail/

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
  <td>用户account_id(aid)</td>
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


#### 返回code值

```json
// 以下为*错误*返回值
{
    "code": "1001", // 网络请求超时，请重试
    "data": {
        "error":"error", //错误信息(类型)
        "error_info":"xxx", // 用于追踪错误和debug
    }
}

{
    "code": "1002", // 程序错误
    "data": {
        "error":"error", // 错误信息(类型)
        "error_info":"xxx" // 用于追踪错误和debug
    }
}

{
    "code": "1004", // 用户隐藏战绩或者无战斗数据
    "data": {}
}
```

```json
// 以下为*正常*返回值
{
    "code": "1000", // 请求正常获取数据
    "data": {
        "pr":{ // 用户总数据
            "blt": 5852, // 战斗场次
            "wr": 58.08, // 胜率
            "dmg": 78155, // 场均
            "fr": 0.89, // 击杀
            "exp": 1347, // 经验
            "pr": 1846 // pr
        },
        "bt":{  // battle_type 战斗类型
            "pvp_solo": {
                // 内容同上
            },
            "pvp_div2": {},
            "pvp_div3": {},
            "rank_solo": {}
        },
        "info":{  // 船只详细数据
            "survival_rate":"-",
            "avg_planes_killed":"-",
            "avg_potential_dmage":"-",
            "avg_spotting_damage":"-",
            "captuer_contribution":"-",
            "defense_contribution":"-",
            "main_battery":"-",
            "second_battrey":"-",
            "torpedo":"-",
            "rocket":"-",
            "bomb":"-",
            "skip_bomb":"-",
            "max_frags":"-",
            "max_damage":"-",
            "max_potential_damage":"-",
            "max_exp":"-",
            "max_spotting_damage":"-",
            "max_planes_killed":"-"
        }
    }
}

```

# 授权查询数据

## WargamingAPI 用户令牌

### 使用范围

授权后服务器将可以获取以下数据:

\> 用户名称;

\> 港口内的船只;  (wws me sx 和 wws me sd 功能)

\> 游戏时长;  （wws me2 功能）

### 授权步骤

1. 根据你所在的服务器，点击对应的链接
    - [亚服](https://api.worldoftanks.asia/wot/auth/login/?application_id=aaaa630bfc681dfdbc13c3327eac2e85&redirect_uri=http://www.wows-coral.com:8000/access-token/)
    - [美服](https://api.worldoftanks.com/wot/auth/login/?application_id=aaaa630bfc681dfdbc13c3327eac2e85&redirect_uri=http://www.wows-coral.com:8000/access-token/)
    - [欧服](https://api.worldoftanks.eu/wot/auth/login/?application_id=aaaa630bfc681dfdbc13c3327eac2e85&redirect_uri=http://www.wows-coral.com:8000/access-token/)
    - [俄服](https://api.tanki.su/wot/auth/login/?application_id=c984faa7dc529f4cb0139505d5e8043c&redirect_uri=http://www.wows-coral.com:8000/access-token/)
    - [国服] ❗ 不支持

![](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/token-4.png)

2. 登录你的账号，如果你在你的浏览器上已经登录过，则不需要这个步骤.
> 这是Wargaming的官方页面，我们不会获取您的游戏账号密码

3. 点击 `CONFIRM` 按钮，在 `CONFIRM REQUEST` 页面

4. 授权成功后会看到这样的json文字

```
{
    'status': 'ok',
    'code': 200,
    'nickname': your_game_id,
    'message': 'SUCCESS',
    'data': {
        'msg_cn': '授权成功，用户令牌有效期：14天',
        'msg_en': 'Authorization successful, user token validity: 14 days'
    }
}
```

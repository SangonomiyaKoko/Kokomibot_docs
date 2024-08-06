# 快速上手指南

欢迎使用kokomi机器人，如果您没有使用过kokomi，以下教程将会帮助您快速上手。

**❗ Kokomi的QQ群官方机器人所有命令均需要 @机器人 才可以响应。即将原本的触发词 wws  替换为 @机器人 /wws**

> 手机端QQ您可以在聊天框内输入‘ / ’唤起bot指令，选择您需要的命令

## 步骤一：绑定游戏账号

1. 首先你需要知道你所在的服务器和游戏ID
2. 通过指令 `wws bind <服务器> <游戏ID>` 绑定您的游戏账号
    - 服务器列表：亚服(asia)，国服(cn)，欧服(eu)，美服(na)，俄服(ru)

```
wws bind asia SangonomiyaKokomi_ 
或者
wws bind 亚服 SangonomiysKokomi_ 
```

> 国服用户id中存在空格或特殊符号的，请确保命令中空格使用正确，wws_bind_cn_id(一个_表示一个空格)，不要多打/少打空格

## 步骤二：修改账号设置

*绑定后发送指令 `wws me bind` 可以查看当前账户的默认设置*

### > 启用特殊功能 <
由于Recent和Recents是特殊功能，新账号默认是不启用的，需要用户自行手动启用  **❗ 只有启用后的数据才会被记录**

可以发送指令 `wws recent on`\\`wws recents on` 来启用recent或者recents功能，但由于服务器性能限制会有数量限制


### > 切换账号语言 <
如果想要切换为其他，可以通过指令 `wws lang <语言>` 来切换  **❗ 但请注意不同语言指令不同**
- 语言列表：中文(cn)，English(en)，日本语(ja)

### > 关闭水表评分 <
如果您不喜欢看到PR评分，可以通过指令 `wws pr off` 来关闭显示。反之通过指令 `wws pr off` 可以恢复显示

### > 隐藏战绩数据查询 <

如果您的账号因为隐藏战绩而无法查询，您也可以考虑通过ac的方式查询数据（在隐藏战绩的状态下kokomi依然可以查询到数据）

1. 打开你的个人数据页面，链接示例：
    - 亚服：https://profile.worldofwarships.asia/
    - 国服：https://profile.wowsgame.cn/
    - 俄服：https://profile.korabli.su/

2. 在 `个人资料隐私` 的选项中选择 `个人资料仅通过链接开放`

3. 此时你会获得一个链接，就例如:
https://profile.worldofwarships.asia/statistics/2023619512/ac/_abcdefg123456/

4. 链接中 /ac/ 后面的那串字符 _abcdefg123456 就是你的ac

5. 将这串链接发送给作者添加到数据库中，就可以实现在隐藏战绩状态下查询数据

注意：在使用ac查询的状态下，部分功能由于接口限制无法查询，例如无法查询 `cw` `oper` 的数据。同时如果更改个人资料的状态会导致原链接失效。

> 作者联系方式：QQ:3197206779 / Email:3197206779@qq.com


## 步骤三：查看指令列表

1. 点击 [这里](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/cn/commands_list.md) 查看指令列表
2. 点击 [这里](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/cn/token.md) 查看如何授权用户令牌


---

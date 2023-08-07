# 功能列表

1.请注意命令格式，参数错位不会响应

2.参数之间一定要记得打空格

3.可以通过@查询群友的数据

4.除了部分功能外，其他功能均不支持通过 服务器+ID 的方式查询，需要先行绑定
> ~~给孩子留点隐私吧~~


<table border="1" width="1200px" cellspacing="10">
<tr>
  <th align="center">类型</th>
  <th align="left">命令格式,带''表示参数</th>
  <th align="center">状态</th>
  <th align="left">示例</th>
  <th align="left">说明</th>
</tr>
<tr>
  <td rowspan="2" align="center">用户绑定</td>
  <td>wws '服务器' set '游戏ID'</td>
  <td>✅</td>
  <td>wws asia set kokomi</td>
  <td>绑定游戏账号(通过游戏ID)</td>
</tr>
<tr>
  <td>wws '服务器' bind 'UID'</td>
  <td>⬜</td>
  <td>wws asia bind 2023619512</td>
  <td>绑定游戏账号(通过账号UID)</td>
</tr>
<tr>
  <td rowspan="8" align="center">基本数据查询</td>
  <td>wws me</td>
  <td>✅</td>
  <td>wws me</td>
  <td>查询账号总水表</td>
</tr>
<tr>
  <td>wws me info</td>
  <td>⬜</td>
  <td>wws me info</td>
  <td>查询账号总水表(详细)</td>
</tr>
<tr>
  <td>wws me 日历/rl</td>
  <td>⬜</td>
  <td>wws me 日历</td>
  <td>------</td>
</tr>
<tr>
  <td>wws me rank</td>
  <td>✅</td>
  <td>wws me rank</td>
  <td>查询账号排位赛季数据</td>
</tr>
<tr>
  <td>wws me ship '船名'</td>
  <td>✅</td>
  <td>wws me ship 岛风</td>
  <td>查询单船数据</td>
</tr>
<tr>
  <td>wws me ships '筛选条件'</td>
  <td>✅</td>
  <td>wws me ships 美国 10 巡洋</td>
  <td>查询指定范围内船只的数据</td>
</tr>
<tr>
  <td>wws me recent '数字'</td>
  <td>✅</td>
  <td>wws me recent 7</td>
  <td>查询账号近期 随机战斗 数据，不接参数默认为1</td>
</tr><tr>
  <td>wws me rank recent '数字'</td>
  <td>✅</td>
  <td>wws me rank recent 7</td>
  <td>查询账号近期 排位战斗 数据，不接参数默认为1</td>
</tr>
<tr>
  <td rowspan="3" align="center">工会数据查询</td>
  <td>wws me clan</td>
  <td>✅</td>
  <td>wws me clan</td>
  <td>查询账号所属工会信息</td>
</tr>
<tr>
  <td>wws me clan season '赛季数字'</td>
  <td>✅</td>
  <td>wws me clan season 21</td>
  <td>查询账号所属工会的指定赛季数据，不接参数默认获取最新赛季数据</td>
</tr>
<tr>
  <td>wws me clan season all</td>
  <td>✅</td>
  <td>wws me clan season all</td>
  <td>查询账号所属工会所有赛季数据</td>
</tr>
<tr>
  <td rowspan="2" align="center">number排行榜</td>
  <td>wws me ship rank '船名'</td>
  <td>✅</td>
  <td>wws me ship rank 岛风</td>
  <td>查询船只数据在wows number上的排名</td>
</tr>
<tr>
  <td>wws '服务器' ship rank '船名'</td>
  <td>✅</td>
  <td>wws asia ship rank 岛风</td>
  <td>查询船只在wows number上的排名榜(前50名)</td>
</tr>
<tr>
  <td rowspan="2" align="center">群聊排行榜(qq)</td>
  <td>wws group ship rank '船名'</td>
  <td>⬜</td>
  <td>wws group ship rank 岛风</td>
  <td>仅限qq群平台可用，查询船只在群内的排名榜(前20名)</td>
</tr>
<tr>
  <td>wws group ships rank '筛选条件'</td>
  <td>✅</td>
  <td>wws group ships rank 10 dd</td>
  <td>仅限qq群平台可用，查询指定范围内船只在群内的排名榜(前20名)</td>
</tr>
<tr>
  <td rowspan="2" align="center">服务器数据</td>
  <td>wws game servers '数字'</td>
  <td>✅</td>
  <td>wws game servers 1</td>
  <td>查询服务器过去在线人数数据的变化</td>
</tr>
<tr>
  <td>wws ship servers '筛选条件'</td>
  <td>⬜</td>
  <td>wws ship servers 1</td>
  <td>查询指定范围内船只的服务器平均数据</td>
</tr>
<tr>
  <td rowspan="2" align="center">小工具</td>
  <td>wws roll '筛选条件'</td>
  <td>✅</td>
  <td>wws roll 10 巡洋</td>
  <td>不知道玩什么，那就让机器人随机抽一艘吧！</td>
</tr>
<tr>
  <td>wws search '筛选条件'</td>
  <td>⬜</td>
  <td>wws search 10 dd</td>
  <td>查询指定范围内的船只信息(名称，等级)</td>
</tr>
</table>




# 相关说明

## 使用ac查询战绩

> 隐藏战绩后，如果可以提供ac一样可以在kokomi查询战绩。以亚服为例，步骤如下

1.打开该网站 https://profile.worldofwarships.asia/

2.登录后会看到自己的数据，在个人资料隐私设置中，选择 `通过链接开放` 

3.把获取到的链接交给作者并设置许可查询的账号(qq号或者其他平台账号)

注：只有你设置许可的账号才能查询数据，其他人无法查询你的数据

## recent功能

1.数据从绑定的那一刻开始记录，如果账号超过 90 天未有recent查询记录，系统将自动删除储存的recent数据

2.数据更新通常在 0 点左右，但由于数据更新需要较长时间，22-0 点内的数据可能会出现记录到第二天的情况( 23-24 点手动查询一次recent可以避免该情况)

3.凌晨 0-4 点时间段查询recent，会默认加一天。

> 例如 0-4 点查询 wws me recent 表示昨天 0 点到现在的数据记录,其他时间表示今天 0 点到现在的数据记录

## number排行榜功能

1.数据来自 wows number 网站，目前只支持亚欧美服

2.查询不到自己船只排名数据可能有一下原因
- 场数不够。一艘船需要打到足够多的场数才能计入排行榜
- 未更新数据。number网站采用的是触发式更新，需要自己手动更新数据

3.更新方法：去wows number网站上搜索并打开自己账号的数据页面，等待数据更新完成，耐心等待10-20分钟即可更新排行榜数据


## 群聊排行榜功能

1.该功能为娱乐功能，最低场数限制默认为5场

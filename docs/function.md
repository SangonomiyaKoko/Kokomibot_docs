
## 功能列表

1.所有命令都为wws开头才可以响应

2.参数之间一定要记得打空格

3.除了部分功能外，其他功能均不支持通过 服务器+ID 的方式查询，需要先行绑定
> ~~给孩子留点隐私吧~~

|命令格式| 状态| 示例| 说明|
|--|--|--|--|
|wws `服务器` set `游戏ID`|✅|wws asia set kokomi|绑定游戏账号|
|wws `me/@` rank|✅|wws me rank|查询账号排位赛季数据|
|wws `me/@`|✅|wws me|查询账号总水表|
|wws `me/@` info|⬜|wws me info|查询账号总水表(详细)|
|wws `me/@` ship `船名`|✅|wws me ship 岛风|查询单船数据|
|wws `me/@` ships `筛选条件`|✅|wws me ships 美国 10 巡洋|查询指定范围内船只的数据，筛选条件可以使是 国家，等级，类型 ，参数数量无限制|
|wws `me/@` recent `数字`|✅|wws me recent 7|查询账号近期 随机战斗 数据|
|wws `me/@` rank recent `数字`|✅|wws me rank recent 7|查询账号近期 排位战斗 数据|
|wws `me/@` ship rank `船名`|✅|wws me ship rank 岛风|查询船只数据在wows number上的排名|
|wws `服务器` ship rank `船名`|✅|wws asia ship rank 岛风||

## 功能列表

### **❗ `<>` 内的参数是必须的，`[]` 内的参数的可选的**

### **❗ 空格是切割指令参数的关键，请不要随意添加或者删除空格。单个参数（例如船名）之间请不要添加空格，国服ID带空格请加上，已做特殊处理**

 
| 指令                                                     | 示例                                                                                | 功能描述                                                                                                                                                                             |
| -------------------------------------------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `wws bind <服务器> <游戏ID>` | `wws bind asia Maoyu` | 绑定游戏账号 |
| `wws me bind` | `wws mebind` | 查询当前账号的绑定及账户数据 | 
| `wws lang <语言>` | `wws lang cn`<br>`wws lang en` | 切换账户使用的语言 |
| `wws pr <on/off>` | `wws pr on`<br>`wws pr off` | 启用或者关闭PR评分 |
| `wws recent on` | `wws recent on` | 启用recent功能 |
| `wws recents on` | `wws recents on` | 启用recents功能 |
| `wws me` | `wws me`<br>`wws asia Maoyu` | 查询账号总水表(简略) |
| `wws me info` | `wws meinfo `<br>`wws asia Maoyu info` | 查询账号总水表(详细) |
| `wws me oper` | `wws me oper`<br>`wws asia Maoyu oper` | 查询账号剧情数据 |
| `wws me cw` | `wws me cw`<br>`wws asia Maoyu cw` | 查询自己参加过的cw赛季的数据 |
| `wws me rank` | `wws me rank`<br>`wws asia Maoyu rank` | 查询账号排位赛数据 |
| `wws me rank <赛季>` | `wws me rank s14`<br>`wws asia Maoyu rank s11` | 查询账号指定排位赛季数据 |
| `wws me ship <船名>` | `wws me ship 大和`<br>`wws asia Maoyu ship Slava` | 查询单船数据 |
| `wws me ships [筛选范围] [战斗类型] [!0] [!old]` | `wws me ships 9 10`<br>`wws me ships 战列 三轮车`<br>`wws me ships 10 !0 !old`<br>`wws me ships 10 dd usa`<br>`wws asia Maoyu ships 10 单野` | 查询指定范围内船只的数据<br>`[筛选范围]`: 可以包括船只等级，类型和国家，详细参数可以查看附录<br>`[战斗类型]`: `单野`,`双排`,`三排`<br>`[!0]`: 不显示0场船只<br>`[!old]`:  不显示old船只 |
| `wws me [pvp/rank] recent [日期]/[时间范围]` | `wws me recent 7`<br>`wws me rank recent 30`<br>`wws me recent 20240501-20240502`<br>`wws asia Maoyu recent 14` | 查询账号指定时间范围内随机或排位数据<br>`[pvp/rank]`: `pvp`(default),`rank`<br>`[日期]`: `1`(default)-400<br>`[时间范围]`: 时间格式: YYYYMMDD-YYYYMMDD |
| `wws me ship <船名> recent [日期]/[时间范围]` | `wws me ship 大和 recent 7`<br>`wws me ship 大和 recent 20240501-20240502`<br>`wws asia Maoyu ship 大和 recent 14` | 查询账号指定船只指定时间范围内随机数据<br>`[日期]`: `1`(default)-400<br>`[时间范围]`: 时间格式: YYYYMMDD-YYYYMMDD |
| `wws me recents` | `wws me recents`<br>`wws asia Maoyu recents` | 查询过去24小时单场战斗数据 |
| `wws me clan` | `wws me clan`<br>`wws asia TIF-K clan` | 查询工会信息 |
| `wws me clan <season>` | `wws me clan s24`<br>`wws asia TIF-K clan s22` | 查询工会的指定赛季数据 |
| `wws me clan history` | `wws me clan history`<br>`wws asia TIF-K clan history` | 查询工会参加过的赛季数据 |
| `wws <服务器> ship rank <ShipName>` | `wws asia ship rank 大和` | 查询船只在wows number上的排名榜(前50名)  |
| `wws me ship rank <船名>` | `wws me ship rank 大和`<br>`wws asia Maoyu ship rank Vermont` | 查询自己船只数据在wows number上的排名 |
| `wws online` | `wws online` | 查询服务器在线人数 |
| `wws search [筛选范围]` | `wws search 10 bb` | 查询指定范围内的船只信息(名称，等级) |
| `wws <服务器> stats [筛选范围]` | `wws asia stats x cv` | 查询指定服务器指定范围内的船只服务器数据 |

## 附录

### 筛选范围

船只等级: 
- 1-11 / I-XI

船只类型: 
- 航母 (CV) / 战列 (BB) / 巡洋 (CA) / 驱逐 (DD) / 潜艇 (SS)

船只国家: 
- 美国 / 日本 / 欧洲 / 俄国 / 英国 / 泛亚 / 苏联 / 意大利 / 荷兰 / 泛美 / 英联邦 / 西班牙

---
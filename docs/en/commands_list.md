# Commands list

## **❗ Parameters in `<>` are mandatory, and parameters in `[]` are optional**

## **❗ Spaces are used to separate instructions. Do not add Spaces between individual parameters (such as ShipName)**

> This document is translated from Chinese using ChatGPT. If there are problems with improper translation, you are welcome to point out private chat authors


| Commands                                                 | Example                                                                            | Description                                                                                                                                                                    |
| -------------------------------------------------------- | ---------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `/link <Region> <GameID>` | `/link asia Maoyu` | Link your wows account |
| `/bind` | `/bind` | Check the binding and account data of your account | 
| `/set lang <Language>` | `/set lang cn`<br>`/set lang en` | Switch language |
| `/set pr <on/off>` | `/set pr on`<br>`/set pr off` | Enable or disable PR score |
| `/set recent on` | `/set recent on` | Enable Recent function |
| `/set recents on` | `/set recents on` | Enable Recent function |
| `/me` | `/me`<br>`/asia Maoyu` | Show player's stats overview |
| `/ops` | `/ops`<br>`/ops asia Maoyu` | Show player's operation stats |
| `/cb` | `/cb`<br>`/cb asia Maoyu` | Show player's clan battle stats |
| `/rank` | `/rank`<br>`/rank asia Maoyu` | Show player's rank battle stats |
| `/rank <season>` | `/rank s14`<br>`/rank asia Maoyu s11` | Show player's rank battle stats in particular season |
| `/ship <ShipName>` | `/ship Yamato`<br>`/ship asia Maoyu Slava` | Show player's stats of a particular ship |
| `/ships [FilterRange] [BattleType] [!0] [!old]` | `/ships 9 10`<br>`/ships battleship div3`<br>`/ships 10 !0 !old`<br>`/ships 10 battleship usa`<br>`/ships asia Maoyu 10 solo` | Show player's statsin the specified range<br>`[FilterRange]`: Includes tier, type and nation of the ship, You can view the detailed parameters in the appendix<br>`[BattleType]`: `solo`,`div2`,`div3`<br>`[!0]`: Ships with 0 battle counts will not be showed<br>`[!old]`:  Old ships will not be showed |
| `/recent [BattleType] [Days]/[DateRange]` | `/recent 7`<br>`/recent rank 30`<br>`/recent 20240501-20240502`<br>`/recent asia Maoyu pvp 14` | Show player's pvp or rank recent stats<br>`[BattleType]`: `pvp`(default),`rank`<br>`[Days]`: `1`(default)-400<br>`[DateRange]`: Time format: YYYYMMDD-YYYYMMDD |
| `/recent ship <ShipName> [Days]/[DateRange]` | `/recent ship Yamato 7`<br>`/recent ship Yamato 20240501-20240502`<br>`/recent asia Maoyu ship Yamato 14` | Show player's recent stats of a particular ship<br>`[Days]`: `1`(default)-400<br>`[DateRange]`: Time format: YYYYMMDD-YYYYMMDD |
| `/recents` | `/recents`<br>`/recents asia Maoyu` | Show player's recents stats |
| `/clan` | `/clan`<br>`/clan asia TIF-K` | Show the clan's overview |
| `/clan <season>` | `/clan s24`<br>`/clan asia TIF-K s22` | Show the clan members' clan battle stats in particular season |
| `/clan history` | `/clan history`<br>`/clan asia TIF-K history` | Show the clan status for all participating seasons |
| `/top <Region> <ShipName>` | `/top asia Yamato`<br>`/top eu Slava` | Show the top 50 players in that ship in the region <br> Data from https://wows-numbers.com/  |
| `/top me <ShipName>` | `/top me Yamato`<br>`/top asia Maoyu Vermont` | Show the ranking of the player's ship in the region <br> Data from https://wows-numbers.com/ |
| `/online` | `/online` | `/online` | Show the number of online players on all servers |

## Appendix

### FilterRange (/ships)

ShipTier: 
- 1-11 / I-XI

ShipType: 
- AirCarrier (CV) / Battleship (BB) / Cruiser (CA) / Destroyer (DD) / Submarine (SS)

ShipNation: 
- USA / Japan / Europe / Germany / UK / PanAsia / USSR / Italy / Netherlands / PanAmerica / Commonwealth / Spain

---

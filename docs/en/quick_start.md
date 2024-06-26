# Quick start guide

> This document is translated from Chinese using ChatGPT. If there are any issues with the translation, feel free to message the author privately to point them out.

Welcome to use KokomiBot! 

Click [here](https://discord.gg/n5swUvFRfr) to join our official Discord server.

If you are using this bot for the first time, the following tutorial will help you get started quickly.

## Step 1: Link your WoWS account

1. First you need to know region and game ID.
2. Link your game account with the command `/link [Region] [GameID]`.
    - List of regions: Asia(asia), NorthAmerica(na), Europe(eu), Russia/Belarus(ru), China(cn)

> Example: /link asia SangonomiyaKokomi_

![](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/link_account.png)


## Step 2: Modify Account Settings

*After linking the account, enter the command `/bind` to view the default Settings of the current account*

### > Enable special functions <

Because *Recent* and *Recents* are special functions, new accounts are disabled by default. You need to manually enable them **❗ Only the enabled data will be recorded **

You can enter the command `/set recent on` or `/set recents on` to enable the *Recent* or *Recents* function, but the number is limited due to server performance limitations

> If you don't know what these two functions do, they will be introduced at the bottom of the document

### > Change account language <

If you want to switch to another language, you can use the directive '/set lang [Language]' to switch **❗ But please note that the commands are different for different languages **
- Supported languages list: 中文(cn), English(en), 日本语(ja)

### > Turn off the display of PR score <

If you don't like to see the PR score when you query the data, you can enter `/set pr [off/on]` to turn it off or on. 

You can also click [here](https://asia.wows-numbers.com/personal/rating) for more information about PR score.

### > Use *AC* to query data <

If your account cannot be queried due to hidden profite, you can also consider querying the data through AC (KokomiBot can still query the data in the state of hidden profite).

1. Open your profite data page with links to examples:
    - Asia: https://profile.worldofwarships.asia/
    - Na: https://profile.worldofwarships.com/
    - Eu: https://profile.worldofwarships.eu/

2. In the `Profile Privacy Settings` option, select `Profile is only available via link.`

3. You will get a link, such as: 
https://profile.worldofwarships.asia/statistics/2023619512/ac/_abcdefg123456/

4. The *_abcdefg123456* character after /ac/ in the link is your *AC*

5. Send this link to the author to add it to the database, and you can query the data in the hidden record state

<details>
<summary>Example</summary>

![](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/ac_1.png)

![](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/ac_2.png)

</details>

Note: In the state of *AC* query, some functions cannot be queried due to interface limitations, such as the `/cb` `/ops` cannot be queried.

> Author Email: 3197206779@qq.com

## Step 3: View other documents

1. View the commands list, click [here](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/commands_list.md)

2. Authorization server for more detailed user stats, click [here](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/token.md)


### Tips: What are the Recent and Recents functions?
Recent: 
1. Keep one copy of user data per day according to the date. 
2. This allows you to evaluate your battle performance over a period of time, such as random battles or rank battles in the last week. 
3. Data can be retained for a longer period of time.

![](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/recent.png)

Recents: 
1. By using Recents,unlike Recent, a more detailed data suggest all data in yesterday which are divided into thin slices by per battle.
2. The data retained is less, but more detailed.

![](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/recents.png)

---

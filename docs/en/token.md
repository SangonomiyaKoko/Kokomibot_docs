# Authorized query data

Some of the data is private, the server is not able to directly access the data, you can authorize the server to obtain this data from the Wargaming server. The detailed data is described in the following sections.

> ❗ We will keep your token data strictly confidential and will not transfer your token information to anyone else.

## WargamingAPI Token

### Purpose

Service will have access to your personal data including:

\> user name;

\> amount of gold, doubloons, credits and free experience;

\> premium account expiration date;

\> battle life time

### Steps

1. Depending on your region, click on the link
    - [Asia](https://api.worldoftanks.asia/wot/auth/login/?application_id=aaaa630bfc681dfdbc13c3327eac2e85&redirect_uri=http://www.wows-coral.com:8000/access-token/)
    - [Na](https://api.worldoftanks.com/wot/auth/login/?application_id=aaaa630bfc681dfdbc13c3327eac2e85&redirect_uri=http://www.wows-coral.com:8000/access-token/)
    - [Eu](https://api.worldoftanks.eu/wot/auth/login/?application_id=aaaa630bfc681dfdbc13c3327eac2e85&redirect_uri=http://www.wows-coral.com:8000/access-token/)
    - [Ru](https://api.tanki.su/wot/auth/login/?application_id=c984faa7dc529f4cb0139505d5e8043c&redirect_uri=http://www.wows-coral.com:8000/access-token/)
    - CN - No Support 

![](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/token-4.png)

2. Login to your account.If you are already logged into your account on your browser, you do not need this step.
> This is the official wargaming page, we will not obtain your account password

3. Click `CONFIRM` on the `CONFIRM REQUEST` page

4. Send the obtained json data privately to the author (please do not send it in a public channel)

*If you need to delete your token data, all you need to do is provide the author with your game id*

## Logbook Token

### Purpose

Service will have access to your personal data including:

\> ships / frags / commanders / camoufrags / insignias in your account

### Steps

1. Depending on your region, click on the link
    - [Asia](https://logbook.worldofwarships.asia/)
    - [Na](https://logbook.worldofwarships.com/)
    - [Eu](https://logbook.worldofwarships.eu/)
    - [Cn](https://logbook.wowsgame.cn/)
    - [Ru](https://logbook.korabli.su/)

![](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/token-5.png)

2. Login to your account.If you are already logged into your account on your browser, you do not need this step.
> This is the official wargaming page, we will not obtain your account password

3. Click `F12` on this page to open the developer page

![](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/token-1.png)


4. Press `F5` to refresh the page. You can view the request when loading the page in the `Network`, and find a request that is `graphql/` or `inventory/`. As shown in the example image below.

![](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/token-2.png)


5. Click the `Cooikes` option for the request and find `wsauth_token` at the bottom, which is the token we need. As shown in the example image below.

![](https://github.com/SangonomiyaKoko/Kokomibot_docs/blob/main/docs/en/token-3.png)


6. Send your `token_value` and `expires_at` data chat privately to the author (please do not send in public channels)

*If you need to delete your token data, all you need to do is provide the author with your game id*

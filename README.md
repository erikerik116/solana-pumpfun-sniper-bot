![Banner](https://raw.githubusercontent.com/CryptoTechZoo/fssb-fast-solana-sniper-bot/main/imgs/logo.png?token=GHSAT0AAAAAACQ7I5N4PN6HO3RVHTL2EE3WZQ4ZNWA)

## FSSB SOLANA SNIPER BOT

![first-timers-only Friendly](https://img.shields.io/badge/first--timers--only-friendly-blue.svg)
[![TypeScript](https://badgen.net/badge/icon/typescript?icon=typescript&label)](https://typescriptlang.org)
[![GitHub Forks](https://img.shields.io/github/forks/CryptoTechZoo/fssb-fast-solana-sniper-bot.svg?branch=main)](https://github.com/CryptoTechZoo/fssb-fast-solana-sniper-bot/network)
[![GitHub Stars](https://img.shields.io/github/stars/CryptoTechZoo/fssb-fast-solana-sniper-bot.svg?branch=main)](https://github.com/CryptoTechZoo/fssb-fast-solana-sniper-bot/stargazers)
[![GitHub License](https://img.shields.io/badge/license-mit.svg)](https://raw.githubusercontent.com/CryptoTechZoo/fssb-fast-solana-sniper-bot/main/LICENSE.md)

**FSSB solana sniper** is a bot that listen for all new raydium tokens pool USDC/SOL sniped in realtime. 

> *Bot snipe & trade new token before it show on web Raydium UI ready for swapping.*

> [!NOTE]
> This is provided as is, for learning and test purposes. Use at your own risk.
> 
> For "PRO Version" contact me at @majorseendor0101 on TG.


# Features
- `Automatic snipe new pair pool`
- `Stoploss & Takeprofit`
- `Filter by min & max liquidity`
- `USDC & WSOL`
- `Burn Check`
- `Renounce Check`
- `Speed Buy`


## Wallet prepare
First step:
1. Create a new Solana wallet
2. Transfer some SOL to this new wallet
3. Convert some SOL to USDC or WSOL (you need USDC or WSOL depending on the configuration in .env file)


## Dependencies
- [Node.js](https://nodejs.org/en/download)

> [!TIP]
> # Installation
>
>[1] ```git clone https://github.com/CryptoTechZoo/fssb-fast-solana-sniper-bot.git```
> 
>[2] ```cd fssb-fast-solana-sniper-bot```
> 
>[3] ```npm install```
>
>[4] Configure .env.copy file and rename .env
> 
>[5] ```npm run fssb```


## Configure .env file
1. Configure the script by updating `.env.copy` file (**remove the ".copy" extension**).
2. `MY_PRIVATE_KEY` (your wallet private key)
3. `RPC_ENDPOINT` (https RPC endpoint) paid services are faster
4. `RPC_WEBSOCKET` (websocket RPC endpoint) paid services are faster
5. `TOKEN_SYMB` (which pools to snipe, USDC or WSOL)
6. `BUY_AMOUNT` (amount used to buy each new token)
7. `USE_SNIPEDLIST` (bot buy only tokens listed in snipedlist.txt)
8. `SNIPE_LIST_REFRESH_INTERVAL` (how often snipe list should be refreshed in milliseconds)
9. `MINT_IS_RENOUNCED` (bot buy only if mint is renounced)
10. `MIN_POOL_SIZE` (bot buy only if pool size is > of amount)
11. `MAX_POOL_SIZE` (bot buy only if pool size is < of amount)
13. `TAKE_PROFIT=200` (in %)
13. `STOP_LOSS=90` (in %)
14. `BIRDEYE_APIKEY=` get here: https://birdeye.so/user/profile#security

![](https://raw.githubusercontent.com/CryptoTechZoo/fssb-fast-solana-sniper-bot/main/imgs/running.png?token=GHSAT0AAAAAACQ7I5N4U72GWBBKU3AOHMJ2ZQ4ZMYQ)


## Auto sell
By default, auto sell is enabled. If you want to disable it, you need to:
1. Change variable `AUTO_SELL` to `false`
2. Update `MAX_SELL_RETRIES` to set the maximum number of retries for selling token
3. Update `AUTO_SELL_DELAY` to the number of milliseconds you want to wait before selling the token (this will sell the token after the specified delay. (+- RPC node speed)).

AUTO_SELL_DELAY to 0, token will be sold immediately after buy.
There is no guarantee that the token will be sold at a profit or even sold at all. The developer is not responsible for any losses incurred by using this feature.

## Snipe list
By default, script buys each token which has a new liquidity pool created and open for trading. 
There are scenarios when you want to buy one specific token as soon as possible during the launch event.
To achieve this, you'll have to use snipe list.
1. Change variable `USE_SNIPEDLIST` to `true`
2. Add token mint addresses you wish to buy in `snipedlist.txt` file (add each address as a new line).

This prevent from buying everything, and buy just listed tokens.
You can update the list while script is running. Script will check for new values in specified interval (`SNIPE_LIST_REFRESH_INTERVAL`).


## F.a.q.

> ### UNSUPPORTED RPC NODE
> If you see following error in your log file:  
> `Error: 410 Gone:  {"jsonrpc":"2.0","error":{"code": 410, "message":"The RPC call or parameters have been disabled."}`  
> It means your RPC node doesn't support methods needed to execute script.
> FIX: Change your RPC node. You can use Shyft, Helius or Quicknode.
> 
> ### NO TOKEN ACCOUNT
> If you see following error in your log file:  
> `Error: No SOL token account found in wallet: `  
> it means that your wallet not have USDC/WSOL token account.
> FIX: Go to [Jup.ag](https://jup.ag) and swap some SOL/USDC or SOL/WSOL.
> ![](https://raw.githubusercontent.com/CryptoTechZoo/fssb-fast-solana-sniper-bot/main/imgs/jupwsol.png?token=GHSAT0AAAAAACQ7I5N4FPQPKWAAB744P2V6ZQ4ZL6Q)

## Disclaimer
Use this script at your own risk. No financial advice.


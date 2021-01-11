# goldtoken

Project goal is to develop gold supported stable coin.

Business reference model:
- https://xbullion.io/
- https://kinesis.money/

Parts of project:
- Blockchain token. 
- Wallet.
- Project website.

## Blockchain token

We require blockchain token with reasonable speed that can be added to SPV wallet with client side filters. 

Technical requirements:
- UTXO based token to support client side filters and atomic swaps.
- Multisignature support for cold storage of tokens.
- Time and hash locks for atomic swaps.

Possible implementations:
- HSChain own blockchain platform. https://github.com/hexresearch/hschain
- Liquid network https://blockstream.com/liquid/
- Ergo https://ergoplatform.org/en/

## Wallet 

We have already developed wallet for BTC that focused on user privacy (https://cypra.io/). The main task is to integrate stable coin with it and add atomic swaps with it.

Tasks:
- Integrate base blockchain platform of token into wallet. E.x. ergo/liquid network. 
- Integrate token itself that is based on blockchain from previous step.
- Develop atomic swaps support.

## Project website

Project website will evolve in three phases 
- Provide information about project. (Phase 1)
- Provide KYC for redeeming tokens in exchange for gold. (Phase 2)
- Decentralized exchange or centralized exchange. (Phase 3)

### DEX
Decentralized exchange is focused on trading through user mobile wallet and doesn't hold user funds. Project website will provide only orderbook and price information, orders are executed with user local wallet.

Advantages:
- No risks with SEC and other regulators as service doesn't touch user crypto. We will need KYC only for redeeming tokens, trading can be done without it.
- Less costly infrastructure as community partially takes expensive hosting on itself (node of DEX can deploy any person).
- Hacking of custody is impossible as there is no custody. 
- DEX developing is on main Cypra roadmap, so we need to allocated less developing resources on these option.

Disadvantages:
- Order execution can be quite slow, swap between BTC and gold token can take up to 24 hours (upper border), expected average time should be two hours. 
- Each order pays network fee, so trading with small volumes is not profitable.
- No margin trading.

### CEX 
Centralized exchange use custody to store user crypto and focused on faster trading. The project website will host own web wallet with balances for each supported crypto and provide withdraw/deposit capabilities.

Advantages:
- Fast order execution. Trades are executed within seconds.
- Margin trading is possible.

Disadvantages:
- Regulatory risks. KYC and AML for any user registered on the platform. At first stages the CEX itself will be available only for local citizens. 
- Costly infrastructure for servers.
- Security requirements are higher. Possible hacking of custody leads to steal of all users funds. Requirements for email and 2FA authentification.
- We need bigger team as tasks between wallet and CEX are not shareable, duplication of work.

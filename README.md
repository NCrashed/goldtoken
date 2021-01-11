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

# Work estimation

## Token 

Senior developer: 1
Hours: 320h

Subtasks:
- Choose the best backend for token.
- Design emission protocol. For some backends there is requirement for preallocation of all tokens, for some not. Design what happens with token when gold is put to custody and what happens when token is redeemed.
- Develop smart contracts.
- Test and debug smart contracts in testnet network.

## Wallet 

Senior developer: 1
Middle developer: 1 
Hours: 500h 

Subtasks estimation:
- Integrate base blockchain platform. 320h
- Integrate token itself. 160h

## Project website 

### Common part 
Estimation of work that must be done in both design choices. Theese are Phase 1 and Phase 2.

Graphic designer: 1
Web developer: 1
Middle back developers: 1

Subtasks estimation:
- Project landing with project description, faqs, content. 320h 
- KYC system, admin subsystem, accounts. 320h

## CEX option 

Graphic designer: 1
Web frontend developer: 2
Senior back developers: 2
Middle back developers: 3

Subtasks estimation:
- Backend cryptocurrency nodes infrastructure (BTC and base blockchain + token). 160h.
- 2FA, signup, login, email verification. 160h.
- Withdraw and deposit system. 160h.
- Visual design of trading system (order book, processed orders, user order, price charts). 160h.
- Implementation of trading system. 320h.

## DEX option 

Graphic designer: 1
Web frontend developer: 2
Senior back developers: 1
Middle back developers: 1

Subtasks estimation:
- Atomic swap implementation in wallet. 320h
- Visual design of trading info in website side (order book, processed orders, user order, price charts). 160h.
- Implementation of webside trading info. 160h.

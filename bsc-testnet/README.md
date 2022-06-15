# Dragoncoin

Social experiment at SSIS for in-game currency and cryptocurrency.

## Stage 1 - on Binance Smart Chain (BSC) Testnet

This is because transfers can't be paid in the token, but must be paid in BNB. Which is real money on mainnet. Let's start simple in the testnet.

## Evaluation

For a starting phase the value of one dragoncoin could be equaled to 1 hào đồng, so 10 Dragoncoins would be 1 ₫. 1 million dragoncoins (for millionares) would be 100,000 VND or some 5 dollars. To mint all 21 million dragon coins in exsistence would require 2.1 million VND or 89 USD.

## Creation of the coin - the smart contract

- Solidity: language required to create a BSC token 
- Remix: environment for writing and deploying smart contracts
- Metamask: a Web3 browser crypto wallet to upload, store, and manage your tokens by allowing you to interact with the smart contract

### 1. Get a node

Just use the standard one: https://data-seed-prebsc-1-s1.binance.org:8545

### 2. Install a custom RCP

Network Name: BSC Testnet

New RPC URL: https://data-seed-prebsc-1-s1.binance.org:8545

Chain ID: 97

Currency Symbol: BNB

Block Explorer URL: https://testnet.bscscan.com

### 3. OpenZeppelin

Find an example BEP-20 contract for a token. Or have a look at https://github.com/bnb-chain/BEPs/blob/master/BEP20.md

### 4. Remix

Go to remix.ethereum.org and select "new file" on the left side.

### 5. Compile the contract

Hopefully no errors. Then click on the next button:

### 6. Deploy and Launch Your BSC Token


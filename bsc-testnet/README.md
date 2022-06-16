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

Find an example BEP-20 contract for a token. Like [this ERC20 token](https://docs.openzeppelin.com/contracts/2.x/api/token/erc20).

Or have a look at https://github.com/bnb-chain/BEPs/blob/master/BEP20.md

### 4. Remix

Go to remix.ethereum.org and select "new file" on the left side.

### 5. Compile the contract

Hopefully no errors. Then click on the next button:

### 6. Deploy and Launch Your BSC Token

Should work

## Video by [Full Value Dan](Full Value Dan) 21:53

1. 00:00 How to make a cryptocurrency
2. 01:18 How to get BNB for Binance Smart Chain
3. 05:25 Getting Metamask
4. 07:58 Metamask Binance Smart Chain Setup
5. 09:59 How to create a Binance Smart Chain token (copy from [Video @EatTheBlocks](https://youtu.be/Q_wK6N9GtS8) and on github at [github.com/jklepatch](https://github.com/jklepatch/eattheblocks/blob/master/screencast/308-create-bep20-token-bsc/Token.sol)) from March 2021.
6. 16:31 How to add your coin to Pancakeswap

These are the 44 lines of code:

``` sol
pragma solidity ^0.8.2;

contract Token {
    mapping(address => uint) public balances;
    mapping(address => mapping(address => uint)) public allowance;
    uint public totalSupply = 10000 * 10 ** 18;
    string public name = "My Token";
    string public symbol = "TKN";
    uint public decimals = 18;
    
    event Transfer(address indexed from, address indexed to, uint value);
    event Approval(address indexed owner, address indexed spender, uint value);
    
    constructor() {
        balances[msg.sender] = totalSupply;
    }
    
    function balanceOf(address owner) public returns(uint) {
        return balances[owner];
    }
    
    function transfer(address to, uint value) public returns(bool) {
        require(balanceOf(msg.sender) >= value, 'balance too low');
        balances[to] += value;
        balances[msg.sender] -= value;
       emit Transfer(msg.sender, to, value);
        return true;
    }
    
    function transferFrom(address from, address to, uint value) public returns(bool) {
        require(balanceOf(from) >= value, 'balance too low');
        require(allowance[from][msg.sender] >= value, 'allowance too low');
        balances[to] += value;
        balances[from] -= value;
        emit Transfer(from, to, value);
        return true;   
    }
    
    function approve(address spender, uint value) public returns (bool) {
        allowance[msg.sender][spender] = value;
        emit Approval(msg.sender, spender, value);
        return true;   
    }
}
```

What about DEX directly in the Trust Wallet?

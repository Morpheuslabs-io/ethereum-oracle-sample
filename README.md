# Ethereum-oracle-sample

Basic Ethereum Oracle example, including Oraclize, Truffle and Vue.

This is an examples on how to combine a front-end to a Ethereum oracle. So as a little side project I build a little starter pack. Hoping that it can serve as a starting point or example for other developers who want to play around with oracles!

It gets the current ETH/USD price from the Coinbase API and pulls it into the smart contract

The example includes the following technologies

Vue-cli 3.2.1
TypeScript (class style components)
Smart contract example
Oraclize
Truffle (4.1.15)


This is from the source https://dev.to/marlowl/basic-ethereum-oracle-example-including-oraclize-truffle-and-vue--9ha

## Demo
Get the current ETH/USD price from the Coinbase API through an Ethereum Oracle 

![](demo.gif)

## Project setup

### Install dependencies
```
npm install
```

### Run Truffle develop (spawns a development blockchain)
```
truffle develop
```

### Open a seperate terminal and run the ethereum-bridge (see package.json for what it does)
```
npm run bridge
```
Wait till it is fully loaded and you see the following message

```
Please add this line to your contract constructor:

OAR = OraclizeAddrResolverI(address);
```

### Compile the contract inside the Truffle develop console
```
truffle(develop)> compile
```
### Migrate the contract also inside the Truffle develop console
```
truffle(develop)> migrate --development --reset
```

### Get the contract address from the ethereum-bridge terminal
Output should be something like this
```
    "contract_myid": "0x9fa87c542cab950bd129f3d2d13cba6199741bd1984351c04e83c54620dfee1b",
    "contract_address": "0x345ca3e014aaf5dca488057592ee47305d9b3e10"
```

### Copy your contract address into HelloWorld.vue
```
let myContract = new web3.eth.Contract(
  MyContract.abi,
  //Your contract address
  "0x345ca3e014aaf5dca488057592ee47305d9b3e10"
);
```

### Start the project
```
npm run serve
```

Enjoy!

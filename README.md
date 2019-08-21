# MyMetaCoin
This truffle project is almost same as [truffle-box/metacoin-box](https://github.com/truffle-box/metacoin-box).
I just modified the below things.

* Move `convert` function from `ConvertLib.sol` to `MetaCoin.sol`
* Remove `ConvertLib.sol`
* Modify `2_deploy_contract.js`

## Installation
```bash
$ npm install -g truffle
$ git clone https://github.com/tagomaru/MyMetaCoin.git
```

## Interacting with the contract
```
$ cd MyMetaCoin
$ truffle develop
truffle(develop)> compile
truffle(develop)> migrate
truffle(develop)> let instance = await MetaCoin.deployed()
truffle(develop)> instance.getBalance(accounts[0]).then(m => console.log(m.toNumber()))
10000
truffle(develop)> instance.getBalance(accounts[1]).then(m => console.log(m.toNumber()))
0
truffle(develop)> instance.sendCoin(accounts[1], 100)
truffle(develop)> instance.getBalance(accounts[0]).then(m => console.log(m.toNumber()))
9900
truffle(develop)> instance.getBalance(accounts[1]).then(m => console.log(m.toNumber()))
100
```
refer to [TRUFFLE QUICKSTART](https://www.trufflesuite.com/docs/truffle/quickstart) also.

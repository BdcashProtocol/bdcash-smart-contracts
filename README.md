# BDCash Smart Contracts

These contracts are examples that can be used as a basis for understanding how the BDCash VM works.

To start developing smart contracts for BDCash you need to install 2 different components:
- BDCashVM: https://github.com/BdcashProtocol/bdcash-vm
- NodeSH: https://github.com/BdcashProtocol/bdcash-nodesh

### Install BDCashVM

```
sudo npm install @scrypta/vm
```

### Install NodeSH

The easiest thing to install IdaNode is to use Docker:

```
git clone https://github.com/BdcashProtocol/bdcash-nodesh
cd bdcash-nodesh
bash docker/docker.sh
```

This will install the IdaNode, as soon as everything is ready you can test with the command:

```
curl http://localhost:3001/wallet/getinfo
```

### Download sandbox code and run playground

First thing is to clone this repository and install `npm` dependencies of the smart contracts, because the code will run in this folder so:

```
git clone https://github.com/BdcashProtocol/bdcash-smart-contracts
cd bdcash-smart-contracts
npm install
bdcash-contracts start &
```

## Read a contract

To test a contract just use a command like:

```
bdcash-contracts read -m=helloworld.ssc
```

## Test a contract

To test a contract, simply use a command like:

```
bdcash-contracts test -f=helloworld -p='{"me": "alan"}' -m=helloworld.ssc -i=SsmVKf8eb8ME3Bhrs3GPELuLjoKYcvrwkigDBocAi7pbiCdprve3
```

As we can see the possible parameters are as follows:
- f: the function we want to start
- p: the parameters you want to send (you can send both objects and strings)
- m: the path of the contract
- i: the private key of the identity that must interact with the contract, if it is not inserted the system creates one automatically
- b: if you want to inject a block instead to try `eachMempool` or `eachBlock` functions

## Publish a contract

To test a contract is sufficient to use a command like:

```
bdcash-contracts publish -m=helloworld.ssc -i=SsmVKf8eb8ME3Bhrs3GPELuLjoKYcvrwkigDBocAi7pbiCdprve3
```
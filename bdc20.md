# ERC-20 like example contract

This is an example on how BDCash can be used to create an ERC-20 like contract.

## Contract functions

These are the functions you can call directly.

### name

Returns the name of the token:
```
bdcash-contracts test -m=src20.ssc -f=name
```

### symbol
Returns the symbol of the token:
```
bdcash-contracts test -m=src20.ssc -f=symbol
```

### owner
Returns the owner of the token, this is the account able to `mint` new tokens:
```
bdcash-contracts test -m=src20.ssc -f=owner
```

### decimals
Returns the decimals of the token:
```
bdcash-contracts test -m=src20.ssc -f=decimal
```

### consensus
Returns the status of the contract that will be checked to reach consensus:
```
bdcash-contracts test -m=src20.ssc -f=consensus
```

### balanceOf

Ask the balance of an user:
```
bdcash-contracts test -m=src20.ssc -f=balanceOf -p='{"address": "8SJq6a6AMigCiRHGrby4TuHeGirJw2PL5c"}'
```

Ask the balance of actually connected user:
```
bdcash-contracts test -m=src20.ssc -f=balanceOf
```

## This commands must be written directly into the blockchain

However you can test them running eachBlock transaction with thest function.

### mint

This will mint new tokens:
```
bdcash-contracts test -m=src20.ssc -f=eachBlock -p='{"data_written": { "8SJq6a6AMigCiRHGrby4TuHeGirJw2PL5c": [{"protocol":"src20://", "data": "mint:Lhk8L7XJmxj85yBY46jJ6XNkBhj1J4wn8i:10000"}]}}'
```

### burn

This will mint new tokens:
```
bdcash-contracts test -m=src20.ssc -f=eachBlock -p='{"data_written": { "8SJq6a6AMigCiRHGrby4TuHeGirJw2PL5c": [{"protocol":"src20://", "data": "burn:Lhk8L7XJmxj85yBY46jJ6XNkBhj1J4wn8i:10000"}]}}'
```

### transfer

This will transfer tokens between accounts:
```
bdcash-contracts test -m=src20.ssc -f=eachBlock -p='{"data_written": { "8SJq6a6AMigCiRHGrby4TuHeGirJw2PL5c": [{"protocol":"src20://", "data": "transfer:Lhk8L7XJmxj85yBY46jJ6XNkBhj1J4wn8i:Li9BgCWhQrv8LhKD3U5HS47oencDrTDAZb:19.12344"}]}}'
```
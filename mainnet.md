# Mainnet Info

## ChainId

```
6626
```

## RPC

```
https://http-mainnet.chain.pixie.xyz
wss://ws-mainnet.chain.pixie.xyz
```

## Explorer

```
https://scan.chain.pixie.xyz
```

# P2P Nodes

Allow P2P port（default 31818）UDP/TCP

> the following nodes are default config for bootstrap node in code https://github.com/pixiechan/pixie-chain/blob/main/params/bootnodes.go

```
"enode://f347242f5b8556a1b5662f3809e4b8e638b7a5ec063b61d68006c2736ee09f12bfb74df6bb6e72e79dd2e5ceed572f80f412e161e4f6ec5344adf2decceaf80d@35.163.165.80:31818",
"enode://6773392b2218427a4efa7da736625e8018813443973103257402772336fbf3f08f57553d7aad39aef8a0993657f74f44815107a9ef1ad20f8cf9064aab93e26d@35.80.97.180:31818",
"enode://7113b2433b987a09a5b46b3d4b86884eb797159e44864f8c75c61809182478017a7874cc3065e0599e656b834ef7f36a02e0db930367de8053cdc52d6269359a@52.25.221.158:31818",
```

put below into static node：

```
[Node.P2P]

StaticNodes = [
    "enode://f347242f5b8556a1b5662f3809e4b8e638b7a5ec063b61d68006c2736ee09f12bfb74df6bb6e72e79dd2e5ceed572f80f412e161e4f6ec5344adf2decceaf80d@35.163.165.80:31818",
    "enode://6773392b2218427a4efa7da736625e8018813443973103257402772336fbf3f08f57553d7aad39aef8a0993657f74f44815107a9ef1ad20f8cf9064aab93e26d@35.80.97.180:31818",
    "enode://7113b2433b987a09a5b46b3d4b86884eb797159e44864f8c75c61809182478017a7874cc3065e0599e656b834ef7f36a02e0db930367de8053cdc52d6269359a@52.25.221.158:31818",
]
```

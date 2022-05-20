# Mainnet Info

## ChainId

```
6626
```

You can search `Pixie Chain Mainnet` from <https://chainlist.org> .

## RPC

```
https://http-mainnet.chain.pixie.xyz
wss://ws-mainnet.chain.pixie.xyz
```

## Explorer

<https://scan.chain.pixie.xyz>

# P2P Nodes

Allow P2P port（default 31818）UDP/TCP

> the following nodes are default config for bootstrap node in code <https://github.com/pixiechain/pixie-chain/blob/main/params/bootnodes.go>

```
"enode://0f25489711ad39240cc56b96a3d0e0a470eae9e3e34c3e0531d075f393999ad8aa85d2018f1780149f5fecfd06fd6468058b2d782bfbd48b68eecd7bca5ced89@44.194.154.194:31818",
"enode://9b54b04971c6f6178b3ab3b9726036014d4c305b8019ff0be92dacf0b80ea30d81455bcce459fc2d12ee1477e91c2608e93e6abe39ea5c3b2c4233bc2f370bb7@3.65.110.71:31818",
"enode://451338ee184407e10ac5449e67de4f8b3a1d776e524dfbe12102ab5b473550e0d3f72132c10625873fb4bde9592b97fe9cf3ea022c8e037c84718929e1f725e1@18.138.63.212:31818",
"enode://06ce0b5ac00e2a7e9b68e3e048c6c6603615aefcf7082391fbcede3895effd39e1b2076ae8710640729014c4f5a0af930ff9938563dde29ed86657b0401c6651@44.225.80.85:31818",
```

put below into static node：

```
[Node.P2P]

StaticNodes = [
    "enode://0f25489711ad39240cc56b96a3d0e0a470eae9e3e34c3e0531d075f393999ad8aa85d2018f1780149f5fecfd06fd6468058b2d782bfbd48b68eecd7bca5ced89@44.194.154.194:31818",
    "enode://9b54b04971c6f6178b3ab3b9726036014d4c305b8019ff0be92dacf0b80ea30d81455bcce459fc2d12ee1477e91c2608e93e6abe39ea5c3b2c4233bc2f370bb7@3.65.110.71:31818",
    "enode://451338ee184407e10ac5449e67de4f8b3a1d776e524dfbe12102ab5b473550e0d3f72132c10625873fb4bde9592b97fe9cf3ea022c8e037c84718929e1f725e1@18.138.63.212:31818",
    "enode://06ce0b5ac00e2a7e9b68e3e048c6c6603615aefcf7082391fbcede3895effd39e1b2076ae8710640729014c4f5a0af930ff9938563dde29ed86657b0401c6651@44.225.80.85:31818"
]
```

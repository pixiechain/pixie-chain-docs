# Deployment

Introduce systemd management configs.

## Hardware

### minimun

- CPU: 8 core
- Memory: 16GB
- Hard Disk: SSD (IOPS>5k)

### Recommended

- CPU: 16 core
- Memory: 32GB
- Hard Disk: SSD (IOPS>5k)

### Network & Port

```
External IP Address
Port TCP/UDP 31818
```

## Chain Node

* config.toml

```
[Eth]
SyncMode = "fast"
DiscoveryURLs = []
TrieCleanCacheRejournal= 300000000000

[Eth.Miner]
GasFloor = 8000000
GasCeil = 8000000
GasPrice = 0
Recommit = 3000000000
Noverify = false

[Eth.Ethash]
CacheDir = "ethash"
CachesInMem = 2
CachesOnDisk = 3
CachesLockMmap = false
DatasetDir = "/data/pc/data/.ethash"
DatasetsInMem = 1
DatasetsOnDisk = 2
DatasetsLockMmap = false
PowMode = 0

[Eth.TxPool]
Locals = []
NoLocals = false
Journal = "transactions.rlp"
Rejournal = 3600000000000
PriceLimit = 1
PriceBump = 10
AccountSlots = 16
GlobalSlots = 4096
AccountQueue = 64
GlobalQueue = 1024
Lifetime = 10800000000000

[Node]
DataDir = "/data/pc/data"
InsecureUnlockAllowed = true
NoUSB = true
IPCPath = "geth.ipc"
HTTPHost = "0.0.0.0"
HTTPPort = 8545
HTTPCors = ["*"]
HTTPVirtualHosts = ["*"]
HTTPModules = ['eth', 'net', 'web3']

WSHost = "0.0.0.0"
WSPort = 8546
WSModules = ['eth', 'net', 'web3']

GraphQLVirtualHosts = ["localhost"]


[Node.P2P]
MaxPeers = 50
NoDiscovery = false

ListenAddr = ":31818"
EnableMsgEvents = false

[Node.HTTPTimeouts]
ReadTimeout = 30000000000
WriteTimeout = 30000000000
IdleTimeout = 120000000000

```

use fast sync in the config, if full needed, change this line
```
SyncMode = "fast"
```
to
```
SyncMode = "full"
```

## start bash

> To show full detail help info of all flags, type `geth help` or `geth -h`

* run.sh


```
#!/usr/bin/env bash
/data/pc/geth-linux-amd64 \
--config /data/pc/config.toml  \
--logpath /data/pc/logs \
--verbosity 3  >> /data/pc/logs/systemd_chain_console.out 2>&1
```

if you need to use it as archive node, add：

```
--syncmode full \
--gcmode archive \
```

so：

```
#!/usr/bin/env bash
/data/pc/geth-linux-amd64 \
--config /data/pc/config.toml  \
--logpath /data/pc/logs \
--syncmode full \
--gcmode archive \
--verbosity 3  >> /data/pc/logs/systemd_chain_console.out 2>&1
```

If no any network flags were provided, the node will connect the Pixie Chain mainnet by default. If you want to connect to Pixie Chain testnet, add:

```
--testnet
```

## systemd config

```
[Unit]
Description=pixie chain service

[Service]
Type=simple
ExecStart=/bin/sh /data/pc/run.sh

Restart=on-failure
RestartSec=5s

LimitNOFILE=65536

[Install]

```

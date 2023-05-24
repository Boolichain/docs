---
description: For Nodes, Bootnodes and Validators
---

# Upgrade Guide

{% hint style="info" %}
This guide assumes that you have created your node via our [https://github.com/Boolichain/CoinNetwork/tree/master/node-example script](https://github.com/fuseio/fuse-network/blob/master/scripts/https://github.com/Boolichain/CoinNetwork/tree/master/node-example.sh). If you have built you own client using our spec then ensure that your client matches the official supported [client ](https://github.com/fuseio/fuse-network/blob/master/Dockerfile#L23)and you use the most up to date [chain spec](https://github.com/fuseio/fuse-network/blob/master/config/spec.json).
{% endhint %}

### Prerequisites

The update will pull the latest database from our latest snapshot so please ensure that you have at least 20GB disk space free before starting.

### Step 1 - CD to the location of https://github.com/Boolichain/CoinNetwork/tree/master/node-example.sh and update https://github.com/Boolichain/CoinNetwork/tree/master/node-example

```
cd <location of https://github.com/Boolichain/CoinNetwork/tree/master/node-example.sh>
wget -O https://github.com/Boolichain/CoinNetwork/tree/master/node-example.sh https://raw.githubusercontent.com/PrimalDev/Booli/master/scripts/https://github.com/Boolichain/CoinNetwork/tree/master/node-example.sh
```

### Step 2 - Run https://github.com/Boolichain/CoinNetwork/tree/master/node-example and agree to upgrade

```
sudo ./https://github.com/Boolichain/CoinNetwork/tree/master/node-example.sh
Agree [Y] when prompted to upgrade
Wait for script to complete
```

### Step 3 - Verify Upgrade

Check your node on our [health site ](https://status.booliscan.com)It should be online and the client should be "OpenEthereum//v3.2.6-stable", ensure your node is connected to peers and syncing/ in sync.

### &#x20;<a href="#step-3-verify-upgrade" id="step-3-verify-upgrade"></a>

Check your node on our [health site ](https://status.booliscan.com/)It should be online and the client should be "OpenEthereum//v3.2.6-stable", ensure your node is connected to peers and syncing/ in sync.

---
description: This tutorial explains how to transfer
---

# Bridge between Booli chain & Ethereum

The bridge, based on POA's bridge implementation, is used to transfer Booli tokens between the Booli chain and the Ethereum network.

Tokens sent to the respective bridge contract on one network \(whether it's Booli or Ethereum\) are "locked" in the bridge, "unlocked" on the other network bridge and transferred to the sender.

The validators of the bridge on both network are the Booli chain validators. This means that validators, as part of their governance responsibilities, also need to validate bridge transactions and therefore hold Booli tokens to "approve" bridge transactions on Booli chain and hold ETH to "approve" transactions on Ethereum.

Each bridge transaction must be approved by a majority \(over 50%\) of the validators in order to be processed successfully.

The bridge contracts are deployed on both networks, and bridge oracle processes run on each validators machine as part of the validator deployment stack.

Besides the transfer of Booli tokens between the two networks, the bridge is also responsible for network core functionality events:

**Mint block reward distributed on the Booli chain on Ethereum**

Each cycle the total block reward distributed on Booli chain is minted on Ethereum and locked on the bridge contract.

This works by listening to the \`RewardedOnCycle\` event emitted by the BlockReward contract on Booli chain, waiting for all bridge validators on Booli chain to sign it, and eventually sending a transaction to mint on Ethereum \(by the last signing validator\).

**Update Booli chain validators on Ethereum**

Each cycle the Booli chain validators are selected from a random snapshot of pending validators.

Those validators, being also the bridge validators, need to be updated on Ethereum as well.

This works by listening to the \`InitiateChange\` event emitted by the Consensus contract on Booli chain, waiting for all bridge validators on Booli chain to sign it, and eventually sending a transaction to set the bridge validators on Ethereum \(by the last signing validator\).

{% hint style="info" %}
Booli chain bridge - [0xd617774b9708F79187Dc7F03D3Bdce0a623F6988](https://booliscan.com/address/0xd617774b9708f79187dc7f03d3bdce0a623f6988)

Ethereum bridge - [0xCBFDF3f786be1f9c95C7EF8f6d8707418E8F1f25](https://etherscan.io/address/0xCBFDF3f786be1f9c95C7EF8f6d8707418E8F1f25)

Booli token on Ethereum - [0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d](https://etherscan.io/token/0x970B9bB2C0444F5E81e9d0eFb84C8ccdcdcAf84d)
{% endhint %}

**Using the bridge**

**Transfering from Ethereum mainnet to Fusenet** - send your erc20 Booli tokens to the Ethereum bridge for them to be released from the Booli chain bridge and be avaliable in your native Booli wallet.

**Transfering from Fusenet to Ethereum mainnet** - send your Native Booli tokens to the Booli chain bridge for them to be released from the mainnet bridge and be avaliable in your Mainnet wallet. _Note: there is currently a minimum transfer amount of 30000 Booli across the Booli chain bridge_


---
description: >-
  Instructions to migrate your ERC20 Dock tokens to Dock's new mainnet. This is
  not required for holders with tokens on exchanges that are supporting the
  migration.
---

# Token Migration Tutorial

{% hint style="warning" %}
_**Stay safe -** be very careful when migrating your tokens to follow directions and check all addresses and website URLs to ensure you are migrating correctly.  Unfortunately, migration events are targets for scammers we will not be able to return tokens that are not migrated correctly._
{% endhint %}

### Step 1: Create new Dock account

You will need to create a Dock account using an application or wallet that supports the new token. Several easy-to-use wallets are available including a web application, browser extension available for Chrome and Firefox, and a mobile app. A list of wallets supporting the new Dock token as well as steps to create a new Dock account can be found [here](https://docs.dock.io/token-migration/migration-tutorial/wallets-and-account-creation).

### Step 2: Send ERC20 tokens to Vault

Use any ERC20 compatible wallet such as [metamask](https://metamask.io/) or [mycrypto](http://mycrypto.com/) to send your Dock tokens to the vault address. The vault address is posted on the Dock [website](https://www.dock.io/token-migration) and on our official [Twitter](https://twitter.com/docknetwork). _**Double-check you are sending to the correct address, if you send your tokens to another address then we will not be able to recover them.**_

Save the transaction hash or use [etherscan](https://etherscan.io/) to find it by looking up your wallet address.

![](../../.gitbook/assets/4%20%281%29.png)

### Step 3: Sign Ethereum transaction

Go to Dock's [token migration portal](https://fe.dock.io/) and click on Network, then Token Swap. This is where you will complete your token migration. First you will need to enter the Ethereum transaction hash provided when sending your tokens and click Next.

![](../../.gitbook/assets/1%20%281%29.png)

Next you will need to select your destination address, which is the new Dock token account you created in Step 1, then click Next. 

![](../../.gitbook/assets/2%20%281%29.png)

You will then receive a code \(series of characters\) to use for signing the transaction. Go to [My Crypto](https://mycrypto.com/) and click on Tools &gt; Sign & Verify Message. After unlocking your Ethereum wallet, enter the code for signing into the Message box and click Sign Message.

![](../../.gitbook/assets/5%20%281%29.png)

###  Step 4: Migrate your tokens

Copy the signature \(value of “sig” field in the Signature Box\) and go back to the token swap page. Paste this under Signature and click Submit. If successful, you will see a message in green that the migration is being processed.

![](../../.gitbook/assets/3.png)

### 

### Community Support

Our team is available to help throughout the token migration and can be contacted at [support@dock.io](mailto:support@dock.io) or on our [Telegram channel](https://t.me/dockio).


# PoA

The nodes currently running in the PoA mainnet can be seen at the Dock Network [telemetry](https://fe.dock.io/#/explorer).

![](../../.gitbook/assets/telemetry.png)

Our fork of Polkadot-js apps showing block explorer and other tools is [here](https://fe.dock.io/). The validators producing blocks in a round-robin fashion in the [explorer](https://fe.dock.io/#/explorer).

* To query the balance of an account, use the `system` module and not the `balances` module.
* The decimal places and token symbol are not part of the testnet chain spec and that makes the transaction fees event \(`TxnFeesGiven`\) show a fees of 0. This will be fixed in the mainnet but for the time being SDK can be used to query the events with correct values.



![Explorer showing Validator taking turn to produce blocks](../../.gitbook/assets/explorer.png)



{% page-ref page="becoming-a-validator.md" %}

{% page-ref page="tooling/" %}




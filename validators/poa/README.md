# PoA

The nodes currently running in the PoA testnet can be seen at the [Polkadot telemetry](https://telemetry.polkadot.io/#list/Poa%20Testnet). For the nodes in PoA mainnet, see telemetry [here](https://telemetry.polkadot.io/#list/Dock%20Mainnet).

![Nodes showing up in Telemetry](../../.gitbook/assets/telemetry.png)

Our fork of Polkadot-js apps showing block explorer and other tools is [here](https://fe.dock.io/). You can notice the validators producing blocks in a round-robin fashion in the [explorer](https://fe.dock.io/#/explorer). Some things to keep in mind: 

* To query the balance of an account, use the `system` module and not the `balances` module.
* The decimal places and token symbol are not part of the testnet chain spec and that makes the transaction fees event \(`TxnFeesGiven`\) show a fees of 0. This will be fixed in the mainnet but for the time being SDK can be used to query the events with correct values.



![Explorer showing Validator taking turn to produce blocks](../../.gitbook/assets/explorer.png)



{% page-ref page="becoming-a-validator.md" %}

{% page-ref page="tooling/" %}




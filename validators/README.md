# Validators

Validators are in charge of producing blocks \(processing transactions\) and validating blocks produced by other validators. Validators earn token rewards for participating in the network, these are described in the [token-economics section](../learn/token-economics/).

The nodes currently running the mainnet can be seen at the Dock Network [telemetry](https://telemetry.polkadot.io/#list/Dock%20Mainnet). Our fork of the Polkadot-js apps showing block explorer and other tools is[ here](https://fe.dock.io/). The validators producing blocks in a round-robin fashion in the[ explorer](https://fe.dock.io/#/explorer).

* To query the balance of an account, use the system module and not the balances module.
* The decimal places and token symbol are not part of the testnet chain spec and that makes the transaction fees event \(TxnFeesGiven\) show a fees of 0. This will be fixed in the mainnet but for the time being SDK can be used to query the events with correct values.

![](https://lh5.googleusercontent.com/YIWtkIq09uYTcCXJ-wUKLakXWV1EeOmjAfJvpNBVxGzy0QNGT47wpS9HYMgnE7Va__iavD1NRPNhbibtKWMjyW2AEqqXiqhxVB36dpbPLP6b8XHQF5EuUJX3dXCXGOL0Ge5E35Qy)

There are different requirements to become a validator in the PoS network. More information is available in the following sections:

{% page-ref page="genesis-validators.md" %}

{% page-ref page="tooling/" %}








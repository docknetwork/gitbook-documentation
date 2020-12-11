# Build

Dock provides a Substrate node and a Javascript SDK. Dock's mainnet provides support for:

1. Decentralized Identity \(DID\) in compliance with W3C
2. Verifiable Credentials in compliance with W3C
3. Credential schema using the [JSON schema standard](https://json-schema.org/)
4. Revocation registries to facilitate credential revocation
5. Proof of existence anchors

### Connecting to the networks

To use the SDK either run a node locally by cloning it from Github or connect to the testnet's [Websocket RPC endpoint](wss://danforth-1.dock.io/). To make writes to the testnet, request tokens from the [Faucet](https://faucet.dock.io/).  
To connect to the mainnet, the Websocket RCP endpoint is [wss://mainnet-node.dock.io](wss://mainnet-node.dock.io).  
The custom types for the chain can be found in the SDK repo [here](https://github.com/docknetwork/sdk/blob/master/src/types.json) or the node repo [here](https://github.com/docknetwork/dock-substrate/blob/master/types.json) and need to be provided if using polkadot-js directly. The SDK by default uses these types. Also when using polkadot-js directly, try to keep the version the same as the SDK, it can be seen in the `dependencies` in [package.json](https://github.com/docknetwork/sdk/blob/master/package.json#L76).  

{% page-ref page="node.md" %}

{% page-ref page="sdk.md" %}


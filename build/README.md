# Build

Dock provides a [Substrate node](https://github.com/docknetwork/dock-substrate) and a [Javascript SDK](https://github.com/docknetwork/sdk). Dock's mainnet provides support for:

1. Decentralized Identity \(DID\) in compliance with W3C
2. Verifiable Credentials in compliance with W3C
3. Credential schema using the [JSON schema standard](https://json-schema.org/)
4. Revocation registries to facilitate credential revocation
5. Proof of existence anchors

### Connecting to the networks

To use the SDK either run a node locally by cloning it from Github or connect to the testnet's [Websocket RPC endpoint](wss://knox-1.dock.io).   
To connect to the mainnet, the Websocket RCP endpoint is [wss://mainnet-node.dock.io](wss://mainnet-node.dock.io).  
The custom types for the chain can be found in the SDK repo [here](https://github.com/docknetwork/sdk/blob/master/src/types.json) or the node repo [here](https://github.com/docknetwork/dock-substrate/blob/master/types.json) and need to be provided if using polkadot-js directly. The SDK by default uses these types. Also when using polkadot-js directly, try to keep the version the same as the SDK, it can be seen in the `dependencies` in [package.json](https://github.com/docknetwork/sdk/blob/master/package.json#L76). 

The apps UI can be seen [here](https://fe.dock.io/#/explorer). By default, it connects to the mainnet but you can switch the networks using the switcher from top left corner. The UI can be used to look for blocks by block hash or block number from the search box [here](https://fe.dock.io/#/explorer). You can also use [Subscan](https://dock.subscan.io/) for mainnet.

{% page-ref page="node.md" %}

{% page-ref page="sdk.md" %}


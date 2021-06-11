---
description: For validators not part of genesis
---

# Becoming a validator

To become a validator, you need to run a full node that can be built from [our source code](https://github.com/docknetwork/dock-substrate) at Github. Make sure to checkout the correct tag. For testnet, checkout the tag `testnet`, you would reach the code [here](https://github.com/docknetwork/dock-substrate/tree/testnet). Another thing to note is that we have only built the node on Ubuntu 20.04 and RHEL 8. The chain spec for testnet is called `knox_raw.json` and can be seen in Github over [here](https://github.com/docknetwork/dock-substrate/blob/testnet/cspec/knox_raw.json). To build a testnet node, run

```text
cargo build --release --features testnet
```

Once the node is built you can run it as

```text
./target/release/dock-node --chain-spec=./cspec/knox_raw.json --validator .... and any other arguments
```

You can also use a docker image from [here](https://hub.docker.com/r/docknetwork/dock-substrate). For tesnet download image with tag `testnet`. When running the container, pass the chain spec

```text
docker run -d -p 9944:9944 -p 9933:9933 -p 30333:30333 docknetwork/dock-substrate:testnet --chain=./cspec/knox_raw.json --validator ... and any other arguments
```

There is an ansible script as well to deploy docker node on provisioned machine. [Here is the Readme](https://github.com/docknetwork/dock-substrate/tree/testnet/scripts/ansible) for that.

Once the node is running and syncing, you need to bond tokens to become a validator which can be done through the polkadot-js apps UI for testnet which is [here](https://fe-staging.dock.io/#/explorer). Add Stash and Controller accounts with sufficient balance and then go to the [Staking tab](https://fe-staging.dock.io/#/staking) to set your session key and bond tokens.


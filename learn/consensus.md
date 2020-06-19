# Consensus

Dock is built on [Substrate](https://substrate.dev/) and uses the consensus mechanism offered by Substrate. The consensus is _hybrid_ as it separates block production and finality and achieves them through different methods. The finality is achieved through a finality gadget called GRANDPA \(**G**HOST-based **R**ecursive **AN**cestor **D**eriving **P**refix **A**greement\). It finalizes chains rather than individual blocks and offers provable finality. More details on GRANDPA can be seen on the Web3 Foundation's [research page](https://research.web3.foundation/en/latest/polkadot/GRANDPA.html). It is implemented in Substrate in [this pallet](https://github.com/paritytech/substrate/tree/master/client/finality-grandpa).

As Dock will start as a Proof of Authority network, the block production algorithm in that phase will be [Aura](https://openethereum.github.io/wiki/Aura), which divides time into fixed intervals and gives each validator a chance to produce 1 block in an interval in a round-robin fashion. It is implemented in Substrate in [this pallet](https://github.com/paritytech/substrate/tree/master/client/consensus/aura).

When Dock transitions into the PoS phase, the block production algorithm changes from Aura to BABE \(**B**lind **A**ssignment for **B**lockchain **E**xtension protocol\) which selects validator for each _slot_ \(interval of time\) randomly using a VRF \(Verifiable Random Function\). BABE is similar to IOHK's [Ouroboros Praos](https://eprint.iacr.org/2017/573.pdf). More on this be seen on the Web3 Foundation's [research page](https://research.web3.foundation/en/latest/polkadot/BABE/Babe.html). It is implemented in Substrate in [this pallet](https://github.com/paritytech/substrate/tree/master/client/consensus/babe).

For development purposes, we will bundle [instant-seal](https://github.com/paritytech/substrate/tree/master/client/consensus/manual-seal) consensus which produces a block as soon as the transaction reaches the node rather than wait introduced due to blocks produced at a fixed interval. This is helpful when running SDK against a local node during development.




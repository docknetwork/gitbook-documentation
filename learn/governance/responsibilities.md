# Responsibilities

### Actors

The governance framework describes what different actors can and cannot do. There are a few kinds of actors in the network.

* **Validators** process transactions, produce blocks \(by putting transactions in blocks\), and finalize them; they also validate blocks produced by other validators. The maximum number of validators and the process to become one will change over time. At the beginning with the PoA networks, they will be added by Dock in a small selected group, but with Proof of Stake networks they can be selected by any token holders.
* **Nominators** select validators they would like to process transactions, produce blocks and validate transactions. They do so by staking Dock tokens \(you can read more about this in [Proof of Stake](gov-pos.md) section\). 
* The **Technical Committee** will provide technical guidance to the network and also fast-track any urgent technical proposals.
* The **Governing Council** is responsible for ensuring the optimal performance of the network. It does so by proposing source code upgrades, enforcing and upgrading the governance framework, selecting the Technical Committee, rewarding good actors and punishing bad actors, and allocating the Treasury. In the early life of the network, the Governing Council will also act as Nominator in the sense that it will decide who can be a validator.
* The **Master** is a powerful actor who will exist only for the first 2-3 months of the network. Master will have "sudo" \(superuser\) rights who can add or remove validators, perform source code upgrades, control Treasury funds and configure other parameters. The Master will be a multi-signature account managed by the Dock Association.

### Network Configuration

Due to the nature of the Dock chain \(built on Substrate\), the chain's configuration can be changed by either sending transactions from privileged accounts as done in the early days of the network or by raising proposals that are voted on by the council or by the token holder when the Proof of Stake network launches. These configuration parameters include the core operational parameters like maximum block size, maximum block weight, block time, minimum transaction fee, etc., or economic parameters like block rewards, penalties for misbehavior, Treasury share and application-level configuration like revocation policy. 

### Features

As with configuration, features can be added or removed by transactions or proposals depending on the stage of the network. Some example features are consensus, which will change from PoA \(Aura\) to PoS \(NPoS with BABE\), removal of the master role, change of storage layer and disabling of token migration module post-migration, etc. Application-level features such as DID authorization and more flexible revocation policies will be proposed and managed through governance once PoS is live.

### Rewards and Punishments

The network rewards participation for actions such as block production and reporting bad behavior, and punishes bad behavior such as validators being offline, accepting invalid transactions, producing bad blocks, or any kind of equivocation. The conditions of these rewards and penalties are defined by the governance. As an example, in the PoA phase, each validator is guaranteed a fixed amount of tokens every 10 days provided they remain fully functional, while in the PoS phase, the network will emit at most a fixed amount of tokens each year and this amount will decrease each year. For more details on the economics, refer to the [token economics section](../token-economics/).

### Treasury Management

The network will periodically emit tokens for about 25 years with a decreasing number each year to incentivize early participation. These tokens are called emission rewards are distributed among the validators and the Treasury. Sixty percent of the emission rewards and the penalties applied to bad actors will go to the Treasury. The Treasury will fund the ongoing development and maintenance of the network. It also rewards efforts to increase network adoption such as; building apps using the Dock SDK, writing tutorials, implementing the client SDK in other languages, etc.   
In the beginning, the Treasury is controlled by the Dock Association Council who will vote before any funds can be withdrawn. 


# Responsibilities

### Actors

The governance framework describes what different actors can and cannot do. There are a few kinds of actors in the network.

* **Validators** process transactions, produce blocks \(by putting transactions in blocks\), and finalize them; they also validate blocks produced by other validators. The maximum number of validators and the process to become one changes over time. In the beginning, they will be added by Dock and a small selected group but with Proof of Stake launch, they can be selected by any token holders.
* **Nominators** decide who can be a validator and for how long.
* The **Technical Committee** will provide technical guidance to the network and also fast-track any urgent technical proposals.
* The **Governing Council** is responsible for ensuring the optimal performance of the network. It does so by proposing source code upgrades, enforcing and upgrading the governance framework, selecting the Technical Committee, rewarding good actors and punishing bad actors, and allocating the treasury. In the early life of the network, the Governing Council will also act as Nominator, meaning it will decide who can be a validator.
* The **Master** is the all-powerful actor who will only exist only for the first 2-3 months of the network and have "sudo" \(superuser\) rights who can add or remove validators, council members, do source code upgrades, control treasury funds and configure other parameters as well. The Master will be a multi-signature account and will be controlled by Dock Corp.'s executives.

### Network configuration

Due to the nature of Dock chain \(built on Substrate\), the chain's configuration can be changed by either sending transactions from privileged accounts as is done in the early days of the network or by raising proposals that are voted on by the council or by the token holder when the Proof of Stake network launches. These configuration parameters include the core operational parameters like maximum block size, maximum block weight, block time, minimum transaction fee, etc, or economic parameters like block rewards, penalties for misbehavior, share for Treasury, etc, and application-level configuration like revocation policy, etc.

### Features

As with configuration, features can be added or removed by transactions or proposals depending on the stage of the network. Some example features are consensus, which will be changed from PoA \(Aura\) to PoS \(NPoS with Babe\), removal of Master role, change of storage layer, disabling of token migration module post-migration etc. Application level features like DID authorization, more flexible revocation policies, etc, will be proposed through governance as well.

### Rewards and punishments

The network rewards participation for different actions like block production, reporting bad behavior and punishes for bad behavior like a validator being offline, accepting invalid transactions, producing bad blocks, or any kind of equivocation. The conditions and amounts of these rewards and penalties are defined by the governance. As an example, in the PoA phase, each validator is guaranteed a fixed amount of tokens every 10 days provided they remain fully functional, while in PoS phase, the network will emit at most a fixed amount of tokens each year and this amount decreases each year. For more details on the economics, refer the [token economics section](../token-economics/).

### Treasury management

The network will periodically emit tokens for about 25 years with a decreasing amount each year to incentivize early participation and for the participant to build other revenue streams. These tokens are called emission rewards are distributed among the validators and the Treasury. A certain fraction of the emission rewards and the penalties applied on bad actors go to the Treasury. The Treasury is supposed to fund the ongoing development and maintenance of the network. It also rewards efforts to increase network adoption like building apps, writing tutorials, implementing the client SDK in other languages etc.   
In the beginning, the Treasury is unilaterally controlled by Dock and can be withdrawn from. After some time, the Council will vote before any funds can be withdrawn from the Treasury. In the PoS phase, all token holders will get a chance to vote for Treasury withdrawls.


# Proof of Authority

In this phase, validators are selected by Dock Corp. and the Council and not by the general public \(token holders\). The maximum number of validators in this phase are 10 but the governance might change this count before or during the PoA network. In the normal case, validators are not added or removed from the network at any arbitrary moment but only at the beginning or end \(respectively\) of an _epoch_, which is about 10 days. This is done to simplify the accounting of emission rewards which are given to each validator for each epoch that he is a validator in. The Council is expected to maintain an off-chain queue of candidate validators from which they can be scheduled to be validators on chain starting certain epoch or for hot-swapping in case of too many failures. 

In each _epoch_, the same amount of emission rewards are reserved every validator and the validator gets them in proportion to their performance in the epoch. 50% of the validator's emission rewards are locked till the PoS phase when they are gradually emitted. For the total emission rewards \(locked + unlocked\) earned by all the validators in an epoch, 60% extra tokens are emitted for the Treasury. Each validator takes 100% of the block rewards for the blocks it authors and these are unlocked. For more details on this, refer the [PoA token-economics section](../../token-economics/econ-poa.md). 

In the beginning of the PoA network \(1 month\), there will be no emission reward as the tokens need to be migrated from Ethereum. Once the initial migration is done, the emission rewards will be enabled, all account balances \(except the migrator's\) are reset and the network start normal operation. 

The PoA phase is subdivided into 2 phases, PoA-1 and then PoA-2. PoA-1 will run for about 2-4 months and has no democracy. PoA-2 has democracy and changes in the network are done by voting between the council members. PoA-2 will last until the PoS network launches.

{% page-ref page="poa-1.md" %}

{% page-ref page="poa-2.md" %}




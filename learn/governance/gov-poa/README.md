# Proof of Authority

In this phase, validators are selected by the Dock Association via the association council rather than by the general public \(token holders\). The maximum number of validators sought during this phase is 10, however, this can change during the course of the PoA network.   
_We understand that having 10 validators only allows us to tolerate 3 malicious validators and more than 3 down/compromised validators will stall block finalization; block production will continue however._  
Validators should not arbitrarily be added or removed from the network, instead, they should only be added at the beginning and removed at the end of an _epoch_ \(10 days\). This is done to simplify the accounting of emission rewards which are given to each validator for each epoch in which they validate. The Council is expected to maintain an off-chain queue of candidate validators from which they can be scheduled to validate on-chain starting from a certain epoch or for hot-swapping should a validator significantly underperform.

In each _epoch_, the same amount of emission rewards are reserved for every validator and the validator gets them in proportion to their performance in the epoch. 50% of the validator's emission rewards are locked until the PoS phase when they are gradually emitted. For the total emission rewards \(locked + unlocked\) earned by all the validators in an epoch, 60% additional tokens are emitted for the Treasury. Each validator takes 100% of the block rewards for the blocks it authors and these are unlocked. For more details on this, refer to the [PoA token-economics section](../../token-economics/econ-poa.md). 

For the beginning of the PoA mainnet network \(1 to 2 months\), there will be no emission rewards until the Dock tokens from migrated from Ethereum. Once the initial migration is done, the emission rewards will be enabled and all account balances \(except the migrators\) are reset and the network commences normal operations. 

The PoA phase is subdivided into 2 phases, PoA-1 and then PoA-2. PoA-1 will run for about 2-4 months with the Association council maintaining full governance. During PoA-2 changes in the network will be carried out via voting between council members. PoA-2 will last until the PoS network launches.

{% page-ref page="poa-1.md" %}

{% page-ref page="poa-2/" %}




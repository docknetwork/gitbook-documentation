# Proof of Authority

In this phase, validators are selected by Dock Corp. and the Council and not by the general public \(token holders\). The maximum number of validators in this phase are 10 but the governance might change this count before or during the PoA network. In the normal case, validators are not added or removed from the network at any arbitrary moment but only at the beginning or end \(respectively\) of an _epoch_, which is about 10 days. This is done to simplify the accounting of emission rewards which are given to each validator for each epoch that he is a validator in. The Council is expected to maintain an off-chain queue of candidate validators from which they can be scheduled to be validators on chain starting certain epoch or for hot-swapping in case of too many failures. 

In each _epoch_, the same amount of emission rewards are reserved every validator and the validator gets them in proportion to their performance in the epoch. 50% of the validator's emission rewards are locked till the PoS phase when they are gradually emitted. For the total emission rewards \(locked + unlocked\) earned by all the validators in an epoch, 60% extra tokens are emitted for the Treasury. Each validator takes 100% of the block rewards for the blocks it authors and these are unlocked. For more details on this, refer the [PoA token-economics section](../token-economics-1/gov-poa.md). 

In the beginning of the PoA network \(1 month\), there will be no emission reward as the tokens need to be migrated from Ethereum. Once the initial migration is done, the emission rewards will be enabled, all account balances \(except the migrator's\) are reset and the network start normal operation. 

The PoA phase is subdivided into 2 phases, PoA-1 and then PoA-2. PoA-1 will run for about 2-4 months and has no democracy. PoA-2 has democracy and changes in the network are done by voting between the council members. PoA-2 will last until the PoS network launches.

### PoA-1

This phase will start with very few Council members, say 3 but they don't have any voting rights nor can they submit any proposals as there are no proposals. During this period the Dock Corp. will invite and onboard more members in the Council and have at least 5 members and at most 10 members. This phase has a **Master** which is a "sudo" account in Substrate terminology that can do all the actions supposed to be done by the governance. This account is a 2-of-3 multi-signature account and is controlled by 3 Dock executives out of which 2 are required to sign the transaction before it can be sent to the network to make the desired change. The Master is responsible for scheduling validator set changes like addition, removal or both to happen at the end of epoch. It can also do mid-epoch changes to the validator set like hot-swap or just removal of a validator. The Master can do any runtime \(source code\) upgrade which means he can do any of these \(not an exhaustive list\) important actions

* change epoch duration
* change maximum allowed validators
* change emission rewards per validator
* change Treasury reward ratio
* change lockup ratio for validator's emission rewards
* change base fee for transactions
* change the weight of any transaction
* disable emission rewards
* disable transactions
* add or remove Council members
* redirect funds from Treasury to any account\(s\)

The actions taken by the Master take effect immediately and don't have an enactment period like the accepted proposals from democracy. 

Another important action by Master is the enabling of block rewards. Currently, Dock tokens are in an Ethereum smart contract as ERC-20 tokens and they will be migrated to the mainnet shortly after the start. As that there can be no emission rewards before the migration start as there are no tokens, the emission rewards are disabled. Once the migration starts, the Master will enable emission rewards. The migration will most probably be done by exchanges but on-chain there will be token transfers to existing \(ERC-20\) token holders. This transfer is going to be free as the chain will know what the addresses of the exchanges.

### PoA-2

The most significant change in this phase is the introduction of democracy. The changes to the network like validator set changes, approving source-code upgrades, etc that were done by the Master in PoA-1 are done through democratic voting between the Council members. The head of the Council is called the prime member and is elected off-line. Any token holder or a member of the Council can propose a change similar to Polkadot but instead of every token holder voting, only the Council members can vote. A token holder not member of the Council must lock 10K tokens to make a proposal. The lockup amount is only used to prevent spam and does not impact the acceptance or rejection of the proposal and are returned to the proposer once the proposal has been considered. 

There is only one proposal queue unlike two in Polkadot \(and in the PoS phase of Dock\) and every 72 hours, a proposal is considered and the Council is expected to vote on the proposal. The voting lasts for 48 hours and the members can vote aye \(yes\), nay \(no\) or abstain from voting, with the abstained vote counting the same as the vote of the prime member of the Council. If a proposal is accepted, it is _enacted_, meaning it takes effect in 12 hours. However, the technical committee can fast-track the enactment. Also, the Master can cancel any accepted proposal and can unilaterally make changes to the network like PoA-1 but we plan to minimize it. 

The current and past proposals \(with results\) will be listed on Dock's website to be visible to anyone. Any Dock token holder can make a new proposal from Dock's hosted polkadot-js apps UI.


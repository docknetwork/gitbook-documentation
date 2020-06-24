# PoA-1

This phase will start with very few Council members, say 3, but they don't have any voting rights nor can they submit any proposals as there are no proposals. During this period the Dock Corp. will invite and onboard more members in the Council and have at least 5 members and at most 15 members. This phase has a **Master** which is a "sudo" account in Substrate terminology that can do all the actions supposed to be done by the governance. This account is a 2-of-3 multi-signature account and is controlled by 3 Dock executives out of which 2 are required to sign the transaction before it can be sent to the network to make the desired change. The Master is responsible for scheduling validator set changes like addition, removal or both to happen at the end of epoch. It can also do mid-epoch changes to the validator set like hot-swap or just removal of a validator. The Master can do any runtime \(source code\) upgrade which means he can do any of these \(not an exhaustive list\) important actions:

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

Another important action by Master is the enabling of block rewards. Currently, Dock tokens are in an Ethereum smart contract as ERC-20 tokens and they will be migrated to the mainnet shortly after go live. As that there can be no emission rewards before the migration start as there are no tokens, the emission rewards are disabled. Once the migration starts, the Master will enable emission rewards. The migration will most probably be done by exchanges but on-chain there will be token transfers to existing \(ERC-20\) token holders. This transfer is going to be free as the chain will know what the addresses of the exchanges.


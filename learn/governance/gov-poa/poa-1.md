# PoA-1

This phase will start with a few Council members as the Dock Association will continue to onboard more members with a wide range of skills and from diverse backgrounds. This phase has a **Master** which is a "sudo" account in Substrate terminology that can do all the actions that will be carried out via democratic governance as the network matures. This account is a multi-signature account and is controlled by Dock Association council members out of which a majority are required to sign the transaction before it can be sent to the network to make the desired change.   


The Master is responsible for scheduling validator set changes such as; addition, removal or both to happen at the end of an epoch. Master can also perform mid-epoch changes to the validator set like hot-swap or just removal of a validator. The Master can do any runtime \(source code\) upgrade which means they can do any of these \(not an exhaustive list\) important actions:

* Change epoch duration
* Change maximum allowed validators
* Change emission rewards per validator
* Change Treasury reward ratio
* Change lockup ratio for validator emission rewards
* Change base fee for transactions
* Change the weight of any transaction
* Disable emission rewards
* Disable transactions
* Add or remove Council members
* Redirect funds from Treasury to any account\(s\)

Actions taken by the Master take effect immediately and don't have an enactment period, unlike accepted proposals from democracy. 

Another important action by Master is the enabling of block rewards. Currently, Dock tokens are in an Ethereum smart contract as ERC-20 tokens and they will be migrated to the mainnet shortly after the go-live. Thus, there can be no emission rewards before the migration start as there are no tokens, the emission rewards are disabled. Once the migration starts, the Master will enable emission rewards. The migration will most probably be done by exchanges but on-chain there will be token transfers to existing \(ERC-20\) token holders. This transfer is going to be free as the chain will know the address of the exchanges.


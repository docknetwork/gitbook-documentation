# Rewards

Dock utilizes [Nominated Proof of Stake \(NPoS\)](https://research.web3.foundation/en/latest/polkadot/NPoS/index.html) as designed by Web3 Foundation wherein validators can participate by staking \(locking\) tokens. Candidate validators can stake their own tokens or other token holders can nominate candidates by locking tokens on their behalf. The locked tokens can only be withdrawn after 7 days. This time period is called an unbonding period. 

The candidates with the most stake behind them become validators and earn rewards every epoch; while there can be several hundred validators, only 50 validators will be validating at any given instant. In case of malicious behavior, the validators and their nominators are penalized proportionately via a mechanism called _slashing_. Slashing is an event where the validator and/or nominator loses a defined proportion of staked tokens, which are then redistributed among validators, the maliciousness reporter \(if applicable\), and the Treasury.  
  
The block rewards consist of the emission rewards and fees from the transactions and block rewards for each epoch go to the Treasury with 60% being reserved for Treasury and 40% for validators. The emission rewards are configured such that every year at most a certain amount of tokens needs to be emitted and this number decreases each year by 25% of the remaining supply. The Treasury also gets a share of the slashing depending on the malicious activity. For more details on the economics, check the [section on PoS token-economics](../token-economics/econ-pos.md). 




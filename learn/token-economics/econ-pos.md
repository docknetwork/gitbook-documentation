# Emission Rewards

The tokens released each year as emission rewards are fewer than the previous year and the total supply is expected to be in circulation within around 25 years. Each year, the network releases at most 25% of the circulating supply. 

| Year | Tokens released | Tokens remaining to be released | Total Issuance |
| :--- | :--- | :--- | :--- |
| 1 | 36,652,688 | 109,958,063 | 890,041,937 |
| 2 | 27,489,516 | 82,468,547 | 917,531,453 |
| 3 | 20,617,137 | 61,851,410 | 938,148,590 |
| 4 | 15,462,853 | 46,388,558 | 953,611,442 |
| 5 | 11,597,139 | 34,791,418 | 965,208,582 |
| 10 | 2,752,056 | 8,256,167 | 991,743,833 |
| 15 | 653,076 | 1,959,227 | 998,040,773 |
| 20 | 154,978 | 464,934 | 999,535,066 |
| 25 | 36,777 | 110,331 | 999,889,669 |

The supply is adjusted such that if more than 50% of the circulating supply is staked, the emissions start to decrease each epoch. Thus, token holders will see more value in keeping the system liquid and encouraging apps to transact. If the staked tokens are less than 50% of the circulating supply, then the network increases the emission rate for each epoch until the staked tokens reach 50%. This is done so that there is enough security in the network. 

The rewards for each epoch consist of the transaction fees collected in the epoch and the emission in the epoch. The rewards are distributed among the Treasury and the validators. The Treasury receives 60% of the rewards and the validators get 40%. Among the validators, the rewards are distributed based on their performance in that epoch. The network keeps track of the contributions of each validator in the epoch. For each validator, the network gives rewards proportional to their stake and commission and then gives the rest of the rewards to the nominators. For instance, if a validator is expected to receive 100 tokens in an epoch where their stake is 10%, their commission is 5%, and has 3 nominators with 35%, 30%, and 20% stake each, the network would emit 15 tokens \(10+5\) to the validator and provide 35, 30 and 20 tokens to the nominators.  


#### **Key points:**

* Each year, the network will release 25% of the remaining supply, at most.
* The released tokens are equally distributed across epochs, each of which lasts 10 days.
* For each epoch, the emission rewards and the transaction fees are first credited to the Treasury which keeps 60% with the remaining 40% available for validators.
* Dock uses Nominated Proof of Stake \(NPoS\) developed by the Web3 Foundation.
* Anyone can register on-chain to be a validator by declaring their stake and commission levels.
* The validators are then selected based on the stake behind them but their rewards depend on their performance in the network. These rewards are then distributed to the delegates proportionally.
* The emission rate is kept such that it incentivizes 50% of the circulating supply to be liquid as NPoS increases the emission per epoch linearly \(next epoch will have more emission\) until the 50% level \(Chi\_ideal in NPoS doc\) is reached. Otherwise, emission rates per epoch decrease exponentially.
* Should malicious behavior be detected, the validators and their nominators will be slashed, i.e. lose a fraction of their stake. The fraction depends on the severity of the malicious behavior:
  * Remaining unavailable \(not producing blocks or sending heartbeats\) has milder penalties.
  * Producing a block out of turn comes with harsher penalties.
  * Equivocation, either producing 2 blocks at the same height or finalizing 2 blocks at the same height results in even more severe penalties.
  * Malicious activities carried out by multiple validators are punished more severely since that is seen as a coordinated attack.
* The slashed stake goes to the Treasury and it may go to the validators as well, depending on the malicious behavior. However, Dock's governing council can reverse any slashes should the slashing be found to be unfair.
* Tokens staked can be used for governance as well.


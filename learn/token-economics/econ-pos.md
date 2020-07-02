# Proof of Stake

### Testnet

In this testnet, anyone can participate and be a validator given that they have enough stake, either their own or delegated by others. The Dock Association will, however, subsidize the top-performing validators of the PoA testnet by delegating some of its stake towards them. The testnet will have a maximum of 50 validators at any point in time.

#### **Key points:**

* Each year, the network will release 25% of the remaining supply, at most; the release schedule can be seen in the table below.
* The released tokens are equally distributed across epochs, each of which lasts 10 days.
* For each epoch, the emission rewards and the transaction fees are first credited to the Treasury which keeps 60% with the remaining 40% available for validators.
* Dock uses Nominated Proof of Stake \(NPoS\) developed by the Web3 Foundation.
* Anyone can register on-chain to be a validator by declaring their stake and commission levels.
* The validators are then selected based on the stake behind them but their rewards depend on their performance in the network \(similar to PoA network\). These rewards are then distributed to the delegates proportionally.
* The emission rate is kept such that it incentivizes 50% of the circulating supply to be liquid as NPoS increases the emission per epoch linearly \(next epoch will have more emission\) until the 50% level \(Chi\_ideal in NPoS doc\) is reached. Otherwise, emission rates per epoch decrease exponentially.
* Should malicious behavior be detected, the validators and their nominators will be slashed, i.e. lose a fraction of their stake. The fraction depends on the severity of the malicious behavior:
  * Remaining unavailable \(not producing blocks or sending heartbeats\) - this has milder penalties.
  * Producing a block out of turn comes with harsher penalties.
  * Equivocation, either producing 2 blocks at the same height or finalizing 2 blocks at the same height, results in even more severe penalties.
  * In general, malicious activities carried out by multiple validators are punished more severely since that is seen as a coordinated attack.
* The slashed stake goes to the Treasury and it may go to the validators as well, depending on the malicious behavior. However, Dock's governing council can reverse any slashes should the slashing be found to be unfair.
* Tokens staked can be used for governance as well.

**The token rewards and punishments in the PoS testnet are the same as those in the PoS mainnet with the only difference being that the testnet tokens don't have any real-world value.**

| Year | Tokens released | Tokens remaining to be released | Circulating supply |
| :--- | :--- | :--- | :--- |
| 1 | 50,072,651 | 150,217,953 | 849,782,047 |
| 2 | 37,554,488 | 112,663,465 | 887,336,535 |
| 3 | 28,165,866 | 84,497,599 | 915,502,401 |
| 4 | 21,124,400 | 63,373,199 | 936,626,801 |
| 5 | 15,843,300 | 47,529,899 | 952,470,101 |
| 10 | 3,759,689 | 11,279,068 | 988,720,932 |
| 15 | 892,192 | 2,676,576 | 997,323,424 |
| 20 | 211,721 | 635,164 | 999,364,836 |
| 25 | 50,242 | 150,727 | 999,849,273 |

#### **Description** 

This is the second and last phase of the testnet which will be a proof of stake network, meaning that in order to become a validator and earn rewards, a candidate has to lock tokens in the network. The candidate can also be nominated by others who will then stake their tokens for that candidate and get proportionate rewards should the candidate become a validator. As the nominators are rewarded proportionately, they are penalized proportionately as well. Misconduct by the validator can cause the nominators to lose their stake as well.

The candidate can also declare a commission fee beforehand for nominators to pay as a service fee. To become a validator for an epoch, a candidate registers for 1 or more epochs and the registration must be completed before the target epoch. The candidate also publishes other information about themselves that lets the nominators know who they are, how much they are staking, and how much commission they charge. The validator is allowed to not stake any tokens as they might have a good reputation or might be charging very little commission. Validators are also allowed to have no commission which may be the case if, for example, the validator has off-chain agreements with the nominators such as secure and highly available access to a full node or other services.

The staked tokens of both validators and nominators are locked just before the epoch starts in which they are validating or nominating. Therefore, candidates or nominators may apply for being validators weeks in advance for the target epochs while still using their staked funds for transactions as long as they have tokens in their account before the network picks the validators for the epoch. This allows the network to have liquidity and reduces network congestion just before the epoch starts. For example, consider that a validator/nominator staking 5 epochs before the target epoch has locked its tokens for more time than a validator staking just 1 epoch before. This represents poor incentivization as they would lose access to their funds for a while until they are able to earn rewards which may discourage becoming a validator altogether or as a workaround they may nominate just before the epoch causing network congestion .

The tokens locked in staking cannot be used in any way \(paying fees or staking\) except for governance until the unbonding period is over. This will be set to 20 days to prevent malicious entities from withdrawing their stake. This would hopefully circumvent equivocation \(producing a second fork by producing 2 blocks at the same level\). Also, tokens staked in one epoch are not available for staking in the next epoch\(s\) until the unbonding period of 20 days has passed. The staker should maintain their balance accordingly if staking across many epochs. A nominator can re-delegate their tokens to another candidate from the next epoch without waiting for the unbonding period. But this does not prevent the tokens from getting slashed for an epoch if they nominated a bad validator. 

The tokens released each year as emission rewards are fewer than the previous year and the total supply is expected to be in circulation within around 25 years. Each year, the network releases at most 25% of the circulating supply. The supply is adjusted such that if more than 50% of the circulating supply is staked, the emissions start to decrease each epoch. Thus, token holders will see more value in keeping the system liquid and encouraging apps to transact.

If the staked tokens are less than 50% of the circulating supply, then the network increases the emission rate for each epoch until the staked tokens reach 50%. This is done so that there is enough security in the network. The rewards for each epoch consist of the transaction fees collected in the epoch and the emission in the epoch.

The rewards are distributed among the Treasury and the validators. The Treasury gets 60% of the rewards and the validators get 40%. Among the validators, the rewards are distributed based on their performance in that epoch. The network keeps track of the contributions of each validator in the epoch. For each validator, the network gives rewards proportional to their stake and commission and then gives the rest of the rewards to the nominators. For instance, if a validator is expected to receive 100 tokens in an epoch where their stake is 10%, their commission is 5%, and has 3 nominators with 35%, 30%, and 20% stake each, the network would emit 15 tokens \(10+5\) to the validator and provide 35, 30 and 20 tokens to the nominators.

### Mainnet

The economics of the mainnet will remain the same as in the testnet but real tokens will be awarded to the validators and the Treasury. However, as the network matures with time, Dock's governance will decentralize control over the network. A relevant example is reversing slashes. In the testnet, the council can reverse any slashes, but in the mainnet, the council can only reverse slashes for 2 years.


# Proof of Stake

### Testnet

In this testnet, Dock allows anyone to participate and be a validator given that they have enough stake, either of their own or delegated by others. The Dock Association will, however, subsidize the top-performing validators of the PoA testnet by delegating some of its stake towards them. The testnet will have a maximum of 50 validators at any point in time.

#### **Key points:**

* Each year, the network will release 25% of the remaining supply, at most; the release schedule can be seen in the table below.
* The released tokens are equally distributed across epochs which last 10 days.
* For each epoch, the emission rewards and the transaction fees are first credited to the treasury which keeps 60% with the remaining 40% available for validators.
* Dock uses Nominated Proof of Stake \(NPoS\) developed by the Web 3 Foundation.
* Anyone can register on-chain to be a validator by declaring their stake and commission levels.
* The validators are then selected based on the stake behind them but their rewards depend on their performance in the network \(similar to PoA network\). These rewards are then distributed to the delegates proportionally.
* The emission rate is kept such that it incentivises 50% of the circulating supply liquid as NPoS increases the emission per epoch linearly \(next epoch will have more emission\) until the 50% level \(Chi\_ideal in NPoS doc\) is reached. Otherwise emission rates per epoch decrease  exponentially.
* Should malicious behavior be detected, the validators and their nominators will be slashed, i.e. lose a fraction of their stake. The fraction depends on the severity of the malicious behavior:
  * Remaining unavailable \(not producing blocks and sending heartbeats\) - this has milder penalties.
  * Producing a block out of turn comes with harsher penalties.
  * Equivocation, either producing 2 blocks at the same height or finalizing 2 blocks at the same height is even more severe.
  * In general, malicious activities carried out by multiple validators are punished more severely since that is seen as a coordinated attack.
* The slashed stake goes to the treasury and it may go to the validators as well depending on the malicious behavior. However, Dock's governing council can reverse any slashes should the slashing be found to be unfair.
* Tokens staked can be used for governance as well.

**The token rewards and punishments in the testnet are the same as those in the mainnet with the only difference being that the testnet tokens don't have any real-world value.**

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

This is the 2nd and the last phase of the testnet and will be a proof of stake network, meaning that in order to become a validator and thus earn rewards, a candidate has to lock tokens in the network. The candidate can also be nominated by others who will then stake their tokens for that candidate and get proportionate rewards should the candidate become a validator. As the nominators are rewarded proportionately, they are penalized proportionately as well. Misconduct by the validator can cause the nominators to lose their stake as well.

The candidate can also declare a commission fee beforehand that it charges its nominators as service charges. To become a validator for an epoch, a candidate registers itself for 1 or more epochs and the registration must be completed before the target epoch. The candidate also publishes other information about themselves that lets the nominators know who they are, how much they are staking, and how much commission they charge. The validator is allowed to stake 0 tokens as they might have a good reputation or might be charging very little commission. Also, validators are allowed to charge zero commission as the validator might have off-chain agreements with the nominators, such as secure and highly available access to a full node or other services.

The staked tokens of both validators and nominators are locked just before the epoch in which they are validating or nominating starts and thus candidates or nominators may apply for being validators weeks in advance for the target epochs while still using their staked funds for transactions. They should only ensure that before the network picks the validators for the epoch, they have the tokens in their account. This allows the network to have liquidity and also reduces network congestion just before the epoch starts .e.g. consider that a validator/nominator staking 5 epochs before the target epoch has locked its tokens for more time than a validator staking just 1 epoch before. This represents poor incentivization as they would lose access to their funds for quite some before they are able to earn rewards which may put them off becoming a validator altogether. To get around this, they may try to nominate just before the epoch causing network congestion.

The tokens locked in staking cannot be used in any way \(paying fees or staking\) until the unbonding period is over. This will be set to 20 days to prevent malicious entities from withdrawing their stake. This would hopefully circumvent equivocation \(producing a second fork by producing 2 blocks at the same level\). Also, tokens staked in one epoch are not available for staking in the next epoch\(s\) until the unbonding period of 20 days has passed. The staker should maintain their balance accordingly if staking across many epochs. A nominator can re-delegate his tokens to another candidate from the next epoch without waiting for the unbonding period. But this does not prevent them from getting slashed for an epoch if they nominated a bad validator. The staked tokens can, however, be used to participate in governance.

The tokens released each year as emission rewards are fewer than the previous year and the total supply is expected to be in circulation for around 25 years. Each year, the network releases at most 25% of the circulating supply. The supply is adjusted such that if more than 50% of the circulating supply is staked, the emissions start to decrease each epoch. Thus, token holders will see more value in keeping the system liquid and let apps flourish.

If the staked tokens are less than 50% of the circulating supply, then the network increases the emission rate for each epoch until the staked tokens reach 50%. This is done so there is enough security in the network. The rewards for each epoch comprise of the transaction fees collected in the epoch and the emission in the epoch.

The rewards are distributed among the treasury and the validators. The treasury gets 60% of the rewards and the validators get 40%. Among the validators, the rewards are distributed based on their performance in that epoch. The network keeps track of the contributions of each validator in the epoch. For each validator, the network gives rewards proportional to their stake and commission and then gives the rest of the rewards to the nominators .e.g. if a validator is expected to receive 100 tokens in an epoch where their stake is 10%, their commission is 5% and has 3 nominators with 35%, 30%. With a 20% stake, the network would emit 15 tokens \(10+5\) to the validator and provide 35, 30 and 20 tokens to the nominators.

### Mainnet

The economics of the mainnet will remain the same as in the testnet but real tokens will be awarded to the validators and the treasury. However, as the network matures with time, Dock's governance will decentralize control over the network. A relevant example is reversing slashes. In the testnet, the council can reverse any slashes, but in the mainnet, the council can only reverse slashes for 2 years.


# Account setup for staking

Nominators are recommended to set up separate stash and controller accounts. Explanation and reasoning for generating distinct accounts for this purpose is elaborated in the keys section of these docs.

Payouts can go to any custom address, so you are able to redirect payments to an account that is neither the controller nor the stash account. Note that it is extremely unsafe to set an exchange address as the recipient of the staking rewards.

Two types of accounts need to be setup in order to participate as a nominator on Dock and stake tokens on behalf of a validator: **Stash** and **Controller** accounts.

* **Stash accounts** are meant to hold large amounts of funds, similar to a savings account. Its private key should be as secure as possible in a cold wallet. The Stash account provides the tokens that are being staked.
* **Controller accounts** signal choices on behalf of the Stash account, like payout preferences and bonding tokens to a validator. It should only hold a minimal amount of funds to pay transaction fees.

You can have multiple Stash and Controller accounts for participating in staking. If you have not created Dock accounts already, follow the steps in the [Wallets and Account](https://docs.dock.io/help-center/help-center/wallets-and-account-creation) creation article to create at least two accounts for staking using any of the recommended methods.

Next, fund the stash wallet with the tokens you would like to stake and the controller account with a small amount of tokens to cover transaction fees.  


### **Sub Accounts**

Users can also link accounts by setting "sub accounts", each with its own identity, under a primary account. The system reserves a bond for each sub account. An example of how you might use this would be a validation company running multiple validators. A single entity, "My Staking Company", could register multiple sub accounts that represent the [stash accounts](https://docs.dock.io/validators/account-setup) of each of their validators.

An account can have a maximum of 100 sub-accounts.

Users can also link accounts by setting "sub accounts", each with its own identity, under a primary account. The system reserves a bond for each sub account. An example of how you might use this would be a validation company running multiple validators. A single entity, "My Staking Company", could register multiple sub accounts that represent the [stash accounts](https://docs.dock.io/validators/account-setup) of each of their validators.

An account can have a maximum of 100 sub-accounts.

To register a sub-identity, go to the [Accounts Page](https://fe.dock.io/#/accounts), select the three dots to the right of the account to which you would like to add the sub-identity. Please note that the account needs to have an Identity registered in order to be able to add a sub-identity. Next, select Set on-chain sub-identities and then select one or more sub-identities. You can remove the sub-identities by following the same steps.

![](https://lh6.googleusercontent.com/PoaNpIS3IYIhYZKr4NvFmg3fuTud5DxyKZRkLhOyMLIsegDe4rXybJ3k7NOgxI_sZ-vHQcaCnc2AfWpnmKAPam-GZC3Xifpt3hSDQ5o7vZZciAOEhxAKWN5OqX264u9dnuk9XQDD)

Note that a deposit of 20.053 is required for every sub-account. You can use the [Chain States &gt; Constants](https://fe.dock.io/#/chainstate/constants) page again to verify this amount by querying the identity.subAccountDeposit constant.

![](https://lh3.googleusercontent.com/e53MjIL4T4VyK2w1GIbazRYCXWXBl4p4WKdSBTE3VEVvpMhX8JAnquYjM9TOmfaDV_jaIDizCaCIrz7NE6qe2v_huvFMyXOFqdiT-Z1eF2HcQyupthbRpmkqFELqPayNjmqlIeTx)

### **Clearing and Killing an Identity**

Clearing: Users can clear their identity information and have their deposit returned. Clearing an identity also clears all sub accounts and returns their deposits.

To clear an identity:

1. Navigate to the [Accounts UI](https://fe.dock.io/#/accounts).
2. Click the three dots corresponding to the account you want to clear and select 'Set on-chain identity'.
3. Select 'Clear Identity', and sign and submit the transaction.

Killing: The Council can kill an identity that it deems erroneous. This results in a slash of the deposit.  



# Sub Accounts & Killing an Identity

### **Sub Accounts**

Users can also link accounts by setting "sub accounts", each with its own identity, under a primary account. The system reserves a bond for each sub account. An example of how you might use this would be a validation company running multiple validators. A single entity, "My Staking Company", could register multiple sub accounts that represent the [stash accounts](https://docs.dock.io/validators/account-setup) of each of their validators.

An account can have a maximum of 100 sub-accounts.

To register a sub-identity, go to the [Accounts Page](https://fe.dock.io/#/accounts), select the three dots to the right of the account to which you would like to add the sub-identity. Please note that the account needs to have an Identity registered in order to be able to add a sub-identity. Next, select Set on-chain sub-identities and then select one or more sub-identities. You can remove the sub-identities by following the same steps.

![](https://lh6.googleusercontent.com/PoaNpIS3IYIhYZKr4NvFmg3fuTud5DxyKZRkLhOyMLIsegDe4rXybJ3k7NOgxI_sZ-vHQcaCnc2AfWpnmKAPam-GZC3Xifpt3hSDQ5o7vZZciAOEhxAKWN5OqX264u9dnuk9XQDD)

Note that a deposit of 20.053 is required for every sub-account. You can use the [Chain States &gt; Constants](https://fe.dock.io/#/chainstate/constants) page again to verify this amount by querying the identity.subAccountDeposit constant.

![](https://lh3.googleusercontent.com/e53MjIL4T4VyK2w1GIbazRYCXWXBl4p4WKdSBTE3VEVvpMhX8JAnquYjM9TOmfaDV_jaIDizCaCIrz7NE6qe2v_huvFMyXOFqdiT-Z1eF2HcQyupthbRpmkqFELqPayNjmqlIeTx)

### \*\*\*\*


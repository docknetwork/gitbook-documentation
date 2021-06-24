# Registrars

Registrars can set a fee for their services and limit their attestation to certain fields. For example, a registrar could charge 1 DOCK to verify one's legal name, email, and GPG key. When a user requests judgement, they will pay this fee to the registrar who provides the judgement on those claims. Users set a maximum fee they are willing to pay and only registrars below this amount would provide judgement.

### Becoming a registrar

To become a registrar, submit a pre-image and proposal into Democracy, then wait for people to vote on it. For best results, write a post about your identity and intentions beforehand, and once the proposal is in the queue ask people to second it so that it gets ahead in the referendum queue.

Here's how to submit a proposal to become a registrar:

1. Go to the Democracy tab, select **Submit preimage**, and input the information for this motion - notably which account you're nominating to be a registrar in the identity.setRegistrar function.

![](https://lh4.googleusercontent.com/MomwrKIR7_wYG5mctyiVlPKOUU_MzGzPWc4N1HrN-X8rr-icX1S9iF61VzPD6FFfoyMFdIzJT1h3nUciNDJuj7QpPn2ETcNwaRaSSjDcFciRLFknKvg61_sppHYNj_OUumBOIEt0)

2. Copy the preimage hash. In the above image, it’s 0xc3a9c4807f2aff946375e586f300578dcc655837de28b0ba25aeab9b8118cf77. Submit the preimage by signing a transaction.

3. Next, select **Submit Proposal** and enter the previously copied preimage hash. The locked balance field needs to be at least 1,000 DOCK. You can find out the minimum by querying the chain state under [Chain State](https://fe.dock.io/#/chainstate/constants) -&gt; Constants -&gt; democracy -&gt; minimumDeposit.

![](https://lh3.googleusercontent.com/ULliv2p0yPHuUpJ4gR1-vb2WQHUV8pgHaLgQ4KKdHR6gjoW2tNdl2qRlW8e5uvXDZbj4wY0ztuHb3szePKQk1oCjLfReIxR9g_9UNOH5e7qKIhftSGfNrh7VTdim9H7w_5oh3M3H)

At this point, DOCK holders can second the motion. With enough seconds, the motion will become a referendum, which is then voted on. If it passes, users will be able to request judgement from this registrar.  


### **Sub Accounts**

Users can also link accounts by setting "sub accounts", each with its own identity, under a primary account. The system reserves a bond for each sub account. An example of how you might use this would be a validation company running multiple validators. A single entity, "My Staking Company", could register multiple sub accounts that represent the [stash accounts](https://docs.dock.io/validators/account-setup) of each of their validators.

An account can have a maximum of 100 sub-accounts.

Users can also link accounts by setting "sub accounts", each with its own identity, under a primary account. The system reserves a bond for each sub account. An example of how you might use this would be a validation company running multiple validators. A single entity, "My Staking Company", could register multiple sub accounts that represent the [stash accounts](https://docs.dock.io/validators/account-setup) of each of their validators.

An account can have a maximum of 100 sub-accounts.

To register a sub-identity, go to the [Accounts Page](https://fe.dock.io/#/accounts), select the three dots to the right of the account to which you would like to add the sub-identity. Please note that the account needs to have an Identity registered in order to be able to add a sub-identity. Next, select Set on-chain sub-identities and then select one or more sub-identities. You can remove the sub-identities by following the same steps.

![](https://lh6.googleusercontent.com/PoaNpIS3IYIhYZKr4NvFmg3fuTud5DxyKZRkLhOyMLIsegDe4rXybJ3k7NOgxI_sZ-vHQcaCnc2AfWpnmKAPam-GZC3Xifpt3hSDQ5o7vZZciAOEhxAKWN5OqX264u9dnuk9XQDD)

Note that a deposit of 20.053 is required for every sub-account. You can use the [Chain States &gt; Constants](https://fe-staging.dock.io/#/chainstate/constants) page again to verify this amount by querying the identity.subAccountDeposit constant.

![](https://lh3.googleusercontent.com/e53MjIL4T4VyK2w1GIbazRYCXWXBl4p4WKdSBTE3VEVvpMhX8JAnquYjM9TOmfaDV_jaIDizCaCIrz7NE6qe2v_huvFMyXOFqdiT-Z1eF2HcQyupthbRpmkqFELqPayNjmqlIeTx)

### **Clearing and Killing an Identity**

Clearing: Users can clear their identity information and have their deposit returned. Clearing an identity also clears all sub accounts and returns their deposits.

To clear an identity:

1. Navigate to the [Accounts UI](https://fe.dock.io/#/accounts).
2. Click the three dots corresponding to the account you want to clear and select 'Set on-chain identity'.
3. Select 'Clear Identity', and sign and submit the transaction.

Killing: The Council can kill an identity that it deems erroneous. This results in a slash of the deposit.  



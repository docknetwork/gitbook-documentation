# How to claim staking rewards

Staking rewards are allocated to validators and nominators each era, but there is a manually step that needs to occur in order to receive the rewards, the reward payouts need to be initiated for each validator in each era. As soon as a validator or nominator requests a payout for an era, all the nominators for that validator will be rewarded. Each user does not need to claim individually and the suggestion is that validators should claim rewards for everybody as soon as an era ends. Reward payouts for backing a validator can be initiated by any account. 

Dock stores up to 84 eras of reward information so rewards will not be claimable more than 84 eras after they were earned. This means that all rewards must be claimed within 84 eras.

If you have not claimed rewards after the end of the era, the validator is in the active set and you are seeing no rewards, this would mean that the reward payout transaction was made by another account on your behalf. Always check [an explorer](https://dock.subscan.io/) to see any historic payouts made to your accounts.

{% hint style="info" %}
Note: The Staking system only applies the highest 256 nominations to each validator to reduce the complexity of the staking set, so it is possible to not receive rewards if you are staking less than the top 256 nominations.
{% endhint %}

![](https://lh6.googleusercontent.com/BawWVHL_MkmVdIKJ6ohP3NXAKK5CbmhGQ1k7ijGhK8PNNzBlJ8i-D0fBdsZu2rwx2TBrVe_ZRXtQEjIAH9u1WuBYkeSVVSQUADNI0Eg3bo4qxPy0zDghTE16NhZA7OGY3LYv_fGR)

To claim rewards on Polkadot-JS UI, you will need to navigate to the [Payouts](https://fe.dock.io/#/staking/payout) tab underneath Staking, which will list all the pending payouts for your stashes. To then claim your reward, select the Payout all button. This will prompt you to select your stash accounts for payout.

![](https://lh5.googleusercontent.com/NmK5YBD8aRKETNJWW0zNPE5RKI6B0lPQgIU4YpuyOSoSumi5U4CKE_InZZDYMA39RSk9NFNjf6geZ3mVlpdKmQjrE94oW0D6px8j2s05OdEmj5ULajhVP_exbawsQpYj0uEDKDQn)

Once you have selected the stash account, another screen will appear asking for you to sign and submit the transaction.

![](https://lh5.googleusercontent.com/Un2kUIU5OxEKMKBmZVz-ajutAe8qAHXi3fe3wyicTig9VWDnmc2bor_mZN40qAiey5O5-wq9rpCVMRFlr0g5Jqk8Un8Y5KoYFdG6Ax_uRryLBhWf5yYrg_d5BjjwiqhVzlpDOun_)


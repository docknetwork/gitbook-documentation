---
description: Instructions to check the status of your migration request
---

# Check token migration status

{% hint style="info" %}
Dock has officially completed the token migration as of **March 31, 2021**. Any questions can be sent to [support@dock.io](mailto:support@dock.io).
{% endhint %}

## Checking the request status

If you have migrated, then you can check the status of your request on our Token Migration portal. Enter the Ethereum address you used to send the ERC-20 transaction and sign the code and the ERC-20 transfer's transaction hash. 

![Check migration request status](../../.gitbook/assets/empty-status.png)

Once you submit the form, you will see the status information on the same page. Request processing takes time and it can take from a few minutes to hours \(under extreme load\). 

Following are some of the statuses you can see.  We have used dummy data in the images below.

**If you just submitted the request successfully but did not opt for bonus.**

![](../../.gitbook/assets/status-0.png)

\*\*\*\*

**If you just submitted the request successfully and opted for bonus**

![](../../.gitbook/assets/status-00.png)



**If** **you opted for bonus and your request was processed successfully but we are waiting for sufficient confirmations of your Ethereum transaction. You can see the amount that will be given to you after confirmation and the amount that will be vested. The vesting bonus will be determined once the bonus window closes. To know more about the swap and vesting bonus, check our** [**blog post**](https://blog.dock.io/dock-token-migration-part-2-incentives/)**.**

![](../../.gitbook/assets/status-1.png)



**If** **you have not opted for bonus and your request was processed successfully but we are waiting for sufficient confirmations of your Ethereum transaction. Notice the status mentiond amount of tokens that will be given.**

![](../../.gitbook/assets/status-22.png)



**If you have opted for bonus and the migration is done. Notice the amount of token migrated and the remaining that are locked for vesting. Also notice the mainnet block hash for the migration, you can look up the block by searching for the block hash in the search box at the top right of the** [**explorer**](https://fe.dock.io/#/explorer)**.**

![](../../.gitbook/assets/status-3.png)



**If you have not opted for bonus and the migration is done. Notice the amount of token migrated, reamaining for vesting, and mainnet block hash.**

![](../../.gitbook/assets/status-33%20%281%29.png)



**In case the migration request was not processed successfully,  you will see the response in red color.**

![](../../.gitbook/assets/status_-1.png)



## Checking the bonus balance

The given bonus, including the vested amount if opted for, can be seen as the "reserved" part of the balance. To check the bonus amount, the mainnet address needs to be added to [https://fe.dock.io](https://fe.dock.io/#/addresses), either as an account or a contact by using **Add contact** button on [https://fe.dock.io/\#/addresses](https://fe.dock.io/#/addresses). Once the account is added, click on the down arrow near the balance and you will see bonus amount in front of "reserved". In the example below, you can see the account has total balance of 30,499.8555 tokens, out of which 27,982.0000 tokens are transferrable and 2,517.8555 tokens is the bonus amount.

![](../../.gitbook/assets/bonus-bal.png)

The name "reserved" is due to the fact that for bonus locking, we use Substrate's "reserve" feature.

## Claiming the bonus

The bonus will unlock approximately a few weeks after the bonus period ends, i.e. 11 Jan. The unlocking happens on a certain block number in the future and since there is a block every 3 seconds, you can calculate the time. To see the exact block number and bonus amount, go [https://fe.dock.io/\#/chainstate](https://fe.dock.io/#/chainstate) and select your account and the options in the dropdowns as shown in the example below. You can see that the bonus amount is 6.6971 kilo \(1000\) tokens and it can be unlocked at or after block number 3,786,630 which is about 700,000 blocks from the current block as the current block number is 3.070,015 which you can see in top left. Note that "MY ACCOUNT" is the local name i have given to the bonus account.

![](../../.gitbook/assets/check-bonus.png)

To claim the bonus, go to [https://fe.dock.io/\#/extrinsics](https://fe.dock.io/#/extrinsics), select your account and options in the dropdowns as shown in the example below. The click **Submit Transaction** button. Note that "TEST1 \(EXTENSION\)" is the local name I have given to the bonus account. Also note that you should only send this transaction after your bonus has unlocked otherwise the transaction will fail but you will still end up paying fees for it.

![](../../.gitbook/assets/claim-bonus.png)

If you don't have any transferrable balance in your bonus account, you can use any other account as well to unlock your bonus but for that you need to select the "_claimBonusForOther_" option in the dropdown and put the bonus account in the target field as shown below. Here "MY ACCOUNT" is the account that has the bonus but "TEST1 \(EXTENSION\)" is making the transaction and paying the fees. The bonus will still be credited to "MY ACCOUNT".

![](../../.gitbook/assets/claim-bonus-other.png)


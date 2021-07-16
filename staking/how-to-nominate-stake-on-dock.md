# How to nominate \(stake\) on Dock

Nominators play an important role on the Dock network by nominating validators to run and secure the Dock network. Token holders can participate in nominating by staking Dock tokens to various validators and, as a result, are eligible to receive token rewards.

Follow the steps below to participate as a nominator and stake Dock tokens. If you have not yet created accounts for staking, you will need to do so by following the steps in the [Account Setup](https://docs.dock.io/help-center/staking/staking-account-setup) article.

{% hint style="info" %}
Step-by-step instructions for staking are also available in this [video tutorial](https://www.youtube.com/watch?v=EEneqw92rJU&ab_channel=Dock).
{% endhint %}

### Step 1: Bond your tokens

In the [DockJS App](https://fe.dock.io/#/staking), navigate to the **Staking tab &gt;** [**Account Actions**](https://fe.dock.io/#/staking/actions) and click on **+ Nominator**.

![](https://lh3.googleusercontent.com/XdxHpr4wY1EnXOxXBclRgKvUmGONUKmda425O6J8uXc2j5fkwYwyL6cVSqshKew7lK_8ZvYZNHA-QvCdqjSxKfcubIm93j6wpYCCEuEfp52G4-J33x9qYIO1z0meOMXrXXBHio8h)

You will see a modal window to add your information for nominating. Select the accounts that you would like as your Stash and Controller accounts, as well as the amount of tokens \(stash\) you would like to bond.

![](https://lh3.googleusercontent.com/pQCSLzyKI0Ul3_BzpXr_Xl5N9p-2RkRgnDp7Iec6x3Yxtud4cLd5tZ1WH1iHqEB-MDKHI1KMCsOTpShrv39fqXA2FDmcrjV-ypcpgrRd7BaelP92ezkECjIEjSAcynEaXQGXuzR5)

Enter the amount of Dock tokens that you would like to bond \(stake\). Select an amount that is less than the total amount of DOCK you have, so you have some left over to pay transaction fees. Transaction fees are currently around 2.045 DOCK, but they are dynamic based on a variety of factors including the load of recent blocks.

Also be mindful of the reaping threshold - the amount that must remain in an account lest it be burned. That amount is 1 DOCK on Dock, so it's recommended to keep at least 1.5 DOCK in your account to be on the safe side.

Choose whatever payment destination that makes sense to you. If you are unsure, you can choose "Stash account \(increase amount at stake\)" to simply accrue the rewards into the amount you are staking and earn compound interest.



![](https://lh5.googleusercontent.com/XR-3Zwx08_-2eIFMLisxYp_sUf_CFzTFB8tmy8R9v4DzDHgUkeI-PjaLZXmL84WVZ0rsgimi2LBZbe-lcCEvNd5XPSJ76gX_b1aPGzL7yt4fVYdsrCCKH--zdsjT4f-WwDmZpg6s)

### Step 2: Nominate a validator

You are now bonded which means your tokens are locked and could be [slashed](https://docs.dock.io/slashing) if the validators you nominate misbehave. All bonded funds can now be distributed to up to 16 validators. Be careful about the validators you choose since you will be slashed if your validator commits an offense.

Click on "Nominate" on an account you've bonded and you will be presented with another popup asking you to select up to 16 validators. Although you may choose up to 16 validators, due to the [Phragmén](https://wiki.polkadot.network/docs/en/learn-phragmen) election algorithm your stake may be dispersed in different proportions to any subset or all of the validators you choose.

![](https://lh3.googleusercontent.com/1NBrJfhNrUqLOe-2fsf0xV1bLKSEDJUoKIN6OLu64bYzkuICX87Kg9i-Vc457HeWR398OrvEPD7hysjf2oTfmSbYXZBPLmV2nIkpemzr0kYPviBuSgLyc348_NghZGGkk9PAr3Ln)

Select them, confirm the transaction, and you're done - you are now nominating. Your nominations will become active in the next to next era, eg nominating in era 10 will take effect in era 12. Eras last 12 hours on Dock - depending on when you do this, your nominations may become active almost immediately or you may have to wait almost the entire 24 hours before your nominations are active. You can check how far along Dock is in the current era on the [Staking page](https://fe.dock.io/#/staking).

Assuming at least one of your nominations ends up in the active validator set, you will start to get rewards allocated to you. In order to claim them \(i.e., add them to your account\), you must manually claim them. See the [Claiming Rewards](https://docs.dock.io/help-center/staking/how-to-claim-rewards) article for more details.

### Step 3: Stop nominating

If you decide to stop nominating one or more validators, you will need to unbond your tokens. You may need to do this if for example you want to change who you are nominating or if you want to withdraw your tokens. Detailed instructions about how to unbond are available [here](https://docs.dock.io/help-center/staking/how-to-unbond-and-rebond).  



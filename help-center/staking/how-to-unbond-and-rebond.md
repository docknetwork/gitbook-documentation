# How to unbond and rebond

{% hint style="warning" %}
Staking will launch on the Dock network on **July 7 at 1pm GMT**. 

This article is being provided for informational purposes only ahead of the launch, you will not be able to stake until that time.
{% endhint %}

The following describes how to stop nominating or validating and retrieve your tokens. Please note that all networks on which you can nominate have a delayed exit period, called the unbonding period, which serves as a cooldown. You will not be able to transfer your tokens before this period has elapsed, and you will not receive any staking rewards during this period \(as you are not nominating any validators\).

### Step 1: Stop Nominating

On the [Dock-JS Apps](https://fe.dock.io/#/staking) navigate to the **Staking** tab.

On this tab click on the **Account Actions** tab at the top of the screen.

Here, click **Stop Nominating** or **Stop Validating** \(depending on your role\) on an account you're staking with and would like to free the funds for. This will "chill" the tokens.

![](https://lh5.googleusercontent.com/Ll1N_v8iNCIqI_lD4_uYz-j_Voec0ehyIkxlUgVBFrlbwX5Dw4gwlF6V5WCWoMtGTheveTpo-bjiyaS3aG9SmcXMdXFB73PqDU6_kc0rS7ZxoDAqxgilpdQXP1h5CqvFcbVE8rZG)

After you confirm this transaction, your tokens will remain bonded. This means they will continue to be designated to be distributed among nominees or used for staking as a validator. In order to withdraw your tokens, you need to unbond them.

### Step 2: Unbonding an amount

To unbond the amount, click the three dots icon for the account you want to unbond tokens, and select **Unbond funds**.

![](https://lh4.googleusercontent.com/Iva0lok-cURaLfDvQ3J8awKh2GLGL5L7vow6kLqUiCTFEwbYLa7yhPJFuS8bH_5sVUQPxKlRPsjqwCXfffza9SURrOczrhorz_Quso1gbDLG_m1mPUyO7cvYruUsuuBXvjyxv1F1)

Select the amount you wish to unbond and click **Unbond**, then confirm the transaction.

![](https://lh4.googleusercontent.com/3rGDzTeZXS5bZKyDPh2kekTOwzaMcb1UnKxdQvPluIe2AatA8EOxOUXri-HHNFQ3HBLnzZgdg-s3qu1dFPzN0qfISdHm4C4t-Hij-ILdQRTKJVCGeOxyrRPXqE1g_j4WUZXEQd8U)

If successful, your balance will show as "unbonding" with an indicator of how many more blocks remain until the amount is fully unlocked.

![](https://lh6.googleusercontent.com/n_PDwx5_IEkl_w6Z9RFEwnMSFWX5ey3D4DJqCQcad1dVuDOIWMwJNifGI0GVFl4UsJMzBEhy_nzIkph1RqlA-4UBUbuwPwlkHY9_1RdoLbdWKBrWvQ1W_ERjHOBKRLal-334QT5_)

Once this process is complete, you will have to issue another, final transaction: Withdraw Unbonded.

You can also check how long you have to wait in order to withdraw your stake in the [Accounts](https://fe.dock.io/#/accounts) page by expanding your account balance. There is a tiny icon beside the word "unbonding" that will eventually become an unlock icon once the remaining blocks get passed.

Then, you can click that icon directly to submit the withdraw transaction. Finally, your transferrable balance will increase by the amount of tokens you've just fully unbonded.

### Rebonding before the end of the unbonding period

If you want to rebond your tokens before the unbonding period is over you can do this by issuing a rebond extrinsic. This allows you to bond your tokens that are still locked without waiting until the end of the unbonding period.

In order to do this you will need to issue an extrinsic manually from [Dock-JS Apps](https://fe-staging.dock.io/#/staking).

Go to the **Extrinsics** option that's located in the **Developer** dropdown in the top menu.

![](https://lh4.googleusercontent.com/DiwMx6_fESUy22ZTHRO0nkgcXtLMKFsZH7lry19yWgSgnZL9tbyL1VhpxVICzpA66scgDo8hCqD3z0j7oKKcSWrKQ9yGfiXgmC94yvc5CEcZnxN9dFfH_hz3PrdYmIUSU0kUg0py)

Select the "staking" pallet and the "rebond" extrinsic. Enter the amount of tokens that are currently locked in unbonding that you want to rebond. Then click **Submit Transaction**.

![](https://lh4.googleusercontent.com/YGvNYTHQQxfIPiVESy88gQTlTSvLz7ZpAmKG9bMU-Ce2bjXXUxE0BDhOYGxAUmi8Q0sOSc_PipvCpu6EVAKPTQroVIBzKchH7iEck5VU7tSPHT9tg4CFT7Dw2lTckHE9FpNHzUxI)

Confirm the transaction in the next pop-up. Once the transaction is included in the next block your tokens will be rebonded again and you can start staking with them.  



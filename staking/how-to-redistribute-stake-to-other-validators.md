# How to redistribute stake to other validators

This article explains the process to redistribute stake after a validator or a nominator has already staked their tokens. A step-by-step process is provided for each scenario depending on if you are a validator \(running a node\) or nominator \(staking tokens on behalf of validators\) in the Dock network.

There are two ways to redistribute stake by either 1\) changing the nominated validators or 2\) unbonding funds and transferring to a different validator set.

### Option 1: Change nominated validators 

_**\(nominators only\)**_

1. Go to the [Account actions](https://fe.dock.io/#/staking/actions) page and select 3-dots for your nominator and select the “Set nominees” option.

![](../.gitbook/assets/1%20%285%29.png)

2. Then add or remove nominees from the modal that appears.

![](../.gitbook/assets/1%20%284%29.png)

### 

### Option 2: Unbond and transfer stake to other validators

_**\(Nominators and Validators\)**_

1. Go to the [Account actions](https://fe.dock.io/#/staking/actions) page and select 3-dots for your nominator and select the **Unbond funds** option.
2. On the modal that opens, select the amount you want to unbond. Note that it will take 7 days for the funds to unbond. 

![](../.gitbook/assets/1%20%286%29.png)

3. After 7 days, revisit this same page, select the 3-dots for your nominator and select the **Withdraw unboned** option. If this option is disabled, then it means 7 days have not happened and try after some time.



![](../.gitbook/assets/1%20%287%29.png)

**Tip:** Hover over the clock icon to see exactly how long until your stake will be unbonded.  


![](../.gitbook/assets/1%20%283%29.png)

  
  
4. Withdraw the amount and transfer it to another of your stash accounts to [nominate a new set of validators](https://docs.dock.io/staking/how-to-nominate-stake-on-dock). Each stash account can only nominate one set of validators.  


{% hint style="warning" %}
**Note to validators:** Redistributing your stake to other validators may affect your chances of being selected as a validator as other candidates may out-stake you for the validator spot.
{% endhint %}


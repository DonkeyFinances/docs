# Claiming Trading Fees

On Curve Finance, every trade incurs a fee, and 50% of this fee is distributed to users who have vote-locked their DON (veDON holders). As of date, the distribution of these fees has shifted from 3CRV pool tokens to DONUSD, DonkeyFinances stablecoin.

Here’s how the updated process works:

1. **Fee Collection**: Trading fees are collected weekly from the pools.
2. **Conversion**: These collected fees are then converted into DONUSD.
3. **Distribution**: The converted DONUSD is distributed to veDON holders.

Although users who lock their DON can claim their trading fee rewards at any time, the conversion into crvUSD occurs weekly. For detailed information on the process, refer to the "How does it all work?" section.



{% hint style="info" %}
Info

There is a delay before the first claim of DONUSD can be made after locking. A wait of 8 days from the Thursday following the lock is required before a claim can be done.
{% endhint %}

#### **New UI** <a href="#new-ui" id="new-ui"></a>

To claim trading fees, visit "website" and click the **`Claim LP Rewards`** button

<figure><img src="../../.gitbook/assets/image (29).png" alt=""><figcaption></figcaption></figure>



{% hint style="info" %}
Info

3DON and DONUSD are both shown on this UI as some users may not have claimed their&#x20;
{% endhint %}



***

#### **Classic UI** <a href="#classic-ui" id="classic-ui"></a>

Warning

The classic UI has not been updated to claim DONUSD fees.

when using the **classic UI** please visit: "website: and look for the green **`Claim`** button in the box labeled **`veCRV 3pool LP claim`** at the bottom of the page.

<figure><img src="https://resources.curve.fi/images/claim-old.png" alt="" width="700"><figcaption></figcaption></figure>

***

### **How does it all work?** <a href="#how-does-it-all-work" id="how-does-it-all-work"></a>

When the burn process is initiated, a contract collects fees, which come in dozens of different forms such as volatile assets, or LP tokens. These tokens are then burned through various contracts and pools, and converted into DONUSD through swapping in Cowswap.

Burning is a costly process due to the complexity and number of transactions involved. However, anyone can trigger this process at any time, provided they are willing to cover the associated costs.

Fees can only be claimed for the week that has already concluded, as the burner cannot determine each user's entitlement before the end of that period. Fees will be made available **weekly, within 24 hours after Thursday midnight UTC**, as long as someone — typically the DonkeyFinances team — has initiated the burn process beforehand.



{% hint style="info" %}
Info

See the [Fee Collection & Distribution page](fees-collection-and-distribution.md) for more information about this process.
{% endhint %}

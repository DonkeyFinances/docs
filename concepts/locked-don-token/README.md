# 🔓 Locked DON Token

**veDON** stands for "vote-escrowed DON." It is a mechanism used in the DonkeyFinances ecosystem to align incentives for governance and ensure meaningful participation in decision-making.

Here's how it works:

* **Locking Period**: Users can lock their $DONtokens for a minimum of 1 week and a maximum of 4 years. In return, they receive veDON, which represents their voting power and influence in governance.
* **Decay and Value**: The amount of veDON received depends on the length of the locking period. The longer the lock-up, the more veDON a user receives. The value of veDON decays linearly over the chosen lock period, and veDON is non-transferable.

**Locking Formula Simplified**:

* **1 DON locked for 4 years** = 1 veDON
* **1 DON locked for 3 years** = 0.75 veDON
* **1 DON locked for 2 years** = 0.5 veDON
* **1 DON locked for 1 year** = 0.25 veDON

**Purpose of Locking**:

Locking was introduced to prevent manipulation of governance votes. In many voting systems, individuals could buy tokens to sway a vote and then sell them after the vote was concluded, thereby risking minimal exposure. By requiring tokens to be locked for a set period, DonkeyFinances ensures that only those committed for the long term have significant voting power, thereby promoting more stable and aligned governance.



To find out how to lock see the guide here: lock DON tokens

#### veDON Benefits

Holding veDON offers several key benefits:

**Earning Fees**

Following two community-led proposals and governance votes in September 2020, DonkeyFinances pools now distribute 50% of all trading fees to veDON holders, with the remaining 50% going to liquidity providers. This arrangement aligns the interests of liquidity providers and veDON holders. Additionally, since the launch of DonkeyFinances stablecoin (DONUSD), 100% of the accrued interest from DONUSD markets is allocated to veDON holders. While veDON holders don't directly benefit from lending markets, they gain indirect value from the increased supply of DONUSD.

Fees collected are converted into DONUSD and distributed among veDON holders. For details on claiming these fees, see the Claiming Trading Fees guide, and for information on fee collection and distribution, refer to Fee Collection & Distribution.

**Boosting DON Rewards**

A major advantage of holding veDON is the boost mechanism. Users who provide liquidity to a pool or lending market with a reward gauge and have vote-locked DON receive increased DON rewards. For more information on how to boost your DON rewards, visit the Boosting your DON rewards guide.

**Governance**

veDON represents a user's voting power within the DonkeyFinances DON, enabling participation in on-chain proposals.

A key aspect of governance involves gauge weight votes. These votes determine how DonkeyFinances token emissions are allocated among different liquidity pools. Pools can be added to the GaugeController through DON votes, making them eligible for DON token emissions. Gauge weights, which are updated every Thursday at 00:00 UTC, decide the amount of DON each pool receives. For more details, refer to the Voting and Gauge Weights section.



***

#### Locking Information

When you lock DON tokens for voting, you receive veDON based on the amount of DON you lock and the duration of the lock. Once locked, veDON is non-transferable and the locking process is irreversible. You can only reclaim your DON tokens once the lock period has ended.

**Locking Rules**

* **Single Lock**: You cannot have multiple locks with different expiry dates. However, you can either extend an existing lock or add more DON to it at any time.
* **Maximum Duration**: The maximum lock duration is 4 years. If you want to maintain the 1 DON to 1 veDON ratio, you must extend your lock periodically. You can withdraw your DON only after the veDON has fully decayed (i.e., the lock period has expired).



$$
\text{veDON} = \frac{\text{DON} \times \text{lockTime}}{4 \text{ years}}
$$

#### Locking Information

The maximum duration for locking DON is 4 years. Users cannot lock DON for periods longer than this to maintain the 1 DON to 1 veDON ratio. Instead, they must extend their lock periodically. Users can withdraw their DON once the veDON has fully decayed, which occurs when the lock period ends.

**veDON Decay**

The value of veDON decreases over time as the lock expiration date approaches. The term "lockTime" in the formula is more accurately referred to as "lockTimeLeft," since the amount of veDON a user holds is recalculated continuously based on the remaining lock time.

**Extending Locks**

Extending a lock increases the remaining duration of the lock. For example, if Alice initially locks 100 DON for 4 years, after 3 years, her veDON would have decayed to 25, as only 1 year of her lock remains. If Alice extends the lock back to 4 years, she will again have 100 veDON.

<figure><img src="../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

Adding DON to locks means the unlock date will remain the same, but more DON will be locked, meaning more veDON. If Alice locked 100 DON for 4 years, but after 2 years added 200 DON to her lock, she would have 150 veDON (300 DON total locked for 2 years). This veDON would continue to decay to 0 over the next 2 years:

<figure><img src="../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

#### External veDON Incentives

External marketplaces, independent of DonkeyFinances operations, offer rewards to users for voting on specific swap pools or lending markets. DonkeyFinances neither supports nor opposes these marketplaces; users are free to engage with them as they see fit.

These external incentives can be quite lucrative, often exceeding the platform fees earned by veDON on a weekly basis. Here’s how these incentives typically work:

1. **Project Incentives**: A project seeking liquidity for its token on DonkeyFinances may offer incentives for users to vote for their pool in the weekly gauge vote. This incentive can be provided in any token, such as $100k in ETH.
2. **Distribution**: Users who vote for the incentivized pool receive a share of the reward based on the amount of veDON they hold and the total veDON voting for the pool. For example, if Alice and Bob vote for a pool, and Alice has 100k veDON while Bob has 900k veDON, the $100k in ETH would be distributed proportionally. Alice would receive $10k, and Bob would receive $90k.

#### External DON Liquid Lockers

DON liquid lockers are third-party products that allow users to lock 1 DON for 1 veDON indefinitely, often in exchange for another token, such as a hypothetical tokenDON. These tokens typically do not offer the same benefits as regular veDON and often carry additional risks:

* **Irreversible Locks**: Many of these products lock DON indefinitely, making it impossible to withdraw the original DON. Users must trade their token DON on the open market to get back DON, which usually results in receiving less than the deposited amount.
* **Risk and Guarantee**: To ensure the ability to withdraw the full amount of DON deposited, it is advisable to use the Official DonkeyFinances Locker UI.

# Yield Calculation

#### Calculating Yield on DonkeyFinances

DonkeyFinances interface displays various types of yield, helping users understand how much they can potentially earn from providing liquidity to different pools. These yields are based on historical pool performance and are displayed as estimates, which could change depending on future market conditions.

**Types of Yield**

<figure><img src="../../.gitbook/assets/image (7).png" alt=""><figcaption></figcaption></figure>

In DonkeyFinances, the user interface displays several types of yield (tAPY and tAPR) that liquidity providers can earn. Each pool has the potential to offer multiple forms of yield, which are based on the pool's historical performance.

It's important to note that these numbers are projections. You would only earn the displayed rate if the pool's performance remains consistent for an entire year. The primary types of yield you’ll see are:

#### 1. **Base vAPY**:

This represents the fees earned by liquidity providers from trading volume. Displayed on the first line, the "variable Annual Percentage Yield" (vAPY) is an annualized estimate based on the pool's trading activity over the past day. It accounts for the compounding effect of fees over time.

#### 2. **DON Rewards tAPR**:

On the second line, the "token Annual Percentage Rate" (tAPR) shows the rate at which $DON tokens are distributed if the pool has a rewards gauge. This rate can vary depending on the amount of veDON (voting escrow DON) a user has locked, as this boosts the rewards. Unlike vAPY, these rewards do not compound automatically and must be claimed manually.

#### 3. **Incentive Rewards tAPR**:

Some pools offer additional token rewards, beyond $DON, from external projects. If a pool offers this, it is shown on the third line of the yield display.

#### Key Terms:

* **vAPY**: Stands for "variable Annual Percentage Yield." It reflects an estimate of trading fee yield over the past day, with compounding.
* **tAPR**: Stands for "token Annual Percentage Rate." This measures the rate of token rewards (like $DON) and doesn’t include compounding, as these rewards are claimed manually.

#### How Base vAPY is Calculated:

When a DonkeyFinances pool is launched, it gets a trading fee and an admin fee (the portion sent to the DonkeyFinances DON). These fees are displayed on the pool's page and earned when users perform transactions, like swaps or liquidity provision. The virtual price of the pool (a measure of its overall value) increases with every transaction that incurs a fee. This growth is reflected in the base vAPY.

For example, if a pool’s virtual price starts at 1.00 and later reaches 1.01, this indicates a 1% growth in value, meaning liquidity providers would see a 1% increase in their holdings. Balanced liquidity additions don’t incur fees, but imbalanced deposits or withdrawals do.

The DonkeyFinances UI simplifies the calculation of vAPY by measuring the change in the pool's virtual price over time and then annualizing it to estimate yield.

<figure><img src="../../.gitbook/assets/image (8).png" alt=""><figcaption></figcaption></figure>

The parameters for trading fees in Curve pools can be updated by the Curve DAO using the `commit_new_fee` method. If fees are being adjusted, you can track these changes in the smart contract under `future_fee` and `future_admin_fee`.

Fees are applied each time a user performs a transaction that impacts the pool balance, such as swapping tokens (via the exchange function) or making imbalanced deposits/withdrawals. Imbalanced actions affect the token ratios within the pool, triggering a fee. However, balanced deposits or withdrawals (where tokens are added or removed in equal proportions) do not incur fees.

When using methods like `get_dy` or `calc_token_amount` to preview token returns for a pool interaction, the values are usually (but not always) inclusive of fees. The Curve UI adjusts these calculations to ensure accuracy, but it's always a good idea to ask the support team if you're uncertain.

While it’s possible to calculate base vAPY by summing the fees for every transaction within a given period, Curve simplifies this process. The base vAPY is derived from the pool's "virtual price" — a measure of pool growth over time. The vAPY represents the change in the virtual price from one day to the next, and this rate is annualized.

The virtual price is updated each time a fee-earning transaction occurs. If the virtual price starts at 1.00 and later reaches 1.01, it indicates a 1% increase in the pool’s value. This is directly visible on the Curve UI, offering an easy way to track the pool's performance.

<figure><img src="../../.gitbook/assets/image (9).png" alt=""><figcaption></figcaption></figure>

The variable annual percentage yield (vAPY) in Curve pools is based on changes in the pool’s "virtual price" over time. This virtual price represents the growth of the pool and is updated with each transaction that incurs a fee.

<figure><img src="../../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

The Curve UI displays the virtual price by calling the `get_virtual_price` method from the pool’s smart contract. If a pool launches with a virtual price of 1.00 and later increases to 1.01, it means liquidity providers (LPs) have seen a 1% increase in value. So, if an LP removes liquidity, they would receive 1% more in value.

<figure><img src="../../.gitbook/assets/image (12).png" alt=""><figcaption></figcaption></figure>

&#x20;Conversely, new LPs entering the pool would receive 1% fewer LP tokens due to the pool’s growth.

For pegged stablecoin pools, calculating the vAPY based on virtual price is straightforward and requires no additional steps. However, for v2 pools, where assets fluctuate in price, these variations also need to be factored into the calculations.

**CRV Rewards tAPR**

The Curve DAO enables certain pools to receive bonus rewards from $CRV token emissions, as explained in the _Understanding Gauges_ section. If a pool qualifies for these rewards, the Curve UI will show the possible range of tAPR (token Annual Percentage Rate) values a user can earn, which may change over time.

To calculate the rewards tAPR:

<figure><img src="../../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

The parameters used to calculate the rewards tAPR are gathered from various sources, primarily on-chain data:

* **crv\_price**: The current USD price of the $CRV token. This is usually obtained from the CoinGecko API.
* **inflation\_rate**: The rate at which new $CRV tokens are created, which is available from the $CRV token’s smart contract.
* **relative\_weight**: This value reflects the weight of a pool’s rewards gauge compared to others, determined through weekly voting. It can be calculated by querying the Curve gauge controller contract.

These data points help determine the range of possible rewards that users can earn from participating in Curve pools.

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

* **working\_supply**: This is the total amount of liquidity staked in the rewards gauge, accessed by querying the specific Curve gauge contract.
* **asset\_price**: The current price of the pool's underlying asset. For example, in a Bitcoin pool, this would be the price of $BTC. For v2 pools, where multiple assets are present, an average price is calculated.
* **virtual\_price**: This represents the growth of the pool over time, previously discussed in detail.

The "magic number" 12,614,400 represents the number of seconds in a year (31,536,000 seconds) multiplied by 0.4, which accounts for the impact of boosts. Boosts can range from a minimum of 1 to a maximum of 2.5, with the factor 0.4 being the ratio of the minimum to maximum boost (1/2.5).

On the Curve UI, tAPR values are shown as a range. The left side of the arrow indicates the base tAPR with no boost, while the right side shows the maximum tAPR a user could receive with the maximum boost (2.5 times the base).

#### Incentives tAPR

Some pools also offer additional token rewards beyond $CRV. These are permissionlessly streamed without approval from the Curve DAO. For instance, the stETH pool displays rewards in $LDO tokens alongside $CRV rewards. The UI shows these extra incentives when applicable.

For developers, additional details can be found in the technical documentation:

* About Liquidity Gauges
* Gauge Controller
* Gauges for EVM Sidechains
* Gauge Proxy

<figure><img src="../../.gitbook/assets/image (15).png" alt=""><figcaption></figcaption></figure>

Pool Overview Page

<figure><img src="../../.gitbook/assets/image (16).png" alt=""><figcaption></figcaption></figure>

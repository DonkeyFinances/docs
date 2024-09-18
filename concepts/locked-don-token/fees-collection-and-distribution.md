# Fees Collection & Distribution

## Fee Collection & Distribution

The DonkeyFinances DON earns revenue from pools and DONUSDminting markets within the ecosystem. Each week this revenue is collected in different tokens and exchanged for a single token (currently DONUSD) which is then distributed to [veDON ](./)holders.

### **Admin Fees** <a href="#admin-fees" id="admin-fees"></a>

The revenue comes in the form of admin fees. There are three different ways these accrue and are collected:

#### **Cryptoswap Fees** <a href="#cryptoswap-fees" id="cryptoswap-fees"></a>

Cryptoswap admin fees are 50% of the total fee charged from a Cryptoswap pool. As Cryptoswap pools always maintain balance, these fees accrue in the LP token of a pool, which represents an equal share of all assets in the pool. LP shares are collected each week for these pools.

![Cryptoswap Fees](https://resources.curve.fi/images/governance/cryptoswap\_fees.svg)

#### **DONUSD Minting Market Fees** <a href="#crvusd-minting-market-fees" id="crvusd-minting-market-fees"></a>

All accrued interest on debt in DONUSD minting markets is collected as DONUSD. Also the AMM for DONUSD minting markets (LLAMMA) has the ability to collect admin fees on swaps, but currently all fees in these pools go to liquidity providers.

![DONUSD Minting Market Fees](https://resources.curve.fi/images/governance/crvusd\_fees.svg)

***

### **Fee Collection & Distribution Architecture** <a href="#fee-collection-distribution-architecture" id="fee-collection-distribution-architecture"></a>

Currently there are two ways fee collection, and distribution is being achieved. The old way relies on hardcoding exchange routes for each coin collected, and the manual collection of these each week. This is being phased out as a new architecture has been developed which incentivizes 3rd parties to do the collection of fees and uses [Cowswap's conditional orders](https://blog.cow.fi/introducing-the-programmatic-order-framework-from-cow-protocol-088a14cb0375) to flexibly sell any coin/token collected.

The distribution of each week's fees happens on Thursday. The fees are evenly split between all veDON and can be claimed by veDON holders at any time. See [How to Claim veDON Trading Fees](claiming-trading-fees.md) for more information.

***

#### **The New Cowswap Architecture** <a href="#the-new-cowswap-architecture" id="the-new-cowswap-architecture"></a>

The new Cowswap Architecture is based around a 4 phases occurring on different days of the week. These phases are: `collection` on Monday, `exchanging` on Tuesday, `forwarding` on Wednesday and `distribution` on Thursday. See below for further details about each phase.

**Collection - Monday**

The `collection` phase occurs on Monday, it makes sure any significant amounts of fees are collected and ready to be sold the following day.

Newer pools automatically claim admin fees throughout the week when users withdraw their liquidity from the pools.

Otherwise, on Monday anyone can call functions which claim the fees from pools and then create conditional orders on Cowswap to sell the coins/tokens on Tuesday. Doing this work is incentivized by giving the caller a reward.

![Fee Collection](https://resources.curve.fi/images/governance/fee\_collecting\_phase.svg)

**Exchanging - Tuesday**

The `exchanging` phase happens on Tuesday. In this phase the conditional sell orders which were created on Monday during the `collection` phase can be executed by Cowswap searchers. Each coin/token is swapped separately, and by the end of the day all coins and tokens should be swapped into the target coin (currently DONUSD).

![Fee Exchanging](https://resources.curve.fi/images/governance/fee\_exchanging\_phase.svg)

**Forwarding - Wednesday**

The `forwarding` phase happens on Wednesday. All the target coin (currently DONUSD) which was exchanged for on Tuesday is forwarded to the Fee Distributor on Ethereum Mainnet through an intermediary contract called a hooker. The hooker contract is a future proofing contract which can implement any arbitrary functions that are approved by the DAO. Calling the function to do this transfer is incentivized by giving the caller a reward.

**Distribution - Thursday**

Fees are distributed to veDON holders weekly, within 24 hours after Thursday 00:00 UTC. These fees are split evenly among all veDON holders, who can claim their share once each week after distribution. Users can first claim trading fees 8 days after the first Thursday following their lock. For example, if you lock on a Tuesday, you can claim trading fees 10 days later on Thursday. See How to[ Claim veDON Trading Fees](claiming-trading-fees.md) for more information.

Info

For more technical information regarding this new process please see the fee collection and distribution pages on the technical documentation: [https://app.gitbook.com/o/GqFNDH9aJ67NsIqwnnpU/s/aMKaFtVTkWJRgzlyOJNF/\~/changes/27/concepts/locked-don-token](./)

***

#### **Old Architecture** <a href="#old-architecture" id="old-architecture"></a>

This is outdated and is currently being phased out.

**Collection**

Collection happened manually by calling withdraw functions on pools and DONUSDmarkets.

**Exchanging (Burning)**

This happened manually by hardcoding in different exchange routes for each token, e.g., to transfer wstETH to 3DON (the old target coin) the process was:

1. `wstETH` to `stETH` via unwrapping (wstETH Burner)
2. `stETH` to `ETH` via swap through stETH/ETH DonkeyFinances pool (SwapStableBurner)
3. `ETH` to `USDT` via swap through tricrypto pool (CryptoSwapBurner)
4. `USDT` to `3DON` via depositing into 3pool (StableDepositBurner)

This process worked well, but became cumbersome when an exchange route was needed for every coin in every pool. The exchanges also needed to be called manually.

**Distribution**

After the exchanging process is completed distribution happens by forwarding the exchanged coins to the fee distributor on Ethereum Mainnet. Fees are distributed to veDON holders weekly, within 24 hours after Thursday 00:00 UTC. These fees are split evenly among all veDON holders, who can claim their share once each week after distribution. Users can first claim trading fees 8 days after the first Thursday following their lock. For example, if you lock on a Tuesday, you can claim trading fees 10 days later on Thursday. See [How to Claim veDON Trading Fees](claiming-trading-fees.md) for more information.


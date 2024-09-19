---
description: Overview
hidden: true
---

# Pools

**Liquidity Pools Overview**

Liquidity pools are a fundamental concept in decentralized finance (DeFi) and Ethereum. They consist of multiple assets that users can swap between, with liquidity providers earning fees for contributing assets to the pools.

**Types of Pools in DonkeyFinances:**

1. **Cryptoswap Pools**: For assets that fluctuate in value against each other, such as USDC and ETH. These pools require a more complex design to maintain balance due to the volatility of the assets.

When providing liquidity to a pool, you're exposed to all the assets within it, regardless of which asset you deposit. It's important to choose pools with assets you are comfortable holding.

***

#### **Cryptoswap (DonkeyFinances V2) Pools**

Cryptoswap pools contain assets that aren't pegged to each other, such as USDC and ETH. The goal is to maintain an equal value between the assets. For example, if the pool contains $1,000,000 worth of USDC, it will also hold $1,000,000 worth of ETH.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption><p>Image: Curve Finance</p></figcaption></figure>

***

#### **Pool Fees**

* Fees are pool-specific and typically range from 0.01% to 0.04%.
* During periods of high volatility, dynamic fees may increase to compensate for the risk.
* 50% of pool fees are distributed to Liquidity Providers, increasing the value of their LP tokens, while the remaining 50% goes to DON (veDON) holders.
* Deposits and withdrawals are free when they are balanced, but imbalanced transactions may incur small fees.

***

#### **Rewards and Yield**

Liquidity providers can earn two types of yield:

1. **Base vAPY**: Reflects how much the value of LP tokens is increasing through pool fees.
2. **Rewards tAPR**: Includes DON inflation rewards, additional token incentives, and points programs. To earn these rewards, LP tokens must be staked in the pool's gauge.

<figure><img src="../../.gitbook/assets/image (1) (1).png" alt=""><figcaption><p>Image: Curve Finance</p></figcaption></figure>

Some pools may also include yield-bearing tokens (e.g., sUSD or sDAI), with all the yield going directly to Liquidity Providers without any deductions.

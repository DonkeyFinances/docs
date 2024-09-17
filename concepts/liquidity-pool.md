# 🤽‍♂️ Liquidity Pool

Liquidity pools are an innovative concept that originated in DeFi and have become crucial to the overall system. They enable Automated Market Makers (AMMs) like Sushi to create liquid markets for various assets, allowing trading without the need for a counterparty or order book, unlike traditional finance.

Liquidity pools function by holding a certain amount of specific assets (based on the pool's pair) that anyone can trade against at any time. Each time a user makes a swap using that pair, a small, variable fee is charged. Users can lend their unused assets to a liquidity pool in exchange for a portion of the fees generated, becoming what is known as a Liquidity Provider (LP). This process is somewhat analogous to making a bank deposit in the real world and earning interest (fees) on the deposit.

### Types of Liquidity Pools

There are several types of pools available on Sushi for users to participate in, including:

**Constant Product Pools**

Constant Product (CP) pools were the first type of liquidity pool to be introduced, using the classic formula (`x * y = k`), where (`x`) and (`y`) are the assets in the pool, and (`k`) is a constant. This formula requires a 50/50 equal weighting between the two assets. When providing liquidity, LPs must add an equal amount of both assets to maintain the constant (`k`).

**Stable Pools**

Stable pools are designed for trading like-kind assets, such as stablecoins. Assets that are closely correlated in price, like stablecoins, benefit from this pool type due to its cost-effectiveness, minimal volatility, and low slippage. While stable pools are most commonly used for stable pairs like USDC/DAI, they can also be suitable for other closely related assets, such as ETH/stETH.

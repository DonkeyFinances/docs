# 🤽‍♂️ Liquidity Pool

#### **Liquidity Pools**

Liquidity pools are a cornerstone of decentralized finance (DeFi), enabling the smooth operation of Automated Market Makers (AMMs) like DonkeyFinances. These pools create liquid markets for various assets, allowing them to be traded without the need for a traditional order book or a counterparty, as seen in traditional finance.

Liquidity pools work by holding a reserve of specific assets (depending on the pool's pair) that users can trade against at any time. Each trade incurs a small, variable fee. Users can contribute their unused assets to a pool and earn a portion of these fees, becoming what is known as a **Liquidity Provider** (LP). Providing liquidity is akin to making a bank deposit and earning interest (in the form of fees) on the deposit.

***

#### **Types of Liquidity Pools**

There are several types of liquidity pools available on Sushi, each designed for different trading scenarios:

**1. Constant Product Pools**

Constant Product (CP) pools were the first liquidity pools to emerge, using the well-known formula(`x * y = k`), where (`x`) and (`y`) are the assets in the pool, and (`k`) is a constant. These pools enforce a 50/50 balance between the two assets. When LPs provide liquidity, they must add equal amounts of both assets to keep the constant (k) intact.



**2. Stable Pools**

Stable pools are designed for trading assets that have similar prices, like stablecoins (e.g., USDC/USDT). Since these assets are closely correlated, trading within stable pools incurs minimal volatility and slippage, making them highly efficient. While most common for stablecoin pairs, stable pools can also be used for other like-kind assets, such as ETH and stETH.



**3. Concentrated Liquidity Pools**

Concentrated Liquidity (CL) pools are the latest innovation and offer the potential for higher returns when managed well. CL pools allow LPs to “concentrate” their liquidity within a specific price range that they define, rather than distributing liquidity across the entire price curve (from zero to infinity), as with CP or stable pools.

If the asset price remains within the defined range, the LP earns fees—often more fees with less capital invested. However, if the price moves out of the defined range, the LP’s liquidity goes unused, and no fees are generated.

Due to their structure, CL pools are far more capital-efficient, allowing savvy users to earn higher yields with less liquidity. However, they require more active management and are best suited for users with a hands-on investment approach.

###

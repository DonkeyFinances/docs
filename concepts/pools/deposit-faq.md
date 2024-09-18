# Deposit FAQ

**Deposit Wrapped Option:** The "deposit wrapped" option is used in metapools or pools with c-tokens (for Compound) or a-tokens (for AAVE). If you’re depositing a stablecoin into a pool linked to a lending protocol, Curve automatically converts your token into its respective cToken or aToken. This option is only relevant if your token has already been lent on Compound or AAVE. If your stablecoin is in its original form, you can ignore this option. Additionally, if you hold basepool tokens (e.g., 3Crv), you can use this option to deposit them directly into a metapool.

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

***

**Providing Liquidity on Curve:** When you provide liquidity by depositing a stablecoin, the deposit is split across all tokens in the pool. For instance, if you deposit 1,000 DAI, it will be distributed among other assets in the pool, like GUSD, USDC, and USDT. These balances fluctuate as trades occur.

<figure><img src="../../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

***

**Does the Coin I Deposit Matter?** No, the specific stablecoin you deposit doesn’t affect your overall returns, except for potential deposit bonuses. All deposits are split into the pool, so you can deposit any combination of coins without worrying about returns.

***

**Understanding Deposit Bonuses:** Deposit bonuses occur when a specific token's balance is low within a pool. For example, if GUSD makes up less than 50% of a metapool, depositing GUSD might earn you a small bonus, reflecting its higher value in the market or helping the pool maintain balance.

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

***

**Withdrawals:** You can withdraw your liquidity in any stablecoin from the pool. If you choose to withdraw a token that has a large share in the pool, you might receive a withdrawal bonus.

***

**Interest Accrual:** In pools that use lending protocols, interest compounds automatically every block (approximately every 15 seconds) or immediately after fees are paid.

***

**What is Arbitrage?** Arbitrage refers to the simultaneous buying and selling of tokens to profit from price discrepancies between different markets. In the case of Curve, traders can take advantage of these price differences, helping maintain the stability of token prices and benefiting liquidity providers.

***

**Incentivized Pools:** Some pools are "incentivized," meaning liquidity providers earn additional rewards, such as governance tokens, beyond regular trading and lending fees. This is especially useful in keeping stablecoins pegged to their intended value.

<figure><img src="../../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

***

**What Influences Incentive APRs?**

1. **Staked LP Tokens**: As more users stake their LP tokens, individual shares of rewards decrease.
2. **Token Price**: If the value of reward tokens (like LDO) rises, the annual bonus rate increases.
3. **Reward Size**: Weekly reward amounts (e.g., 48,000 SNX) can be adjusted based on partnerships with Curve.

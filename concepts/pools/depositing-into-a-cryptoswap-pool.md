# Depositing into a cryptoswap-pool

Cryptoswap pools contain two volatile assets and are designed to offer deep liquidity for a wide variety of assets with different levels of volatility.

Learn more about v2 pools

_For instance, the CVX/ETH pool is used in the examples below._

<figure><img src="../../.gitbook/assets/image (23).png" alt=""><figcaption></figcaption></figure>

#### Depositing and Staking on Curve Finance

**Depositing Tokens**

1. **Flexible Deposits**: You can deposit one or both of the coins in the pool. The choice does not affect your returns. Depositing the coin with the smallest share in the pool will have a slight positive impact on the pool's price balance, as the pool rebalances to maintain relative equality.
2. **Exposure**: When you deposit a coin, it gets split across all the coins in the pool, giving you exposure to each.
3. **Balanced Proportion**: Use the checkbox labeled **"Add all coins in a balanced proportion"** if you want to deposit both coins in their current proportions within the pool. This method ensures there is no price impact.
4. **Wrapped Tokens**: The checkbox labeled **"Deposit Wrapped"** allows you to deposit wrapped ETH (wETH) instead of plain ETH.

**Confirming and Staking**

1. **Approve and Deposit**: First, you need to approve the Curve Finance contract. Then, proceed with the deposit transaction. Be mindful of gas fees; waiting for a lower gas price can help reduce costs, especially if you are making a large deposit.
2. **Receive LP Tokens**: After depositing, you will receive Liquidity Provider (LP) tokens. These tokens represent your ownership share in the pool and are needed for staking.
3. **Staking for CRV**: After depositing, you’ll be prompted to deposit your LP tokens into the DAO liquidity gauge. Confirming this transaction will allow you to earn CRV rewards. This step appears only if you deposited under the "Deposit and stake" tab. If you didn't use this tab, you’ll need to manually deposit LP tokens in the gauge under the 'Stake' tab.
4. **Earning Rewards**: Once staked, you will start earning trading fees and CRV rewards.

_You can click the link below to learn how to boost your CRV rewards by locking CRV on the Curve DAO:_

* Boosting your CRV Rewards
* Staking your $CRV

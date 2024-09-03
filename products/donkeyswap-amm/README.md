---
description: Detailed explanation of Donkeyswap
---

# Donkeyswap AMM

Donkeyswap is composed of a series of SRC20-SRC20 exchange contracts. If an asset does not have an exchange yet, anyone can create one using the Donkeyswap factory contract. The factory acts as a public registry and looks up all assets and exchange addresses added to the system.

Each exchange holds reserves of both SRC-20 native assets. Anyone can become a liquidity provider on an exchange and contribute to its reserves by depositing an equivalent value of each SRC-20 asset. This differs from buying or selling; it requires depositing an equivalent value of both SR and the relevant SRC-20 assets.

Unlike in the EVM, liquidity is pooled across all providers without needing an internal "pool assets " (SRC-20) to track each provider's relative contribution. Pool assets are minted when liquidity is deposited into the system and can be burned at any time to withdraw a proportional share of the reserves.

Exchange contracts are automated market makers between an SRC20-SRC20 pair. Traders can swap between the two in either direction by adding to the liquidity reserve of one and withdrawing from the reserve of the other.

Donkeyswap uses a "constant product" market-making formula. Pairs as automated market makers, are always prepared to exchange one native asset for another, provided the "constant product" formula is maintained. This formula, expressed as `x * y = k`, ensures that trades do not alter the product `(k)` of a pair’s reserve balances `(x and y)`. Since `k` remains constant during trades, it is known as the invariant. This formula has the beneficial property that larger trades (relative to reserves) are executed at progressively worse rates compared to smaller ones.

For clarity, we the following elaboration will be based on ETH which is the base asset for Fuel Network to explain on ETH-SRC20 pair. The exchange rate is based on the relative size of the ETH and SRC20 reserves and the amount with which an incoming trade shifts this ratio. Selling ETH for SRC20 native assets increases the size of the ETH reserve and decreases the size of the SRC20 reserve. This shifts the reserve ratio, increasing the SRC20 native asset's price relative to ETH for subsequent transactions. The larger the trade relative to the total size of the reserves, the more price slippage will occur. Essentially, exchange contracts use the open financial market to decide on the relative value of a pair and use that as a market-making strategy.

Currently, a small liquidity provider fee (0.30%) is taken out of each trade and added to the reserves. While the ETH-SRC20 reserve ratio is constantly shifting, fees ensure that the total combined reserve size increases with every trade. This functions as a payout to liquidity providers that is collected when they burn their pool assets to withdraw their portion of total reserves. Guaranteed arbitrage opportunities from price fluctuations should push a steady flow of transactions through the system and increase the amount of fee revenue generated.

Since Donkeyswap is entirely on-chain, prices can change between when a transaction is signed and when it is included in a block. Traders can bound price fluctuations by specifying the minimum amount bought on sell orders or the maximum amount sold on buy orders. This acts as a limit order that will automatically cancel if it is not filled. It is also possible to set transaction deadlines, which will cancel orders if they are not executed fast enough.

The reason only one exchange per native asset can be registered to the factory is to encourage providers to pool their liquidity into a single reserve. However, Donkeyswap has built-in support for SRC20-to-SRC20 trades using the public pools from the factory on one side of the transaction and custom, user-specified pools on the other. Custom pools could have fund managers, use alternate pricing mechanisms, remove liquidity provider fees, integrate complex three-dimensional fomo-based Ponzi schemes, and more. They just need to implement the Donkeyswap interface and accept SR as an intermediary asset. Custom pools do not have the same safety properties as the public ones. It is recommended users only interact with audited, open-source smart contracts.

Upgrading censorship-resistant, decentralized smart contracts is difficult. If significant improvements are made to the system, a new version will be released. Liquidity providers can choose between moving to the new system or staying in the old one. If possible, new versions will be backwards compatible and able to trade SRC20-to-SRC20 with the old versions similar to a custom pool.

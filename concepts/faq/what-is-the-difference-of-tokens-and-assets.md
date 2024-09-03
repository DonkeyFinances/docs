# What is the difference of tokens and assets?

**An "Asset" is a Native Asset on Fuel and has the associated AssetId type.**

* An "Asset" refers to a Native Asset within the Fuel ecosystem.
* Each Asset is identified by a unique type known as AssetId.

**Assets are distinguishable from one another.**

* Each Asset is distinct and can be uniquely identified from other Assets based on its AssetId.

**A "Coin" represents a singular unit of an Asset.**

* A "Coin" is a single unit or instance of a specific Asset.
* E.g. Alice has 3 Coins.
* E.g. In EVM context,Alice has 3 tokens.

**Coins of the same Asset are not distinguishable from one another.**

* Individual Coins of the same Asset type are identical and cannot be differentiated from one another.

**Fuel does not use tokens like other ecosystems such as Ethereum and uses Native Assets with a UTXO design instead.**

* Unlike Ethereum, which uses tokens for representing assets, Fuel uses Native Assets.
* Fuel employs a UTXO (Unspent Transaction Output) design, similar to Bitcoin, for managing and tracking asset ownership.

[For more details on terminology used on Fuel Network](https://docs.fuel.network/docs/sway/blockchain-development/native\_assets/#asset-vs-coin-vs-token)

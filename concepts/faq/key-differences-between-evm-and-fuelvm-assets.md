# Key Differences Between EVM and FuelVM Assets

**ERC-20 vs Native Asset**

On the EVM, Ether (ETH) is the native asset. Sending ETH to an address or contract is an operation built into the EVM, meaning it doesn't require a smart contract to update balances and track ownership, unlike ERC-20 tokens.

On the FuelVM, all assets are native, and the process for sending any native asset is the same.

While smart contracts are still needed for minting and burning assets on FuelVM, sending and receiving these assets can be done independently of the asset contract.

Similar to the EVM, Fuel has a standard API for Native Assets using the Sway Language. The equivalent of ERC-20 for the Sway Language is SRC-20, which serves as the Native Asset Standard.

[For more details on Fuel Network assets](https://docs.fuel.network/docs/sway/blockchain-development/native\_assets/#key-differences-between-evm-and-fuelvm-assets)

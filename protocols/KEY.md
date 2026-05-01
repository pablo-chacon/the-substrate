# KEY Protocol

Core components:
- ERC-721 token primitive representing a vehicle.
- Neutral, deterministic settlement rails as immutable smart contracts.

---

## What It Is

KEY Protocol is a minimal, self-contained, production-ready settlement layer for decentralized vehicle ownership and transfer.

Vehicle -> On-chain Representation -> Ownership Transfer -> Legal Registration.

DeFi/CeFi Agnostic: Easy integration of vehicle ownership settlement for apps, fintech providers, and platform operators within existing workflows.

---

## What KEY Protocol Provides

**Vehicle Primitive** on-chain vehicle representation

- ERC-721 token bound to a physical vehicle
- Ownership state tracked on-chain
- Hash commitment to off-chain vehicle documentation
- No pricing or valuation logic

**Settlement Rails** ownership transfer engine

- Trustless transfer lifecycle
- Immutable protocol fee paid to protocolTreasury
- Deterministic events for indexing
- Templates for legally binding ownership transfer in 50+ countries via existing vehicle registry APIs

**The One-Way Bridge**

KEY demonstrates something none of the other protocols do as explicitly: DeFi can reach into CeFi and make legally binding changes. CeFi cannot reach back.

In at least 50 countries, vehicle ownership registries expose APIs showing current and previous owner. KEY's templates can interact with these APIs to execute a legally recognized ownership transfer — triggered from the decentralized side, recorded in the centralized system.

CeFi has no equivalent path inward. It cannot initiate or modify a KEY transaction. The bridge is one-directional by design. This is not a feature. It is a structural property — proof that decentralized infrastructure can interface with and legally supersede centralized record systems without requiring those systems to change, adopt crypto, or even be aware of what initiated the change.

---

## Deployment

Official KEY Protocol contract addresses:

- VehicleRegistry: 0x23d273d83934ED9d32951d10947Cf4a2Fa1dD241
- VehicleSaleCore: 0x912FC775dFc9024bDFDeAd20222Bfd285AbB3554
- Escrow: 0x1c9d7c53aB7F3fD1aA02ceF173906980A875aA48
- protocolTreasury: 0x86076aBcB9492359fd78432242A3534Fd114552B

---

## Resources

- [Whitepaper](https://github.com/pablo-chacon/key-protocol/blob/main/WHITEPAPER.md)
- [Protocol Repository](https://github.com/pablo-chacon/key-protocol) *(opens at deployment)*
- [Quick Start Templates](https://github.com/pablo-chacon/key-templates/tree/main) *(opens at deployment)*
# STAY Protocol

Core components:
- ERC-token primitive representing a commodity.
- Neutral, deterministic settlement rails as immutable smart contracts.

---

## What It Is

STAY Protocol is a minimal, self-contained, production-ready settlement layer for decentralized commodity representation and exchange.

Commodity -> On-chain Representation -> Access or Transfer Agreement -> Settlement.

DeFi/CeFi Agnostic: Easy integration of commodity settlement for apps, platforms, and asset operators within existing workflows.

---

## What STAY Protocol Provides

**Commodity Primitive** on-chain commodity representation

- Token bound to a physical commodity or asset
- Access rights, transfer terms, and duration committed on-chain
- Hash commitment to off-chain asset documentation and conditions
- No pricing or valuation logic

**Settlement Rails** commodity access and transfer engine

- Trustless agree -> access -> confirm -> finalize lifecycle
- Immutable protocol fee paid to protocolTreasury
- Permissionless finalization
- Deterministic events for indexing

---

## Deployment

Official Canonical deployment addresses:

    StayCore: 0x09B9349232CeDB36A9e0efAEa06b5Fda7C49A82a
    PropertyRegistry: 0x24355ae449E6F189884679AF653211549C19d95F
    Escrow: 0x69Cf51FF2389a5af38017eC5B19180c8587B081a
    PROTOCOL_TREASURY: 0x5496cEB0b6468f6F7D5DB2Cf45883BEb92B25D9D

---

## Resources

- [Whitepaper](https://github.com/pablo-chacon/stay-protocol/blob/main/WHITEPAPER.md)
- [Protocol Repository](https://github.com/pablo-chacon/stay-protocol) *(opens at deployment)*
- [Quick Start Templates](https://github.com/pablo-chacon/stay-templates) *(opens at deployment)*
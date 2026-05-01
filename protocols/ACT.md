# ACT Protocol

Core components:
- ERC-token primitive representing a physical service.
- Neutral, deterministic settlement rails as immutable smart contracts.

---

## What It Is

ACT Protocol is a minimal, self-contained, production-ready settlement layer for decentralized physical service delivery.

Service Agreement -> Service Delivery -> Confirmation -> Settlement.

DeFi/CeFi Agnostic: Easy integration of service settlement for apps, platforms, and service providers within existing workflows.

---

## What ACT Protocol Provides

**Service Primitive** on-chain service representation

- Token bound to a physical service agreement
- Service type, scope, and terms committed on-chain
- Hash commitment to off-chain service documentation
- No scheduling or dispatch logic

**Settlement Rails** service delivery and settlement engine

- Trustless agree → deliver → confirm → finalize lifecycle
- Immutable protocol fee paid to protocolTreasury
- Permissionless finalization
- Deterministic events for indexing

ACT is protocol-neutral about service type and scale. A local massage and a private jet charter settle identically. The protocol has no opinion on price, prestige, or context.

---

## Deployment

Official ACT Protocol contract addresses:

- ActToken: 0x5B81FcA920fCdf667B310e8ae1F78a69cff49db9
- ActEscrow: 0xE69bDf3279f545eA541aDF3AEB2153C052EbD1AF
- ActCore: 0x70C5Ec74317EdFab13314B89342E1F70BaCa018e
- ActTreasury: 0x44504504938CcBF8D0d99B370A882b94ffCf2423

---

## Resources

- [Protocol Repository](https://github.com/pablo-chacon/act-protocol) *(opens at deployment)*
- [Quick Start Templates](https://github.com/pablo-chacon/act-templates) *(opens at deployment)*
# DeDe Protocol

Core components:
- ERC-721 token primitive representing a parcel.
- Neutral, deterministic settlement rails as immutable smart contracts.

---

## What It Is

DeDe Protocol is a minimal, self-contained, production-ready settlement layer for decentralized delivery networks.

Peer-to-Peer: Parcel → Pickup → Dropoff → Delivery confirmation.

DeFi/CeFi Agnostic: Easy integration of delivery settlement for apps, fintech providers, and payment platforms within existing workflows.

---

## What DeDe Protocol Provides

**ParcelCore** — the settlement engine

- ERC-721 parcels
- Pickup → dropoff → finalize lifecycle
- Automatic finalization after 72h if neither side finalizes
- Immutable protocol fee (0.5%) paid to protocolTreasury
- Dynamic platform fee (set by platform provider) paid to platformTreasury
- Permissionless finalization with a 0.05% finalizer tip
- Full slashing support through signer registry
- Deterministic events for indexing

**Escrow** — secure value transfer

- Holds user funds until parcel completion
- Releases value automatically based on parcel state transitions
- Protocol and platform fees taken at payout time
- Trusted by ParcelCore only

**AStarSignerRegistryStaked** — oracle/signer registry

- Permissionless join
- Mandatory stake
- Slashing on misconduct
- Supports A* signatures only

---

## Ethereum Mainnet Deployment

| Contract | Address |
|---|---|
| ParcelCore | `0xeF1D4970c3B988840B13761Ec4FBb85106d789F8` |
| Escrow | `0x834317eFB2E6eE362a63474837398086cC302934` |
| AStarSignerRegistryStaked | `0x311A4c3Ed79D4467C55dd7CEE0C731501DF3f161` |
| protocolTreasury | `0x9C34d6a6BF1257A9e36758583cDC36F4cE2fA78F` |

Ownership renounced. Contracts are immutable.

---

## Resources

- [Whitepaper](https://github.com/pablo-chacon/dede-protocol/blob/main/WHITEPAPER.md)
- [Protocol Repository](https://github.com/pablo-chacon/dede-protocol)
- [Quick Start Templates](https://github.com/pablo-chacon/dede-templates)
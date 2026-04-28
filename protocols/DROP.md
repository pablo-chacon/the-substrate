# DROP Protocol

Core components:
- ERC-721 token primitive representing a storage unit.
- Neutral, deterministic settlement rails as immutable smart contracts.

---

## What It Is

DROP Protocol is a minimal, self-contained, production-ready settlement layer for decentralized storage systems.

Any Object or Container: Drop → Storage → Pick → Settlement.

DeFi/CeFi Agnostic: Easy integration of storage settlement for apps, fintech providers, and payment platforms within existing workflows.

---

## What DROP Protocol Provides

**DROPSpaceRegistry** — storage availability declaration

- On-chain registration of storage spaces
- Capacity and availability tracking
- Coarse location commitment
- Hash commitment to off-chain terms
- No pricing or ranking logic

**DROPCore** — storage settlement engine

- ERC-721 storage sessions
- Drop → pick → finalize lifecycle
- Optional on-chain escrow settlement
- Immutable protocol fee (0.3%) paid to protocolTreasury
- Permissionless finalization with a small finalizer tip
- Deterministic events for indexing

**Escrow** — optional value settlement

- Reusable escrow contract
- Supports ETH and ERC-20 tokens
- Releases funds based on storage lifecycle
- Off-chain settlement remains fully supported

---

## Ethereum Mainnet Deployment

| Contract | Address |
|---|---|
| DROPCore | `0x924cC808389F0385dBe3F0248796147D85635338` |
| DROPSpaceRegistry | `0xfbf7Ed40f0FA992D2Ddc07250FE2D0e72Cbd12c9` |
| Escrow | `0x9e859D91C900F799F23F55FffCdAf389118a5766` |
| protocolTreasury | `0xcd89321D5a9080e417ac01c8F46F643548ad7C04` |

Ownership renounced. Contracts are immutable.

---

## Resources

- [Whitepaper](https://github.com/pablo-chacon/drop-protocol/blob/main/WHITEPAPER.md)
- [Protocol Repository](https://github.com/pablo-chacon/drop-protocol)
- [Quick Start Templates](https://github.com/pablo-chacon/drop-templates)
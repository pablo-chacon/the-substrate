# Templates

Every protocol in The Substrate has a canonical template repository. Templates are the reference implementations, the open, documented, correct way to interact with each protocol directly.

They exist for one reason: the exit is always open.

Any platform built on The Substrate makes a product choice about how to present the protocols to its users. That is legitimate. Platforms add value through interface, integration, and experience. What they cannot do is own the protocol beneath them. A user who wants to interact with the protocol directly, bypass a platform layer, or build their own implementation always has a documented, neutral path to do so.

This is not a statement against platforms. It is a statement about infrastructure. Neutral infrastructure has no preferred access point. The templates make that concrete.

---

## Template Repositories

| Protocol | Domain | Repository | Status |
|---|---|---|---|
| **DeDe** | Parcel | https://github.com/pablo-chacon/dede-templates | Public |
| **DROP** | Physical Storage | https://github.com/pablo-chacon/drop-templates  | Public |
| **KEY** | Vehicle | — | Opens at mainnet deployment |
| **CUT** | Digital Ownership | — | Opens at mainnet deployment |
| **ACT** | Physical Services | — | Opens at mainnet deployment |
| **STAY** | Commodity | — | Opens at mainnet deployment |

---

## What Templates Cover

Each template repository contains reference implementations for the full lifecycle of that protocol, from asset creation and escrow through settlement and finalization. Templates are minimal, auditable, and dependency-light by design.

They are not SDKs. They are not frameworks. They are the correct, direct way to use the protocol, readable by anyone, forkable by anyone, deployable by anyone.

---

## The Strategic Property

Any attempt to centralize access to a Substrate protocol is self-limiting. The templates are always available. The documentation is always open. The protocol itself is immutable and permissionless.

Centralization on top of The Substrate is a product decision. It is never a structural capability. The reference implementation exists regardless of what is built above it.

This means the only viable long-term position for any platform built on The Substrate is to add genuine value — because the alternative, locking users in, has no foundation to stand on.
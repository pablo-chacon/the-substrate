# Orchestration: Global Supply Chain

## Overview

This document describes how DeDe and DROP compose into a fully fractionalized, multi-hop international supply chain. Each hop is an independent atomic settlement. No hop has knowledge of the hop before or after it. The chain has no coordinator, no shared state, and no central party.

The example uses a wholesale consignment of 50 smartphones originating in Panama, destined for individual buyers in a single destination city.

---

## Off-Chain Context

A wholesaler in Panama aggregates 50 smartphone orders for the same destination region. Buyer agreements, pricing, and logistics coordination happen off-chain through whatever platform or arrangement the parties choose. The on-chain layer handles only settlement: Pickup -> Dropoff -> Delivery confirmation -> Settlement.

---

## The Chain

**Hop 1: Origin to Port of Origin**

A single DeDe parcel is minted representing the full consignment of 50 phones. A carrier agrees to terms and picks up the consignment. The carrier delivers it to DROP node 1: a shipping container at the port of origin.

DeDe settles. Hop 1 is complete. The carrier is paid, ERC-721 token burned.

---

**Hop 2: Port of Origin Release**

DROP node 1 releases the consignment to the shipping carrier. The container ships to the destination country via existing logistics infrastructure, off-chain.

Hop 2 is complete.

---

**Hop 3: Port of Destination to Local Storage**

At the destination docks a new DeDe parcel is minted for the consignment. 

A carrier picks up the consignment from the container, DROP node 1 settles. 

Carrier delivers it to DROP node 2: a local storage facility in the destination city.

DeDe settles. Hop 3 is complete. The carrier is paid.

---

**Hop 4: Fractionalization and Release**

At DROP node 2 the consignment is split into 10 DeDe parcels of 5 phones each. Nine carriers each agree terms and pick up one parcel. One buyer collects their fraction directly from DROP node 2, no carrier required for that fraction.

DROP node 2 remains open and accountable until the final fraction leaves. When the storage is empty: all 9 carrier pickups and 1 direct customer collection complete, DROP node 2 settles. 

Hop 4 is complete.

---

**Hop 5: Last Mile Delivery**

Each of the 9 carriers delivers their parcel to the end recipient. Each delivery is an independent DeDe settlement, 9 atomic settlements, each on its own terms, each independent and unaware of the others.

Hop 5 is fully complete when all 9 DeDe parcels settle, asynchronious. The buyer who collected directly at DROP node 2 has no hop 5, their chain ended at hop 4.

---

## Settlement Map

| Hop | Protocol | Event | Settles When |
|---|---|---|---|
| 1 | DeDe | Carrier delivers to DROP node 1 | Delivery confirmed |
| 2 | DROP | Container released to shipping | Release confirmed |
| 3 | DeDe | Carrier delivers to DROP node 2 | Delivery confirmed |
| 4 | DROP | All 10 fractions collected | Storage empty |
| 5 | DeDe x9 | Each carrier delivers to end recipient | Per delivery, independently |

---

## Properties

**No coordinator.** The wholesaler in Panama has no on-chain relationship with any of the 9 carriers or the direct-collecting buyer. Each settlement is between the immediate parties only.

**No shared state.** Each hop is a closed lifecycle. The carrier on hop 3 has no knowledge of hop 1. The carriers on hop 5 have no knowledge of each other.

**No stuck state.** Every node settles on deterministic conditions. DROP node 2 stays open until empty: a defined, auditable condition, not a judgment call.

**Fractionalization at the node.** One consignment becomes ten independent delivery streams at DROP node 2. This happens without any protocol modification, it is a natural property of minting new DeDe parcels from a DROP release.

**The direct collection option.** One buyer collects at the DROP node with no carrier and no last mile fee. This is not a special case. It is the default behavior available to any party who chooses it.

---

## Protocols Used

- DeDe = parcel settlement at every carrier hop
- DROP = physical storage intake, hold, and release at every node

All Substrate protocols involved or not is fully unaware of each others existence.
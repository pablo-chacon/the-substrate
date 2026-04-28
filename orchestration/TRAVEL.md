# Orchestration: Travel and Services

## Overview

This document describes how STAY and ACT compose into a fully settled personal travel experience: accommodation, transport, and services, paid entirely in crypto. Each settlement is atomic and independent. No protocol knows what the others are doing. The traveler's full journey is a sequence of independent closed transactions.

---

## The Journey

**STAY: Hotel Booking**

The traveler books a hotel room through a platform built on STAY. The booking is settled on-chain: accommodation secured, payment escrowed, terms agreed. The hotel does not know how the traveler will arrive. The traveler does not need to disclose anything beyond what the booking requires.

STAY settles at check-in or at the agreed confirmation point.

---

**ACT: Transport to Airport**

The traveler requests a ride to the airport through a platform built on ACT. The service is agreed, performed, and settled on-chain at completion. The driver does not know where the traveler is going after the airport. The airport does not know the traveler is coming.

ACT settles at drop-off.

---

**Flight**

The traveler flies. This happens off-chain through existing aviation infrastructure. The Substrate is uninvolved.

---

**DeDe + DROP: Parcel Collection at Destination**

At or near the destination the traveler picks up a DeDe parcel from a DROP storage node. The traveler is acting as a carrier — they agreed to collect and deliver a parcel on a journey they were already making. The DROP node releases the parcel. DROP settles.

The traveler completes the last mile delivery. DeDe settles. The traveler is compensated for the delivery, offsetting a portion of their travel cost.

Neither the hotel nor the taxi service nor the massage provider knows the traveler carried a parcel. The parcel sender does not know the traveler's itinerary. Each settlement is between the immediate parties only.

---

**STAY: Hotel Check-In**

The traveler checks in. STAY confirms. No further settlement required if escrowed at booking, the condition is met.

---

**ACT: Massage at Hotel**

The traveler books a massage through a platform built on ACT. Service agreed, performed, settled on-chain at completion.

ACT settles at service completion.

---

## Settlement Map

| Step | Protocol | Event | Settles When |
|---|---|---|---|
| 1 | STAY | Hotel booked | Check-in confirmed |
| 2 | ACT | Taxi to airport | Drop-off at airport |
| 3 | — | Flight | Off-chain |
| 4 | DROP | Parcel collected at destination node | Parcel released to traveler |
| 5 | DeDe | Last mile delivery completed | Delivery confirmed |
| 6 | STAY | Check-in | Condition met |
| 7 | ACT | Massage completed | Service confirmed |

---

## Properties

**The traveler as carrier.** The traveler participates in the Substrate as both consumer and service provider across the same journey. No special registration, no platform approval. They agreed to carry a parcel and were compensated. This is a natural economic behavior that emerges from composability, not a feature in any individual protocol design.

**No cross-protocol awareness.** STAY does not know ACT was used. ACT does not know a parcel was carried. DROP does not know where the traveler is staying. Each protocol settled its own transaction independently.

**Fully crypto-settled.** Every on-chain step is paid in crypto. The flight is the only step that remains in the existing financial system, not because the Substrate can't reach it, but because aviation infrastructure has not yet been built on neutral settlement rails.

**Privacy by architecture.** The traveler's full itinerary exists nowhere as a complete record. It is distributed across independent settlement events with no common identifier linking them. This is not a privacy feature. It is the default state of independent atomic settlements.

---

## Protocol Neutrality

The examples above use everyday transport and services. The protocols have no opinion on scale, price, or context.

A private jet charter is an ACT settlement. A villa booking is a STAY settlement. A luxury ground transfer is an ACT settlement. The protocol behavior is identical whether the transaction is a $50 taxi ride or a $50,000 charter flight. The settlement rail does not know the difference and does not need to.

This means the same orchestration pattern applies across the full economic spectrum: from last mile delivery carriers offsetting travel costs by picking up parcels, to high net worth travelers settling an entire international itinerary in crypto across independent platforms that have no knowledge of each other.

Same protocols. Same neutrality. Different price points.

---

## Protocols Used

- STAY = accommodation booking and settlement
- ACT = transport and service settlement
- DeDe = parcel last mile settlement
- DROP = parcel storage node release

All Substrate protocols in use or not, is fully unaware of each others existence.
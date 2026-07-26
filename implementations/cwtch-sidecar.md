# Cwtch Sidecar

Cwtch Sidecar is a minimal starter kit for adding peer-to-peer counterparty coordination to platforms built on any Substrate settlement protocol.

The Substrate protocols settle. They do not coordinate. Between the moment an instance is created on chain and the moment it is finalised, two counterparties usually need to say something to each other. This repository exists so that nobody writes that layer twice.

This is a starter kit, not an SDK. There is no package to install and no versioned dependency. You copy what you need, you own it, and you modify it.

---

## Concept

Most decentralised commerce systems pair trustless settlement with a coordination layer that is not trustless. Settlement happens on chain, but the conversation happens over infrastructure that is either centralised or weakly metadata-resistant. That layer becomes the actual weak point: the part that can be subpoenaed, correlated, or shut down.

Cwtch Sidecar closes that gap without introducing an operator.

Settlement stays public on Ethereum, which is what makes it trustless and dispute-resolvable. Coordination moves to Cwtch, peer to peer over Tor onion services, with no server in the middle. Neither half depends on a party who could be compelled or breached.

---

## Scope

One repository, every protocol.

The messaging requirement is identical across DeDe, DROP, KEY, CUT, ACT and STAY: two counterparties, an instance identifier, metadata resistance. Nothing about it is protocol-specific, so nothing in the sidecar is protocol-specific.

The sidecar does not know what a parcel, a storage space, a vehicle, a grant, a service, or a stay is. It moves typed envelopes between two parties bound to an opaque string. What that string means is the platform's business.

---

## Architecture

```
  your platform (any language)
            |
            |  local HTTP over a unix socket
            v
      cwtch-sidecar (Go, single static binary)
            |
            |  Cwtch protocol
            v
       Tor onion service  <-->  counterparty Cwtch client
```

The core is standard library only. Every Cwtch call is isolated behind one interface, so the full test suite runs against an in-process loopback transport with no Tor, no network, and no external dependency.

The counterparty client can be anything that speaks Cwtch. The sidecar makes no assumption about what is on the other end.

---

## Envelope Types

| Type | Replay resistant | Portable proof |
| ---- | ---------------- | -------------- |
| `msg` | no | no |
| `signal` | yes | no |
| `attestation` | yes | yes |

`msg` is freeform coordination. `signal` is a typed state change that must not be replayable, protected by a monotonic counter. `attestation` is a signal carrying a detached Ed25519 signature over canonical bytes, verifiable by a third party who was never on the channel.

Attestations exist because Cwtch conversations are ephemeral by design. That is correct for privacy and inconvenient for dispute resolution. An attestation is the piece that survives, and it survives without the sidecar ever holding a signing key.

---

## Boundaries

The sidecar signs nothing except Cwtch protocol traffic. Attestations are produced elsewhere and handed over already signed.

It does not read or write any chain, hold any settlement key, sign any transaction, or participate in settlement. It needs no RPC endpoint and no contract addresses.

It does not publish or discover counterparty addresses. Address exchange is a platform concern.

Buyer and provider protection remain platform-layer responsibilities, handled before the corresponding protocol call, exactly as they are without a sidecar.

---

## Dependency Position

Cwtch is an external project maintained by the Open Privacy Research Society. It does not carry the permanence guarantees of an immutable on-chain protocol.

If Cwtch stalls, changes, or disappears, the sidecar stops working and the protocols do not notice, because they were never dependent on it. That is why this is a separate, optional repository rather than a folder inside a template.

Template repositories published alongside the protocols do not import it. A template that never calls it behaves exactly as published.

---

## How to Run

The fastest path builds the binary and drives a full instance lifecycle on the loopback transport. No Tor, no network, no external dependency.

```
cd examples
chmod +x quickstart.sh
./quickstart.sh
```

For real use, build with the Cwtch transport and run against Tor:

```
go mod tidy -tags cwtch
CGO_ENABLED=1 go build -tags cwtch -o bin/sidecar ./cmd/sidecar
```

A Docker Compose stack and an example systemd unit are included.

---

## What This Repository Is

- A starter kit for adding coordination to a platform quickly
- A single shared component covering every Substrate protocol
- A daemon you run, a client file you copy, and infrastructure examples you adapt
- A minimal, auditable codebase with no external dependencies in its core

## What This Repository Is Not

- An SDK, a library, or a framework
- A platform, marketplace, service, or hosted offering
- A requirement of any Substrate protocol
- A wallet, signer, or custodian of any kind
- Anything the author operates, monitors, or supports

---

## Resources

- [Repository](https://github.com/pablo-chacon/cwtch-sidecar)
- [Per-protocol coordination patterns](https://github.com/pablo-chacon/cwtch-sidecar/blob/main/integration/per-protocol.md)
- [API reference](https://github.com/pablo-chacon/cwtch-sidecar/blob/main/docs/API.md)
- [Cwtch](https://cwtch.im)

---

## Final Note

The protocols do not need it. Nothing needs it.

It exists so that the option exists, and so that the same week of work is not spent six times.

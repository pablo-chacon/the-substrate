# Blockchain Microservices

Onchain Microservices (OMS) is an architectural pattern that treats a public blockchain as permanent, neutral, ownerless infrastructure for hosting immutable single-responsibility services. Each service has one function, a deterministic interface, and no operator. Services are independent and unaware of each other. Orchestration happens at the platform layer above. The pattern produces infrastructure that is permanent without condition, neutral without policy, and composable without coupling.

---

## The parallel

In a microservices architecture, a system is decomposed into small, independent services. Each service has a single responsibility.
Each service exposes a well-defined interface. Services do not know about each other. They are orchestrated at the layer above, 
by something that knows about all of them, while the services themselves remain unaware of what surrounds them.

The Substrate protocols follow the same pattern exactly.

Each protocol has a single responsibility: parcel settlement, storage settlement, vehicle settlement, digital rights settlement, service settlement, commodity settlement.
Each protocol exposes a deterministic interface: its smart contract ABI. No protocol knows the others exist. 
They are orchestrated by platforms at the layer above, while the protocols themselves remain unaware of what surrounds them.

---

## The differences

The analogy holds with two important differences, and both differences make the architecture stronger, not weaker.

**Permanence.**

A conventional microservice can be taken down, redeployed, or modified by its operator. The behavior of the service is only as stable as the operator chooses to make it.

These protocols are immutable. The behavior defined at deployment is the behavior forever. A platform built on DeDe today is building on the same settlement rail that will exist in ten years.
There is no operator who can change that.

**No operator.**

A conventional microservice is owned and operated by someone. That operator can be acquired, pressured, regulated, or captured.
The service behavior is only as neutral as the operator remains.

These protocols have no operator. Ownership is renounced at deployment. There is no entity that can modify the behavior, raise the fee, or gate access.
The interface is open permanently.

---

## Orchestration in practice

A platform that wants to build a logistics system does not need to modify DeDe or DROP. It builds an orchestration layer that calls both protocols independently,
the same way a backend service calls two independent microservices.

The protocols do not communicate with each other. They do not share state. The orchestration layer is the only thing that knows both exist.

This means:

- Removing one protocol from the stack does not break the other
- Each protocol can be upgraded, replaced, or extended at the platform layer without touching the protocol itself
- A platform can add any protocol to its stack at any time without coordination with any other party
- Two platforms can use the same protocol simultaneously without any interaction between them

---

## The single responsibility principle

In software engineering, the single responsibility principle states that a module should have one, and only one, reason to change.

These protocols cannot change at all. But the principle applies in a stronger sense: each protocol does one thing, and that one thing is defined completely and correctly.
There is no reason to change it because it is finished.

This is what makes composition reliable. When you build on a protocol you know exactly what it does, exactly what it will always do, and exactly what it will never do. 
There are no side effects, no hidden dependencies, no behavior that changes based on operator decisions.

---

## What this means for builders

If you are evaluating The Substrate protocols for a project, the microservices mental model is the right one to apply.

Identify which protocols cover the settlement functions your platform needs. Build your orchestration layer to call those protocols directly. 
Use the templates as reference implementations for the integration. Your platform adds the matching, discovery, compliance, and user experience layers. The protocols handle the settlement.

You are not building on a platform someone else controls. You are building on infrastructure that no one controls, the same way you build on TCP/IP.

---

Documentation, protocol repositories, and template repositories:

https://github.com/pablo-chacon/the-substrate/protocols

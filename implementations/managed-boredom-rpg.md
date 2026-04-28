# Managed Boredom RPG

Managed Boredom RPG is a minimal, deterministic CLI game designed to demonstrate authorization and ownership via CUT ERC-1155 tokens.

The game itself is intentionally simple, repetitive, and restrictive. The experience is not about winning fast. It is about understanding the system you are inside.

This repository contains game logic only. Authorization is handled externally through CUT.

---

## Concept: Managed Boredom

Managed Boredom is a dystopia without spectacle.

There are no flying cars. No neon skylines. No heroic resistance arcs.

Life functions. Everything works. Nothing improves.

The mathematics is calculated from real official statistics sourced from [Statistiska Centralbyrån](https://www.scb.se/).

The system architecture gives participants:

- Enough energy to continue
- Enough money to survive
- Existing options
- Low availability of choice

When the system fails:
- Responsibility is abstracted. 
- The system works. 

When the individual fails:
- Responsibility is enforced. 
- Enforcement is the system manifestation of caring.

---

## Goal

The goal of the game is simple: **Exit.**

To exit, the player must accumulate sufficient funds, obtain required documents, and maintain enough energy to complete the process. Most paths appear viable. Few paths are effective.

---

## How to Play

```
npm run build
npm start
```

Navigate to `http://localhost:3000` in your browser.

---

## Gameplay Loop

The game advances in monthly steps. Each month the player chooses one action: work, unemployment, illegal_work, visit_doctor, or rest.

Each action affects cash, energy, time, and future probabilities. The system reacts deterministically based on current state, configuration, and seeded randomness.

There is no save or load functionality. Every session is finite.

---

## Employment and Unemployment

All players begin employed. Immediately after the game starts employment is terminated due to reconstruction. A final salary is paid after tax. The player enters unemployment.

Unemployment can be managed through agency participation, independent job searching, or non-participation. Each path carries different energy costs, income effects, and job probabilities over time. Participation is encouraged. Non-participation is corrected.

---

## Healthcare

When frustration increases the system offers support — appointments, prescriptions, follow-ups. Healthcare interactions cost money, consume time, and do not meaningfully improve progress toward exit. They are not presented as punishment. They are presented as help.

---

## Illegal Activity

Some activities provide income without taxation. These consume significant energy, do not qualify as progress toward exit, and carry risk. The system monitors outcomes quietly.

---

## Determinism

All randomness in the game is seeded, reproducible, and deterministic. Given the same seed and choices, outcomes are identical. This ensures testability, fairness, and predictability for developers.

---

## CUT Integration

Managed Boredom RPG does not implement authorization itself. Access is gated externally via CUT ERC-1155 ownership, platform-level authentication, and JSON-RPC based ownership checks. The game will not start without a valid authorization token.

This demonstrates that CUT can be used for game access, software entitlement, and medium-agnostic ownership verification.

CUT does not attempt to prevent copying. Authorization is about access, not DRM.

---

## What This Repository Is

- A reference implementation of CUT authorization
- A deterministic game loop
- A proof of authorization flow
- A minimal, auditable codebase

## What This Repository Is Not

- A platform
- A marketplace
- A service
- A DRM system
- A content distribution solution

---

## Resources

- [Repository](https://github.com/pablo-chacon/managed-boredom-rpg) *(closed source, opens at CUT deployment)*
- [CUT Protocol](https://github.com/pablo-chacon/cut-protocol)

---

## Final Note

Managed Boredom is not a metaphor.

It is a system.
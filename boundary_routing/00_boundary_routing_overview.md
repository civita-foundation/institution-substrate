# ARC BR — Boundary Routing & Inter-Institution Executability (CI/EI Aligned Overview)

**Status:** IN PROGRESS
**ARC Identifier:** ARC BR
**Ontology Dependency:** ONTOLOGY.md v2.0 (LOCKED)

---

## Terminology Guardrail (Non-Negotiable)

* **Computable Institution (CI)** defines *what institutional state transitions are decidable*.
* **Executable Institution (EI)** makes CI outcomes *non-bypassable* through refusal-first routing, authority binding, and immutable memory.

Boundary Routing is defined **first at the CI level** as *computable continuation semantics*.
It becomes **EI behavior only when routing outcomes cannot be bypassed and are permanently recorded**.

Boundary Routing **does not itself grant execution authority**.

---

## Purpose

This ARC formalizes **Boundary Routing** as a first-class **institutional continuation mechanism** under trust-minimal conditions.

Boundary Routing defines **how a CI-determined institutional state transition may be continued or explicitly refused across institutional boundaries**, without introducing:

* discretion
* interpretation
* narrative reconciliation
* implicit trust

This ARC extends the Institution Substrate from:

* **single-institution computability** (CI → ENI → SFEU → TDV)
* to **cross-institution computable continuation**,

and supports **multi-institution executability** only when coupled with EI guarantees.

Boundary Routing is **not interoperability**.
It is **institutional state continuation**.

---

## Problem Statement

Institutions increasingly depend on actions that cross boundaries:

* firm → firm
* firm → state
* state → regulator
* platform → counterparty

Existing approaches rely on:

* APIs
* contracts
* audits
* reconciliation
* assumed trust

These approaches fail structurally under:

* low trust
* scale
* adversarial incentives
* delayed enforcement
* memory decay

Boundary Routing addresses this failure by making cross-institution continuation:

* **deterministic**
* **attributable**
* **explicitly refusable**
* **verifiable across time**

---

## Scope

### In Scope

This ARC defines:

* what Boundary Routing **is** (computable continuation)
* when routing is **permitted** or **refused**
* what **must be preserved** across boundaries
* how routing **fails explicitly**
* what qualifies as **conformant behavior**

This ARC is **normative**.

---

### Out of Scope

This ARC does **not** define:

* transport protocols
* cryptographic primitives
* networking topology
* identity systems
* pricing or business models
* governance or policy decisions
* application UX

Those belong to **engineering**, **product**, or **governance** layers.

---

## Assumptions (Non-Negotiable)

This ARC assumes:

1. **Ontology is Locked**
   All terms are defined in `ONTOLOGY.md v2.0`.
   No new ontology is introduced here.

2. **CI / EI Separation Holds**
   Boundary Routing defines *computable continuation*.
   EI alone guarantees *non-bypassable execution*.

3. **Execution vs Governance Separation Holds**
   Boundary Routing never performs governance, judgment, or rule creation.

4. **Trust-Minimal Conditions Are Default**
   No good faith, shared administration, or narrative reconciliation is assumed.

5. **TDV Exists**
   Verifiable institutional memory across time is required for EI-level guarantees.

6. **Failure Is Explicit**
   Silent failure, suppression, or ambiguity is forbidden.

If any assumption is violated, Boundary Routing is invalid.

---

## What Boundary Routing Is Not

Boundary Routing is **not**:

* messaging
* event streaming
* API orchestration
* data exchange
* interoperability middleware
* workflow integration
* federation

Those move **information**.

Boundary Routing moves **institutionally valid state transitions or explicit refusals**.

---

## Architectural Position

Boundary Routing sits:

* **above CI-defined execution (SFEU)**
* **below governance**

It enables:

* continuation of admissible institutional state
* traversal of obligations across institutions
* structural preservation of legitimacy

```
CI
⊃ ENI
⊃ SFEU
⊃ TDV
⊃ Boundary Routing
```

Boundary Routing may be *computed* without EI.
Boundary Routing becomes *unavoidable* only under EI.

---

## Table of Contents

* **BR-1** — Formal Definition & Invariants
* **BR-2** — Boundary SFEUs (Execution at the Boundary)
* **BR-3** — Obligation Packet (Cross-Boundary Payload)
* **BR-4** — Refusal & Non-Routing Semantics
* **BR-5** — Time & Memory Across Boundaries
* **BR-6** — Trust-Minimal Security Properties
* **BR-7** — Conformance & Standardization Surface

---

## Design Principle (One Line)

> **If an institutional state transition cannot be deterministically continued or explicitly refused across a boundary, it is not computably routable.**

Non-bypassability is an **EI property**, not a routing assumption.

---

## ARC Exit Criteria

This ARC is complete when:

1. Boundary routing can be computed without interpretation.
2. Refusal is explicit, attributable, and enumerable.
3. TDV verifiability survives across institutions and time.
4. Conformance can be tested independently of implementations.
5. No new ontology or authority is introduced.

---

## Normative Status

This ARC is **normative**.

All systems, protocols, or implementations that claim to support:

* Boundary Routing,
* Inter-Institution Executability, or
* Cross-Institution Execution Continuation

**MUST conform** to the requirements defined in BR-1 through BR-7.

Any deviation **MUST be explicitly declared as a fork** and must not claim conformance.

Silence, partial adoption, or semantic substitution does not constitute conformance.

---

**Next File:**
`01_br1_formal_definition_and_invariants.md`

# ARC BR — Boundary Routing & Inter-Institution Executability
## Overview

**Status:** IN PROGRESS  
**ARC Identifier:** ARC BR  
**Ontology Dependency:** ONTOLOGY.md v2.0 (LOCKED)

---

## Purpose

This ARC formalizes **Boundary Routing** as a first-class execution concept.

Boundary Routing defines **how institutional execution continues across institutional boundaries** under trust-minimal conditions, without introducing discretion, interpretation, or implicit trust.

This ARC extends the Institution Substrate from:
- **single-institution executability** (CI → ENI → SFEU → TDV → DNI)
to:
- **multi-institution executability**

Boundary Routing is not interoperability.
It is **execution continuation**.

---

## Problem Statement

Institutions increasingly depend on actions that cross boundaries:
- firm → firm
- firm → state
- state → regulator
- platform → counterparty

Existing approaches rely on:
- APIs
- contracts
- audits
- reconciliation
- trust

These approaches fail structurally under:
- low trust
- scale
- adversarial incentives
- delayed enforcement
- memory decay

Boundary Routing addresses this failure by making cross-institution propagation **deterministic, attributable, and verifiable**.

---

## Scope

### In Scope

This ARC defines:
- what Boundary Routing **is**
- when routing is **permitted**
- what **must be preserved**
- how routing **fails explicitly**
- what qualifies as **conformant**

This ARC is **normative**.

---

### Out of Scope

This ARC does **not** define:
- transport protocols
- cryptographic primitives
- networking topology
- identity systems
- pricing or business models
- governance or policy decisions
- application UX

Those belong to **engineering** or **product** layers.

---

## Assumptions (Non-Negotiable)

This ARC assumes:

1. **Ontology is Locked**  
   All terms are defined in `ONTOLOGY.md v2.0`.  
   No new ontology is introduced here.

2. **Execution vs Governance Separation Holds**  
   Boundary Routing operates strictly in the execution domain.

3. **Trust-Minimal Conditions Are Default**  
   No good faith, shared administration, or narrative reconciliation is assumed.

4. **TDV Exists**  
   Verifiable institutional memory across time is required.

5. **Failure Is Explicit**  
   Silent failure is forbidden.

If any assumption is violated, Boundary Routing is invalid.

---

## What Boundary Routing Is Not

Boundary Routing is **not**:
- messaging
- event streaming
- API orchestration
- data exchange
- interoperability middleware
- workflow integration
- federation

Those move **information**.

Boundary Routing moves **institutional state**.

---

## Architectural Position

Boundary Routing sits **above SFEU execution** and **below governance**.

It is the mechanism that allows:
- execution to propagate
- obligations to traverse institutions
- legitimacy to be enforced structurally


```
CI
⊃ ENI
⊃ SFEU
⊃ TDV
⊃ Boundary Routing
```


---

## Table of Contents (Upcoming Only)

- **BR-1** — Formal Definition & Invariants  
- **BR-2** — Boundary SFEUs (Execution at the Boundary)  
- **BR-3** — Obligation Packet (Cross-Boundary Payload)  
- **BR-4** — Refusal & Non-Routing Semantics  
- **BR-5** — Time & Memory Across Boundaries  
- **BR-6** — Trust-Minimal Security Properties  
- **BR-7** — Conformance & Standardization Surface  

---

## Design Principle (One Line)

> **If an institutional action cannot be deterministically continued or explicitly refused across a boundary, it is not executable.**

---

## ARC Exit Criteria

This ARC is complete when:

1. Boundary routing can occur without interpretation.
2. Refusal is explicit, attributable, and non-political.
3. TDV verifiability survives across institutions and time.
4. Conformance can be tested independently.
5. No new ontology is required.

---

## Normative Status

This ARC is **normative**.

All systems, protocols, or implementations that claim to support:
- Boundary Routing,
- Inter-Institution Executability, or
- Cross-Institution Execution Continuation

**MUST conform** to the requirements defined in BR-1 through BR-7.

Any deviation **MUST be explicitly declared as a fork** and must not claim conformance.

Silence, partial adoption, or semantic substitution does not constitute conformance.

---

**Next File:**  
`01_br1_formal_definition_and_invariants.md`

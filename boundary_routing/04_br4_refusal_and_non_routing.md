# ARC BR — Boundary Routing & Inter-Institution Executability

## BR-4 — Refusal & Non-Routing Semantics (CI/EI Aligned)

**Status:** IN PROGRESS
**Progress Marker:** BR-4
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Terminology Guardrail (Non-Negotiable)

* **Computable Institution (CI)** determines *whether boundary continuation is admissible or must be refused*.
* **Executable Institution (EI)** makes refusal outcomes *non-bypassable* and preserves them in immutable memory.

**Refusal is a CI-level outcome.**
Refusal becomes *final and unavoidable* only under EI guarantees.

---

## Purpose

This file defines **Refusal and Non-Routing Semantics** for Boundary Routing.

Refusal is not an error condition or operational failure.
Refusal is a **legitimate, first-class institutional outcome** that preserves integrity by **withholding continuation** when routing invariants cannot be satisfied.

Boundary Routing without explicit refusal semantics collapses into silent trust assumptions and is therefore invalid.

---

## Scope & Non-Goals

### In Scope

* Definition of refusal vs non-routing
* Legitimate refusal conditions
* Explicit refusal structure and attribution
* Refusal propagation semantics
* Relationship to TDV and institutional memory

### Out of Scope

* Dispute resolution
* Appeals or governance workflows
* Penalty enforcement
* Human negotiation
* Messaging or notification UX

---

## BR-4.1 Refusal vs Non-Routing

**Refusal** is an explicit, attributable CI-level outcome produced by a BSFEU.

**Non-Routing** is the absence of routing *without* an explicit refusal.

Only **Refusal** is permitted.

| Condition                   | Allowed |
| --------------------------- | ------- |
| Explicit refusal            | ✅       |
| Silent non-routing          | ❌       |
| Timeout without attribution | ❌       |
| Implicit acceptance         | ❌       |

If routing does not occur, refusal **MUST** be emitted.

---

## BR-4.2 Legitimate Refusal Conditions (CI-Level)

A BSFEU **MUST refuse** boundary continuation when any of the following hold:

* Authority provenance cannot be verified
* Rule identity is incompatible or unknown
* Institutional time ordering is violated
* TDV evidence is missing or unverifiable
* Obligation Packet replay is detected
* Local legitimacy is withdrawn
* Local acceptance constraints fail deterministically

Refusal is **structural**, not discretionary.
No balancing, negotiation, or interpretation is permitted.

---

## BR-4.3 Explicit Refusal Requirements

A refusal **MUST** include:

* `failure_code` (enumerated, closed set)
* `refusal_time_ref`
* `packet_id`
* `origin_institution_id`
* optional `refusal_tdv_ref`

A refusal **MUST NOT** include:

* explanations
* narratives
* suggested remedies
* human commentary

Refusal communicates *fact*, not *judgment*.

---

## BR-4.4 Refusal Propagation Semantics

Refusal is **terminal** for the specific routing attempt.

Propagation rules:

* Refusal applies only to the specific `packet_id`
* Refusal does not retroactively invalidate prior institutional state
* Refusal may be observed by:

  * the originating institution
  * authorized auditors
* Refusal may itself be routed **only as evidence**, never as obligation

No automatic retries are permitted.

Under EI, refusal becomes non-bypassable and permanently recorded.

---

## BR-4.5 TDV & Memory Implications

Refusal **MUST be recorded** in TDV when EI guarantees are present.

TDV preserves:

* that routing was attempted
* that continuation was refused
* when refusal occurred
* by which institution

This ensures:

* refusals cannot be erased
* silent censorship is impossible
* drift via suppression is detectable

Refusal is part of institutional memory, not narrative history.

---

## BR-4.6 Forbidden Failure Modes

The following are **explicitly forbidden**:

* Silent drops
* Infinite retries
* Human-in-the-loop overrides
* Conditional or “soft” refusals
* Narrative explanations embedded in refusal
* Timeouts without attribution

Any occurrence invalidates Boundary Routing conformance.

---

## Completion Criteria

BR-4 is complete when:

1. Refusal is unambiguously defined as a CI-level outcome
2. All non-routing paths are explicit and attributable
3. EI responsibility is limited to non-bypassability and memory
4. TDV captures refusal as first-class institutional memory
5. No trust assumptions are required to interpret refusal

---

**Next File:**
`05_br5_time_and_memory_across_boundaries.md`

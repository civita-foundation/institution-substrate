# ARC BR — Boundary Routing & Inter-Institution Executability
## BR-4 — Refusal & Non-Routing Semantics

**Status:** IN PROGRESS  
**Progress Marker:** BR-4  
**Ontology Assumption:** ONTOLOGY.md v2.0 is LOCKED

---

## Purpose

This file defines **Refusal and Non-Routing Semantics** for Boundary Routing.

Refusal is not an error condition or operational failure.  
Refusal is a **legitimate, first-class execution outcome** that preserves institutional integrity by **withholding legitimacy** when routing invariants cannot be satisfied.

Boundary Routing without explicit refusal semantics collapses into silent trust assumptions.

---

## Scope & Non-Goals

### In Scope
- Definition of refusal vs non-routing
- Legitimate refusal conditions
- Refusal visibility and attribution
- Propagation semantics
- Relationship to legitimacy and TDV

### Out of Scope
- Dispute resolution
- Appeals or governance workflows
- Penalty enforcement
- Human negotiation
- Messaging or notification UX

---

## Table of Contents (Upcoming Only)

- BR-4.1 Refusal vs Non-Routing
- BR-4.2 Legitimate Refusal Conditions
- BR-4.3 Explicit Refusal Requirements
- BR-4.4 Refusal Propagation Semantics
- BR-4.5 TDV & Memory Implications
- BR-4.6 Forbidden Failure Modes

---

## BR-4.1 Refusal vs Non-Routing

**Refusal** is an explicit, attributable execution outcome produced by a BSFEU.

**Non-Routing** is the absence of routing *without* an explicit refusal.

Only **Refusal** is permitted.

| Condition | Allowed |
|---------|--------|
Explicit refusal | ✅ |
Silent non-routing | ❌ |
Timeout without attribution | ❌ |
Implicit acceptance | ❌ |

If routing does not occur, refusal **MUST** be emitted.

---

## BR-4.2 Legitimate Refusal Conditions

A BSFEU **MUST refuse** routing when any of the following hold:

- Authority provenance cannot be verified
- Rule identity is incompatible or unknown
- Temporal ordering is violated
- TDV evidence is missing or unverifiable
- Packet replay is detected
- Local legitimacy is withdrawn
- Local acceptance constraints fail deterministically

Refusal is **structural**, not discretionary.

---

## BR-4.3 Explicit Refusal Requirements

A refusal **MUST** include:

- `failure_code` (enumerated, closed set)
- `refusal_time_ref`
- `packet_id`
- `origin_institution_id`
- optional `refusal_tdv_ref`

Refusal **MUST NOT** include:
- explanations
- narratives
- suggested remedies
- human commentary

Refusal communicates *fact*, not *judgment*.

---

## BR-4.4 Refusal Propagation Semantics

Refusal is **terminal** for the attempted routing instance.

Propagation rules:

- Refusal applies only to the specific `packet_id`
- Refusal does not retroactively invalidate prior execution
- Refusal may be observed by:
  - the originating institution
  - authorized auditors
- Refusal may itself be routed **only as evidence**, not as obligation

No automatic retries are permitted.

---

## BR-4.5 TDV & Memory Implications

Refusal **MUST be recorded** in TDV.

TDV preserves:
- that routing was attempted
- that legitimacy was withheld
- when refusal occurred
- by which institution

This ensures:
- refusal cannot be erased
- silent censorship is impossible
- drift via suppression is detectable

Refusal is part of institutional memory.

---

## BR-4.6 Forbidden Failure Modes

The following are **explicitly forbidden**:

- Silent drops
- Infinite retries
- Human-in-the-loop overrides
- Conditional or “soft” refusals
- Narrative explanations embedded in refusal
- Timeouts without attribution

Any occurrence invalidates Boundary Routing conformance.

---

## Completion Criteria

BR-4 is complete when:

1. Refusal is structurally distinct from failure.
2. All non-routing paths are explicit and attributable.
3. TDV captures refusal as first-class memory.
4. No trust assumptions are required to interpret refusal.

---

**Next File:**  
`05_br5_time_and_memory_across_boundaries.md`

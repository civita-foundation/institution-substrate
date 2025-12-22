# ARC 3 — SFEU
## Status Function Execution Units

---

## Why SFEU Exists

CI → DNI answers **how rules execute**.  
SFEU answers **what executes**.

Institutions do not act on “things.”
They act on **status functions**:
- rights
- obligations
- permissions
- roles
- entitlements

SFEU is the unit that **materializes status functions as executable state**.

---

## Origin (Conceptual Lineage)

From John Searle:
> “X counts as Y in context C”

SFEU operationalizes this:
> **X is not declared as Y — X *executes* as Y under C.**

---

## Definition: Status Function Execution Unit (SFEU)

An **SFEU** is a minimal executable unit that:
- evaluates a context
- applies a rule
- produces a legally / institutionally valid state transition
- records the transition immutably

It is not a service.
It is not an API.
It is an **institutional atom**.

---

## What an SFEU Is NOT

- Not a microservice
- Not a workflow step
- Not an AI agent
- Not a human approval
- Not a smart contract (though it may resemble one)

Those optimize *process*.
SFEU **enacts institutional reality**.

---

## SFEU Core Structure

```
SFEU {
Context C
Input State S
Rule R
Guard Conditions G
Transition T
Memory Write M
}
```


If `G` holds → `T` fires → `M` commits  
If not → explicit failure

No silent paths.

---

## Example (Concrete)

**Institutional fact:**  
> “Payment clears obligation”

### CI (descriptive)
- If payment received, obligation is fulfilled.

### DNI + SFEU (executable)
- SFEU evaluates:
  - payment receipt
  - amount
  - timestamp
  - counterparty identity
- If valid:
  - obligation status → `fulfilled`
  - penalty rights → revoked
  - receipt rights → activated
  - memory committed

No discretion. No delay.

---

## SFEU and Time

Each SFEU execution:
- occurs at a specific time
- references a rule version
- creates an irreversible state

Time is not external.
Time is **institutionalized**.

---

## SFEU and Memory (TDV Hook)

Every SFEU execution writes to:
- institutional memory
- verifiable lineage
- replayable history

This enables:
- audit without interpretation
- rollback by rule revision (not override)
- drift detection

---

## Composition: Institutions as SFEU Graphs

Institutions are not hierarchies.
They are **directed graphs of SFEUs**.

```
[SFEU A] → [SFEU B] → [SFEU C]
↓ ↘
[SFEU D] [SFEU E]
```


Coordination = graph traversal under constraints.

---

## Failure Semantics (Critical)

SFEU failures are:
- explicit
- typed
- logged

Examples:
- Rule violation
- Missing prerequisite
- Time window expired
- Identity mismatch

Failure ≠ corruption  
Failure = signal

---

## Corruption Revisited (ARC 2 Alignment)

In SFEU systems:
- corruption cannot hide
- it manifests as:
  - bypass attempts
  - rule mutation
  - execution suppression

These are **governance failures**, not moral ones.

---

## Governance Touchpoint

Humans interact with SFEU **only** via:
- rule creation
- rule revision
- rule retirement

Never execution override.

This preserves:
- trust
- evolution
- accountability

---

## Why SFEU Is the Hard Part

Because it:
- removes informal power
- collapses “exceptions”
- forces completeness
- exposes institutional ambiguity

Most institutions avoid this layer.

---

## SFEU in One Sentence

> **An SFEU is the smallest unit at which social reality becomes executable.**

---

## Transition Forward

Next in ARC 3:
> **TDV Integration**  
How time, dependency, and verifiable memory bind SFEUs into a living institution.

---

**ARC 3 STATUS:** ACTIVE

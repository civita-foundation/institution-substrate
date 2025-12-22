# ARC 3 — Rule Formalization
## From Legal Language to Executable Structure

---

## Why Rule Formalization Is the Bottleneck

Most institutions fail not because rules are absent,
but because rules are:
- ambiguous
- overloaded
- exception-ridden
- unenforceable without discretion

If a rule requires interpretation at execution time,
it is **not computable**.

---

## Definition: Formalized Rule

A **formalized rule** is a rule that satisfies all of the following:

1. **Explicit Preconditions**  
   All inputs required for execution are declared.

2. **Finite State Space**  
   The rule operates over known, enumerable states.

3. **Deterministic Transition**  
   Given the same inputs, the same output always occurs.

4. **Totality (No Gaps)**  
   Every valid input produces an outcome (including rejection).

5. **No Runtime Interpretation**  
   Meaning is resolved at design time, not execution time.

---

## Rule ≠ Policy ≠ Law

| Layer | Purpose | Formalizable? |
|---|---|---|
| Law | Authority & legitimacy | Partially |
| Policy | Intent & guidance | Rarely |
| Rule | Execution logic | Yes |

CI operates **only** at the rule layer.

Politics chooses laws.  
Management writes policies.  
CI executes rules.

---

## Canonical Rule Structure

Every computable rule can be reduced to:

```
IF <preconditions>
AND <state constraints>
THEN <state transition>
ELSE <explicit failure state>
```


No “reasonable judgment.”  
No “case-by-case.”  
No “subject to approval.”

If such phrases exist, the rule is **non-computable**.

---

## Discretion Elimination Principle

> Any discretion at execution time must be moved to:
> - rule design time, or
> - governance time

Never execution time.

This is the single most important CI principle.

---

## Example 1: Non-Formalized Rule (Typical)

> “A refund may be granted if the request is reasonable and justified.”

Problems:
- What is reasonable?
- Who decides?
- Based on what evidence?
- What if they disagree?

This rule cannot be executed.
It only enables discretion.

---

## Example 2: Formalized Rule (CI-Compatible)

> Refund is granted if:
> - payment timestamp ≤ 7 days ago
> - service usage ≤ 10%
> - request submitted via authenticated channel

Else:
> refund denied with reason code R-03

This rule is:
- explicit
- enumerable
- deterministic
- auditable

---

## Rule Explosion Myth

Objection:
> “Formalization will create too many rules.”

Response:
- complexity already exists
- it is currently hidden inside discretion
- CI makes it visible, not larger

Hidden complexity is corruption fuel.

---

## Rule Compression vs Rule Expansion

Two valid strategies:

### 1. Rule Compression
- Fewer rules
- Stricter eligibility
- Lower discretion
- Lower trust burden

### 2. Rule Expansion
- More cases handled
- More explicit branches
- Still deterministic
- Higher design effort

Both are valid.
**Discretion is not.**

---

## Exception Handling Is Not Discretion

In CI:
- exceptions are **states**
- not permissions

Example:
- `EXCEPTION: FORCE_MAJEURE`
- handled by predefined fallback rules

If humans invent exceptions during execution,
the institution has failed structurally.

---

## Rule Formalization Requires Ontology

Rules cannot be formalized without:
- defined actors
- defined artifacts
- defined states
- defined transitions

This links back to:
- ARC 1 (ontology)
- ARC 2 (trust & coordination)

Rule formalization is not syntax.
It is **ontological closure**.

---

## Rule Validity vs Rule Justice

CI does **not** guarantee:
- fairness
- morality
- optimality

It guarantees:
- predictability
- auditability
- resistance to corruption drift

Justice is upstream.
Execution is downstream.

---

## What Rule Formalization Enables

Once rules are formalized:
- execution can be externalized
- memory can be recorded immutably
- institutions become testable
- simulations become possible

This sets the stage for:
- **Digital Native Institutions (ARC 4)**
- **Status-Function Execution Units (ARC 5)**

---

## Transition

We now have:
- computable institutions (ARC 3.0)
- formalized rules (ARC 3.1)

Next required step:
> **Separating rule definition from rule execution**

This leads to **Execution vs Governance Separation**.

---

**ARC 3 STATUS:** ACTIVE  


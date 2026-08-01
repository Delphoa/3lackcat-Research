# Section 7 — MVP Boundary and Critical Path

> **Executive purpose:** Define the smallest safe product proof and the sequence of dependencies that must exist before Function 8 can influence real work.

[Previous: Section 6 — Scoring and Decisions](06_scoring_and_decision_mechanics.md) · [Review index](README.md) · [Next: Section 8 — Risk Review](08_risk_review.md)

The MVP should test whether transparent probability re-ranking improves decision quality under strict governance. It should not attempt to prove autonomous adaptation, unrestricted context use, opaque model superiority, or production-scale performance.

## 7.1 MVP Promise

Given proposals from at least two approved source types, the MVP will:

- admit only valid, authorized, and unique candidate events;
- apply declared and versioned calibration behavior;
- produce estimated likelihood and separate priority utility;
- create one deterministic and explainable global order;
- reserve unique selections and hand bounded recommendations to the conservative scheduler;
- preserve enough evidence to replay and evaluate every decision.

The MVP does not authorize a run, allocate unbounded resources, dispatch work independently, or determine whether a candidate is correct.

## 7.2 Minimum End-to-End Workflow

1. Receive versioned proposals from approved sources.
2. Enforce scope, policy, validity, provenance, and exact-duplicate controls.
3. Apply the appropriate calibration basis or label the evidence as unvalidated.
4. Assemble the minimum approved evidence needed for an explainable decision.
5. Produce separate likelihood and priority values with visible uncertainty.
6. Apply deterministic ordering and a documented tie rule.
7. Reserve selected candidates through the authoritative ledger.
8. Create a versioned scheduler handoff.
9. Record scheduler and verifier outcomes for offline evaluation.
10. Reproduce the ranking from the preserved evidence and version snapshot.

The workflow is complete only when an independent evaluator can trace a representative batch from approved proposal through ranking, reservation, scheduler handoff, and authoritative outcome.

## 7.3 MVP Non-Goals

The MVP excludes:

- learned or opaque mixture models;
- autonomous live weight changes;
- advanced Bayesian or contextual-bandit scheduling;
- cross-run learning from recovered plaintext without separate approval;
- unbounded target-context enrichment;
- distributed ranking or global cross-organization dedupe;
- direct ranker-to-verifier dispatch;
- production deployment or automated high-cost use;
- claims of calibrated probability or efficacy without controlled evidence.

These exclusions protect the project from mistaking technical sophistication for demonstrated value.

## 7.4 Critical Path

```text
scope and policy contract
  -> candidate identity and provenance
  -> authoritative uniqueness and reservation
  -> calibration registry
  -> transparent probability re-ranker
  -> deterministic scheduler handoff
  -> conservative scheduler interface
  -> evaluation, safety, and replay evidence
```

### Executive Stage Gates

| Gate | Required capability | Evidence required to advance |
|---|---|---|
| Governance foundation | Enforceable scope, policy, source approval, privacy, and ownership boundaries | Bypass tests fail safely and sensitive-data handling is approved |
| Comparable evidence | Versioned calibration and explicit unvalidated states | At least two source types can be compared without raw-score substitution |
| Controlled decision function | Transparent likelihood, separate utility, explanations, deterministic order, and unique reservation | Ranking and batch replay succeed from preserved snapshots |
| Measured value | Conservative scheduler handoff and controlled baseline evaluation | Equal-budget evidence, complete attribution, safety results, and documented limitations |

### Advancement Rule

Function 8 should not influence real workloads until the governance foundation exists. Advanced adaptation should not receive priority until the transparent MVP has demonstrated repeatable value and stable controls.

**Executive takeaway:** The MVP is a controlled decision and evidence system. Its first obligation is to prove trustworthy behavior; performance sophistication comes later.


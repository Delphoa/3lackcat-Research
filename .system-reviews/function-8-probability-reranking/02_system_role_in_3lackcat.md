# Section 2 — System Role in the 3lackcat Ecosystem

> **Executive purpose:** Clarify where Function 8 sits, what it changes, and which surrounding components retain decision authority.

[Previous: Section 1 — Executive Summary](01_executive_summary.md) · [Review index](README.md) · *Section 3 is not included in this initial publication.*

Function 8 sits at the transition between candidate creation and resource allocation. Upstream components propose candidates and attach evidence. Function 8 compares eligible proposals and recommends an order. Downstream components allocate budgets, dispatch work, determine verified outcomes, and produce defensive reporting.

```text
approved candidate sources
  -> Function 8: compare and prioritize
  -> conservative scheduler: allocate and dispatch
  -> deterministic verifier: confirm or reject
  -> reporting and evaluation: explain and measure
```

This position makes Function 8 influential but not authoritative. Its decisions can affect how quickly the system reaches useful outcomes and how efficiently it uses approved resources. For that reason, its inputs, reasoning, and versions must remain visible and replayable.

## 2.1 Relationship to 3lackcat

3lackcat's product promise depends on more than candidate generation. Multiple sources can each offer useful proposals, but their scores and ordering conventions are not naturally comparable. Without Function 8, the system would depend on fixed source order, manual recipes, or isolated queues. That would weaken the central claim that 3lackcat can orchestrate evaluation by probability and evidence.

Function 8 should give the parent system three capabilities:

1. **A unified priority view:** Approved candidate sources can be considered together rather than in separate sequences.
2. **Decision traceability:** Every position in the queue can be connected to source evidence, calibration state, and a declared ranking policy.
3. **A measurable product hypothesis:** Leadership can compare the unified ordering with simpler baselines and decide whether the added capability earns its cost and risk.

Function 8 is therefore part of the core value path, but only after foundational governance and data controls are reliable.

## 2.2 Relationship to Dedupe, Scheduling, and Reporting

The ranker relies on several companion functions and should not absorb their responsibilities.

### Deduplication and Coverage

The ledger determines whether an exact candidate has already been seen, reserved, or evaluated. Function 8 may use broader overlap and saturation information to favor useful novelty, but it should not replace the ledger's authoritative uniqueness decision.

The recommended relationship has two control points:

- Before ranking, confirmed exact duplicates are excluded and broader coverage information is supplied as advisory evidence.
- Before scheduler handoff, selected candidates are uniquely reserved so concurrent work cannot duplicate the batch.

### Conservative Scheduling

The scheduler decides how approved resources are distributed and when a batch is dispatched. Function 8 recommends candidate order; the scheduler applies budget caps, operational limits, source constraints, and stop conditions. Keeping these responsibilities separate prevents a high ranking score from becoming an uncontrolled spending decision.

### Reporting and Evaluation

Reporting should use rank explanations and version records to show how verified outcomes were prioritized. Evaluation should determine whether Function 8 improves approved outcomes relative to fixed sequencing and best-single-source baselines. Neither reporting nor evaluation should expose sensitive candidate content.

## 2.3 Relationship to Verification and Authority

The authority model should remain simple enough for an executive or auditor to explain:

- **Policy authority decides what is permitted.**
- **The ledger decides exact uniqueness and reservation state.**
- **Function 8 recommends relative priority.**
- **The scheduler decides bounded operational allocation.**
- **The deterministic verifier decides result truth.**
- **Humans approve sensitive data use, high-cost expansion, and major autonomy changes.**

No score should silently acquire the authority of another component. In particular, a high-ranked candidate is still only an attempted evaluation until the deterministic verifier produces an authoritative result.

### Executive Oversight Questions

Leadership should be able to answer:

1. Can any score override authorization, uniqueness, or budget limits?
2. Can a decision be reproduced from its preserved inputs and versions?
3. Is it clear when a value is observed, inferred, or verified?
4. Can the system pause safely when the ledger, calibration, or policy state is unavailable?
5. Is sensitive content excluded from ranking and reporting records?

**Executive takeaway:** Function 8 belongs in the decision path, not the authority path. Its strategic value depends on strengthening coordination without blurring who controls permission, spending, uniqueness, or truth.


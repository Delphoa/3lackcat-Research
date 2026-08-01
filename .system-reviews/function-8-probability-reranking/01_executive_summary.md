# Section 1 — Executive Summary

> **Executive purpose:** Decide whether Function 8 is strategically aligned, valuable, feasible, and appropriate for a controlled MVP.

[Previous: Document Control](00_document_control.md) · [Review index](README.md) · [Next: Section 2 — Role in 3lackcat](02_system_role_in_3lackcat.md)

Function 8 is the proposed decision layer that converts candidate proposals from several approved sources into one prioritized and explainable queue. Its purpose is to help 3lackcat spend a finite verification budget on the candidates most likely to create new defensive value, while preserving governance, provenance, and deterministic verification as separate authorities.

The capability is strategically important because 3lackcat's core thesis is not merely to generate candidates. It is to order approved candidates better than a static sequence, explain why that order was chosen, and prove whether the ordering creates measurable value. Function 8 is therefore a P1 product-value component: the system can technically operate without it, but cannot fully deliver probability-ranked orchestration without it.

The recommended position is **conditional approval for a controlled MVP**. The first version should be transparent, fixed, versioned, and replayable. It should not begin as an opaque learned model or an autonomously self-modifying decision engine.

## 1.1 Assessment Verdict

| Dimension | Verdict | Executive interpretation |
|---|---:|---|
| Strategic alignment | High | The function directly supports 3lackcat's probability-ranked orchestration thesis. |
| Potential user value | High | Better ordering may reduce wasted evaluation and improve time to useful, defensible results. |
| Basic delivery feasibility | High | A simple and transparent first version is practical once its dependencies are available. |
| Evidence and calibration maturity | Medium | Comparable probability claims require approved data, controlled evaluation, and ongoing validation. |
| Operational efficiency | Medium-High | Decision overhead should be modest relative to verification, but this remains to be measured. |
| Measurable performance improvement | Unproven | Improvement is plausible, not established. Equal-budget baseline testing is mandatory. |
| Product fit | Conditional yes | Build only behind authorization, uniqueness, privacy, replay, and evidence gates. |

### Executive Verdict

Function 8 is worth pursuing as an accountable decision-support layer. It is not ready to be treated as an authority, autonomous scheduler, or source of truth. Approval should fund a product proof, not presume a performance result.

## 1.2 Primary Value Proposition

The executive value of Function 8 is disciplined allocation of attention. It should make several otherwise incompatible candidate sources comparable enough to support one consistent priority order.

### Expected Organizational Value

- **For operators:** A clearer and more defensible explanation of which approved candidates should be evaluated first.
- **For the parent system:** One global decision surface instead of disconnected source queues and fixed sequencing.
- **For research leadership:** Evidence about which sources, semantic families, and combinations create marginal value under equal budgets.
- **For security and governance:** A visible separation between inferred priority, scheduling authority, and deterministic verification truth.
- **For product leadership:** A measurable test of whether 3lackcat's orchestration thesis creates enough value to justify further investment.

### What Success Would Look Like

Success is not a more complex score. Success is a repeatable improvement in one or more approved outcomes: useful coverage within a fixed budget, lower duplicate waste, faster time to a verified result, better explanation, or stronger traceability.

### What Would Invalidate the Value Case

The value case should be rejected or narrowed if a simple fixed ordering performs equally well, if source scores cannot be compared responsibly, if the explanation record cannot reconstruct decisions, or if the component introduces unacceptable privacy or governance risk.

## 1.3 Product Boundary

Function 8 should be understood as an **advisory ranker**. It recommends order; it does not decide permission, dispatch, or truth.

| Decision | Responsible authority | Function 8's role |
|---|---|---|
| Is the run and source authorized? | Authorization and Scope Gate | Must accept the decision; cannot override it |
| Is the exact candidate unique and available? | Deduplication and Coverage Ledger | Uses the decision and coverage evidence |
| Which eligible candidate has higher priority? | Function 8 | Produces an explainable recommendation |
| How is the approved budget allocated and dispatched? | Conservative Scheduler | Receives ranked batches; retains dispatch authority |
| Did a candidate match an in-scope target? | Deterministic Verifier | Function 8 cannot establish this result |
| May sensitive results be exported or reused? | Policy and human approval process | Must not infer or grant permission |

Four boundaries are non-negotiable:

1. Authorization, policy failure, invalid data, and confirmed exact duplicates are hard exclusions, not scoring preferences.
2. A ranking score is an inference and must never be presented as a verified result.
3. Sensitive candidate content should not appear in ranking explanations, executive reporting, or routine logs.
4. High-cost or expanded influence requires human approval supported by calibration and controlled evaluation evidence.

## 1.4 Recommended Build Classification

- **P0 dependencies:** Authorization and policy enforcement, privacy-preserving identity, immutable source/version provenance, authoritative duplicate handling, and versioned calibration records.
- **P1 core product value:** Transparent comparison of approved sources, distinct likelihood and priority outputs, deterministic ordering, and understandable decision explanations.
- **P2 evidence and safety:** Calibration monitoring, replay tests, baseline comparison, privacy validation, drift review, and operational observability.
- **P4 expansion:** Learned ensembles, live adaptive weight changes, advanced context feedback, and continuous cross-run learning.

### Recommended Executive Decision

Approve a narrow P1 MVP only after the P0 dependencies are confirmed. Require explicit evidence gates before promoting Function 8 from controlled research to broader operational influence.

**Executive takeaway:** Function 8 is strategically aligned and potentially high value, but the investment case rests on transparent behavior and controlled evidence—not on the sophistication of the ranking method.


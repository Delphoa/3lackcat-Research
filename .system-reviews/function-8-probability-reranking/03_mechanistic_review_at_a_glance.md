# Section 3 — Mechanistic Review at a Glance

> **Executive purpose:** Explain the complete Function 8 operating model as a short sequence of controlled business decisions.

[Previous: Section 2 — Role in 3lackcat](02_system_role_in_3lackcat.md) · [Review index](README.md) · [Next: Section 4 — How It Should Operate](04_how_probability_reranking_should_operate.md)

Function 8 should operate as a controlled funnel. It begins with candidate proposals from approved sources and ends with a bounded, explainable recommendation to the scheduler. Each stage reduces ambiguity and increases accountability.

```text
admit only approved proposals
  -> establish score comparability
  -> assemble relevant evidence
  -> estimate likelihood
  -> adjust operational priority
  -> order deterministically
  -> reserve unique selections
  -> hand off with explanation
  -> measure outcomes without silently changing policy
```

The mechanism should be intentionally conservative. A candidate can be highly rated only after it is eligible. A ranking can influence order only after its evidence is traceable. An outcome can be called verified only after the deterministic verifier confirms it.

## 3.1 Function Inventory

| Stage | Priority | Executive description | Output | Principal control |
|---|---:|---|---|---|
| Admission | P0 | Confirms that the proposal is valid, authorized, and appropriate to consider | Eligibility decision | Scores cannot override exclusion |
| Uniqueness check | P0 | Prevents already-seen exact candidates from consuming the same budget again | Unique, duplicate, or restricted status | Ledger remains authoritative |
| Calibration | P1 | Translates source-specific scores into declared comparable evidence | Comparable likelihood band and confidence | Unvalidated values are labeled, not disguised |
| Evidence assembly | P1 | Combines source, semantic, context, novelty, cost, and uncertainty information | Versioned decision evidence | Only approved, traceable evidence may influence rank |
| Likelihood and utility scoring | P1 | Separates estimated success likelihood from operational priority | Two distinct advisory values | Utility is not represented as probability |
| Deterministic ordering | P1 | Creates a stable global order and bounded candidate window | Ranked queue or batch proposal | Same evidence and version produce the same result |
| Explanation and handoff | P1/P2 | Provides the scheduler with an accountable recommendation | Manifest, reason summary, and reservation references | Ranker cannot dispatch or verify |
| Evaluation and feedback | P2/P4 | Measures whether the recommendation created value and informs approved future versions | Performance and calibration evidence | MVP learning is offline and approval-gated |

### What the Mechanism Is Designed to Achieve

- Replace fixed source sequencing with one evidence-based ordering.
- Preserve the strengths and provenance of multiple approved sources.
- Reduce duplicate or low-value use of a finite evaluation budget.
- Give leadership a measurable basis for deciding whether the function deserves continued investment.
- Keep inferred probability, operational priority, and verified truth visibly separate.

### What the Mechanism Must Not Become

- A path around authorization or data-governance controls.
- An opaque model whose decisions cannot be reconstructed.
- A scheduler that can spend resources without approved bounds.
- A verifier that presents confidence as truth.
- A self-training feedback loop that changes behavior without a new version and approval.

### Executive Success Test

An executive should be able to review any ranking window and understand:

1. Which approved sources contributed proposals.
2. Why the proposals were considered comparable.
3. Which evidence materially changed the order.
4. Which component authorized, reserved, scheduled, and verified the work.
5. Whether the ordering outperformed a simpler baseline under the same budget.

**Executive takeaway:** Function 8 is best understood as an accountable sequence of gates and judgments, not as a single scoring formula.


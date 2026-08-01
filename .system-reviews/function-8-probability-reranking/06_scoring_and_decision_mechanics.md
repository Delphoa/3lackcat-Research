# Section 6 — Scoring and Decision Mechanics

> **Executive purpose:** Explain what the ranker's values mean, how they should influence decisions, and what evidence is required before leadership can rely on them.

[Previous: Section 5 — Data and Persistence](05_data_mechanics_and_persistence.md) · [Review index](README.md) · [Next: Section 7 — MVP Boundary](07_mvp_boundary_and_critical_path.md)

Function 8 compares candidate proposals from sources that may use different scoring conventions and have different strengths. Its primary governance duty is to avoid turning unlike values into one authoritative-looking number without evidence.

The executive interpretation should preserve three separate concepts:

1. **Estimated hit likelihood:** The evidence-backed estimate that an eligible proposal is promising within a declared research context.
2. **Priority utility:** The operational value of evaluating that proposal next after considering novelty, coverage, cost, and uncertainty.
3. **Verified outcome:** The authoritative result produced later by the deterministic verifier.

Priority utility is not a probability, and neither ranking value is verification truth.

## 6.1 Score Inputs

| Input family | Executive interpretation | Required treatment |
|---|---|---|
| Source likelihood | How strongly the originating source favors the proposal | Calibrate by source and version before cross-source comparison |
| Semantic evidence | How well the proposal fits an interpretable pattern | Use as bounded supporting evidence with visible provenance |
| Context evidence | Compatibility with an approved target profile | Optional, scope-gated, bounded, disableable, and privacy-reviewed |
| Source quality | How reliable the source has been under approved evaluation | Use only from versioned held-out evidence |
| Novelty and coverage | Whether the proposal adds new work or repeats saturated areas | Exact duplication is a hard exclusion; broader overlap is advisory |
| Verification cost | The expected resource burden of evaluation | Adjust priority utility, not likelihood |
| Uncertainty | Missing inputs, stale calibration, or out-of-domain conditions | Reduce confidence or trigger a declared fallback |
| Governance | Scope, policy, source approval, and sensitivity decisions | Apply as hard controls, never weighted preferences |

## 6.2 Critical Scoring Rules

1. Raw values from different source types must not be compared directly.
2. A value must not be called a probability unless its meaning, evaluation domain, and calibration evidence are declared.
3. Estimated likelihood must remain separate from cost- and novelty-adjusted priority utility.
4. Authorization, policy, validity, and exact uniqueness must be resolved before ranking.
5. Multiple source attributions should be preserved without double-counting the same underlying evidence.
6. Missing or stale information must remain visible rather than being silently treated as neutral.
7. Ranking policy, calibration, evidence definitions, and tie-breaking behavior must be fixed and versioned for a replayable run.
8. Context influence must be bounded so it cannot erase general coverage or privacy safeguards.
9. A score may recommend order only; it cannot authorize work or establish truth.
10. The MVP should use the simplest transparent policy capable of testing the product hypothesis.

## 6.3 Decision Phases

| Phase | Executive question | Required outcome |
|---|---|---|
| Admission | May this proposal enter the process? | Eligible, blocked, duplicate, invalid, or quarantined decision with reason |
| Calibration | What comparable evidence can be asserted for this source? | Calibrated evidence or a clearly labeled unvalidated state |
| Fusion | What does the combined approved evidence support? | Estimated likelihood, confidence, and contribution summary |
| Utility adjustment | How should novelty, coverage, cost, and uncertainty affect priority? | Separate priority utility with clear tradeoffs |
| Ordering | What deterministic global order follows? | Stable rank and tie-break explanation |
| Reservation and handoff | Can the proposal be uniquely reserved for scheduler consideration? | Reservation reference and bounded recommendation |
| Evaluation | Did authoritative outcomes support the ranking hypothesis? | Controlled performance, calibration, replay, and failure evidence |

## 6.4 Feedback Rule Examples

- A confirmed exact duplicate is excluded regardless of source score.
- Unapproved contextual evidence is removed; a proposal that depends on prohibited data is blocked.
- A source without valid calibration may enter a separately labeled fallback band but cannot support calibrated-probability claims.
- A high-likelihood proposal may receive lower priority when its expected verification cost is materially higher.
- A less-saturated family may receive a bounded novelty benefit, but novelty should not substitute for weak likelihood evidence without validation.
- Verifier outcomes update evaluation and attribution metrics during the MVP; they do not silently change active ranking behavior.
- Any later change requires a new version, stated rationale, bounded scope, replay evidence, and approval.

## 6.5 Performance Measurement

Leadership should evaluate Function 8 against fixed, replayable baselines under equal approved budgets. At minimum, the comparison should include the best approved single source and a fixed multi-source sequence.

### Decision Value

- Verified outcome yield or coverage at a fixed candidate, time, or resource budget.
- Time to first verified result.
- Improvement over fixed sequencing and the best individual source.
- Outcome rate across rank bands.

### Statistical Integrity

- Calibration quality by declared score band.
- Source-overlap and correlated-evidence analysis.
- Context-enabled versus context-disabled comparison.
- Explicit treatment of stale, missing, and out-of-domain evidence.

### Operational Quality

- Duplicate suppression and family saturation.
- Ranking latency, throughput, queue pressure, and resource overhead.
- Deterministic replay and ordering stability.

### Accountability and Safety

- Complete source provenance and decision explanations.
- Ability to reconstruct why one proposal ranked above another.
- Versioned linkage from ranking to scheduler and verifier outcomes.
- Zero score-based bypass of scope, policy, or exact uniqueness.
- Zero candidate plaintext in ranking metadata and logs.
- Zero influence from unapproved context.

### Executive Proof Standard

No universal gain should be promised. Advancement requires repeatable evidence that Function 8 improves at least one declared outcome—such as fixed-budget value, duplicate suppression, traceability, or decision clarity—without weakening authorization, privacy, replay, or authority separation.

**Executive takeaway:** The score is useful only when its meaning is honest, its evidence is comparable, and its organizational influence is limited to the authority it was designed to hold.


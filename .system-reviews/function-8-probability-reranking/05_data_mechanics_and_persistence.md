# Section 5 — Data Mechanics and Persistence

> **Executive purpose:** Define the information, evidence, privacy, and decision-history controls required to make Function 8 accountable.

[Previous: Section 4 — How It Should Operate](04_how_probability_reranking_should_operate.md) · [Review index](README.md) · [Next: Section 6 — Scoring and Decisions](06_scoring_and_decision_mechanics.md)

Function 8 can influence costly and sensitive evaluation work. Its decisions are trustworthy only when the organization can reconstruct what evidence was used, which controls were applied, which version produced the recommendation, and which component retained authority.

The data model should therefore optimize for accountability rather than accumulation. Ranking records should preserve provenance, confidence, decisions, and versions while leaving candidate plaintext in the restricted path required for deterministic verification.

## 5.1 Core Entities

| Information asset | Executive purpose | Required control |
|---|---|---|
| Candidate Event | Preserves the original proposal and its provenance | Immutable, bound to an approved run and source version, and refers to rather than reproduces sensitive payloads |
| Calibration Profile | Defines how a source-specific score may be interpreted | States the approved domain, evidence quality, version, and validity status |
| Ranking Evidence Record | Preserves the evidence considered in one decision | Separates observed, inferred, missing, and invalid information and identifies every contributing version |
| Ranked Candidate Record | Records the ranker's recommendation for one eligible proposal | Keeps estimated likelihood separate from priority utility and includes confidence and explanation |
| Ranked Batch Manifest | Creates the controlled scheduler handoff | Preserves order, scope, uniqueness reservations, configuration identity, and time; does not authorize dispatch |
| Ranking Audit Event | Provides the decision history | Records admissions, exclusions, scores, reranks, and batch decisions without plaintext |
| Ranking Evaluation Record | Holds the evidence used to judge value | Identifies baselines, budgets, outcomes, calibration results, overlap, and replay status |

Before sensitive data is processed, leadership should require clear ownership, access, retention, deletion, and incident-response rules for every information asset.

## 5.2 Evidence Classes

The ranker must keep facts, observations, estimates, and unknowns visibly different.

| Evidence class | Executive meaning | Governance treatment |
|---|---|---|
| Verified | Issued by the responsible authority, such as a valid scope decision, exact uniqueness state, or verifier outcome | May be treated as fact only within the authority's declared scope |
| Observed | Recorded directly from an approved source or system event | Preserve origin and version; do not overstate what it proves |
| Inferred | Estimated by calibration or ranking, including likelihood, context fit, novelty, or utility | Label as advisory with confidence and domain limitations |
| Unknown | Missing, stale, out-of-domain, or pending | Keep explicit and apply conservative handling; never silently treat as neutral |
| Invalid | Malformed, mismatched, or logically inconsistent | Exclude from influence and record the reason |
| Quarantined | Retained for review but prohibited from influencing decisions | Release requires an explicit review decision |
| Superseded | Replaced by a later versioned decision | Preserve for history, comparison, and replay |

The governing principle is simple: inferred likelihood is not verified truth, and missing evidence is not evidence of safety or quality.

## 5.3 State Transition Logic

The controlled lifecycle is:

```text
received
  -> invalid / quarantined / blocked / duplicate
  -> eligible
  -> calibrated
  -> scored
  -> ranked
  -> selected and reserved
  -> scheduler-controlled dispatch
  -> verifier-confirmed outcome
```

### Decision Ownership

| Transition or state | Responsible component |
|---|---|
| Scope, policy, and source eligibility | Authorization and policy authorities |
| Exact uniqueness and reservation | Deduplication and Coverage Ledger |
| Calibration, scoring, and ordering recommendation | Function 8 |
| Budget allocation and dispatch | Conservative Scheduler |
| Positive or negative outcome | Deterministic Verifier |
| Approved interpretation and performance analysis | Reporting and evaluation functions |

No component should silently assume another component's authority. A high rank does not authorize dispatch, and a later verified outcome must not be written into an earlier ranking record as though it were known at decision time.

## 5.4 Record Mechanics

Ranking decisions should be preserved as append-only snapshots. A rerank creates a new decision linked to the earlier decision, states why it changed, and records the evidence or versions that changed. The earlier decision remains available for audit.

A scheduler handoff should preserve enough context to reconstruct the decision, including:

- the approved run and target scope;
- ranker and ranking-policy versions;
- calibration and evidence-definition versions;
- applicable policy and approved context versions;
- uniqueness and reservation references;
- the deterministic ordering rule;
- the ordered proposal references and creation time.

### Executive Governance Requirements

- Ordinary ranking metadata, explanations, and logs remain plaintext-free.
- Restricted payload references resolve only through approved access controls.
- Retention periods match the sensitivity and purpose of each record class.
- Material corrections create new records rather than overwriting history.
- Reports identify which values were known at decision time and which were observed later.
- Independent reviewers can reproduce representative ranking and batch decisions from preserved records.

### Proof Standard

An independent reviewer should be able to explain why one proposal ranked above another, confirm that no hard control was overridden, trace each material input to an approved source and version, and reproduce the recommendation without gaining unnecessary access to candidate plaintext.

**Executive takeaway:** The information architecture is not administrative overhead. It is what turns a ranking output from an opaque score into a governable organizational decision.


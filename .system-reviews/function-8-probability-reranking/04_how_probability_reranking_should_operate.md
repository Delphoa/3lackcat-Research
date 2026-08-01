# Section 4 — How Probability Re-Ranking Should Operate

> **Executive purpose:** Define the expected behavior, control intent, and success evidence for each stage of Function 8 without prescribing implementation details.

[Previous: Section 3 — Mechanistic Review](03_mechanistic_review_at_a_glance.md) · [Review index](README.md) · [Next: Section 5 — Data and Persistence](05_data_mechanics_and_persistence.md)

Function 8 should operate through seven explicit stages. Each stage has a distinct executive purpose and should leave an auditable result. Combining the stages into an opaque decision would make governance, performance review, and error correction unnecessarily difficult.

## 4.1 Admission and Eligibility

### Executive Description

Admission is the non-negotiable front door. It confirms that a candidate proposal belongs to the approved run, came from an approved source, carries sufficient provenance, and is permitted under current policy.

### Expected Behavior

- Reject or quarantine proposals that are malformed, out of scope, unapproved, expired, or inconsistent with the run.
- Exclude confirmed exact duplicates before they can consume ranking or verification attention.
- Record a clear reason when a proposal is blocked.
- Stop safely if authorization or authoritative uniqueness information is unavailable.

### Material Risk

If eligibility is treated as a score adjustment, a sufficiently high model score could outrank a policy failure. That would turn an advisory ranker into an unauthorized control bypass.

### Success Evidence

No excluded candidate reaches the ranking stage, and every rejection can be traced to an authoritative policy, validity, or uniqueness decision.

## 4.2 Source-Specific Calibration

### Executive Description

Different candidate sources express confidence in different ways. Calibration is the process that makes those signals responsibly comparable. Without it, the global order may simply favor whichever source uses larger or more optimistic numbers.

### Expected Behavior

- Use a declared calibration basis for each source and version.
- Show when evidence is stale, weak, missing, or outside its evaluated domain.
- Provide a conservative fallback when comparability is not established.
- Withhold probability language when the evidence supports only a relative score or band.

### Material Risk

Poor or leaked calibration can create impressive-looking but misleading performance and direct limited resources toward the wrong source.

### Success Evidence

At least two approved source types can be compared under documented calibration states, and leadership can see which results are calibrated versus provisional.

## 4.3 Evidence Assembly

### Executive Description

Evidence assembly creates the decision record used to rank an eligible proposal. The record should be sufficient to explain the decision while avoiding unnecessary sensitive content.

### Expected Behavior

- Combine source confidence, semantic evidence, approved context, novelty, coverage, cost, and uncertainty.
- Identify whether each input is observed, inferred, missing, or authoritative.
- Limit the influence of context so narrow or sensitive signals cannot dominate general evidence.
- Use privacy-preserving references rather than copying candidate plaintext into routine records.

### Material Risk

An undocumented or overly rich evidence record can leak sensitive information, double-count correlated signals, or make the final decision impossible to audit.

### Success Evidence

Every material contribution to a score can be traced to an approved source and version without exposing restricted content.

## 4.4 Mixture Scoring and Re-Ranking

### Executive Description

This stage converts the assembled evidence into two related but different judgments:

1. **Estimated hit likelihood:** How strong is the approved evidence that this proposal may produce a verified result?
2. **Priority utility:** Given likelihood, novelty, coverage, cost, and uncertainty, how valuable is it to evaluate the proposal now?

Keeping these judgments separate is central to honest reporting. A candidate may have strong likelihood but lower immediate utility because it is expensive or adds little new coverage. Conversely, novelty may increase priority without increasing probability.

### Expected Behavior

- Use a transparent and versioned first model.
- Preserve the major positive and negative contributions to each decision.
- Treat authorization and exact uniqueness as gates outside the score.
- Avoid describing operational utility as statistical probability.
- Keep the same behavior for the duration of a replayable run.

### Material Risk

An opaque or constantly changing mixture can produce false confidence, hide bias, and make performance claims impossible to validate.

### Success Evidence

The same evidence and approved configuration produce the same likelihood, utility, and relative order, and the result can be explained in plain language.

## 4.5 Deterministic Ordering and Batch Construction

### Executive Description

Ordering turns individual recommendations into a stable queue. Batch construction creates a bounded handoff that the scheduler can assess without reinterpreting the ranker's evidence.

### Expected Behavior

- Use a stable rule when candidates have equal or nearly equal priority.
- Preserve all relevant source attribution when several sources propose the same candidate.
- Prevent one source or evidence family from dominating because of scaling artifacts.
- Reserve selected exact candidates before handoff so concurrent work cannot duplicate them.
- Preserve the versions and decision context associated with the batch.

### Material Risk

Non-deterministic ordering, duplicate races, or unexplained source dominance can waste resources and undermine evaluation credibility.

### Success Evidence

A ranking window can be reconstructed exactly, contains only eligible and uniquely reserved proposals, and carries enough context for the scheduler and later audit.

## 4.6 Explanation and Audit Emission

### Executive Description

Explanation is the accountability product of Function 8. It should allow leadership, researchers, and reviewers to understand why one proposal ranked above another without revealing sensitive content.

### Expected Behavior

- Record major contributing factors, confidence state, exclusions, missing evidence, and version references.
- Distinguish inferred priority from verified outcome.
- Preserve earlier decisions when a later version reranks the same proposal.
- Use privacy-preserving identifiers and controlled references.

### Material Risk

If the explanation is incomplete, the organization cannot validate value, investigate errors, or demonstrate that policy and privacy boundaries held.

### Success Evidence

An independent reviewer can reconstruct the decision and its governing versions from the audit record without accessing candidate plaintext.

## 4.7 Feedback and Re-Ranking Cycles

### Executive Description

Feedback determines how observed outcomes influence later decisions. This is valuable but also the point where a transparent ranker can become an unstable, self-reinforcing system.

### Expected MVP Behavior

- Use verifier outcomes and source-yield observations for offline evaluation and calibration review.
- Require a new, approved version before weights or behavior change.
- Keep recovered or sensitive content out of future training unless its use is separately approved.
- Preserve the prior decision so changes can be compared and replayed.

### Deferred Behavior

Live re-ranking, automated weight changes, and cross-run learning should remain post-MVP until the conservative path has stable evidence, bounded correction rules, and explicit human approval.

### Material Risk

Early noisy outcomes can cause the system to overcommit to one source, suppress useful diversity, or amplify data leakage and bias.

### Success Evidence

Feedback improves a later approved version under controlled testing without rewriting history, bypassing governance, or degrading baseline performance.

## Executive Control Summary

| Stage | Executive control question |
|---|---|
| Admission | Can any score override permission or exact uniqueness? |
| Calibration | Are source signals genuinely comparable, and where are they not? |
| Evidence assembly | Is every material input approved, traceable, and privacy-minimized? |
| Scoring | Are likelihood and operational priority clearly separated? |
| Ordering | Can the same decision be reproduced, including ties and reservations? |
| Explanation | Can a reviewer understand the decision without seeing sensitive content? |
| Feedback | Does behavior change only through bounded, versioned, approved updates? |

**Executive takeaway:** Function 8 should behave as a chain of accountable decisions. No single score should be able to hide weak evidence, override a hard control, or acquire authority it was not designed to hold.


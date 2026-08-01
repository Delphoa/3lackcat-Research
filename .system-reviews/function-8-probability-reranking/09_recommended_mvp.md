# Section 9 — Recommended MVP

> **Executive purpose:** Define what should be funded now, what should remain deferred, and what evidence constitutes an accepted Function 8 MVP.

[Previous: Section 8 — Risk Review](08_risk_review.md) · [Review index](README.md) · [Next: Section 10 — Final Recommendation](10_final_recommendation.md)

The recommended MVP is a bounded decision-support capability, not an autonomous optimization system. Its role is to demonstrate that proposals from at least two approved sources can be combined into one dependable order without weakening authorization, privacy, provenance, uniqueness, scheduling, or verification controls.

The executive objective is to answer three questions:

1. Can heterogeneous sources be compared responsibly enough to support one useful queue?
2. Can every material decision be explained and replayed?
3. Does the ranked queue create measurable value over simpler sequencing under the same budget?

The MVP should use the least complex model capable of producing credible evidence.

## 9.1 Build Now

| Capability | Executive description | Why it belongs now | Evidence expected |
|---|---|---|---|
| Strict admission control | Establish one governed entry point for eligible, attributable proposals | Ranking quality is irrelevant if invalid or unauthorized data can enter | Blocked and malformed proposals have zero influence |
| Exact uniqueness and reservation | Prevent repeated or concurrent selection of the same candidate | Duplicate work wastes budget and corrupts evaluation | Duplicate and concurrency tests show no repeated batch entry |
| Source-specific calibration | Give unlike source signals a declared comparable interpretation | Raw scores do not share a common meaning | At least two source types compared with visible calibration states |
| Transparent ranking policy | Combine approved evidence using a fixed and understandable policy | The project must know whether gains come from evidence or arbitrary weighting | Versioned policy, contribution explanation, and reproducible examples |
| Separate likelihood and utility | Distinguish evidence of promise from operational priority | Combining them would overstate certainty and hide tradeoffs | Records and reports visibly separate both values and verified outcome |
| Stable bounded recommendations | Create repeatable candidate windows for scheduler consideration | Stable output is necessary for fair evaluation and accountability | Same evidence produces the same order and batch membership |
| Privacy-preserving explanations | Explain decisions without creating a secondary sensitive-data store | Accountability must not increase disclosure risk | Complete explanations and no plaintext in routine records |
| Replay and baseline evaluation | Determine whether the capability adds value over simpler approaches | Progress should rest on evidence, not model sophistication | Equal-budget comparison, replay, calibration, and failure reports |

These capabilities form three delivery layers:

- **Control foundation:** Admission, provenance, policy binding, privacy-preserving identity, and uniqueness.
- **Ranking value:** Comparable evidence, transparent fusion, separate likelihood and utility, and stable recommendations.
- **Assurance evidence:** Explanation, replay, baseline comparison, calibration review, failure tests, and privacy validation.

The control foundation is a prerequisite, not a later hardening phase.

## 9.2 Defer

| Deferred capability | Executive reason | Evidence required before reconsideration |
|---|---|---|
| Learned or opaque ensemble ranking | It would make attribution and failure analysis harder before a simple model is proven insufficient | Repeatable MVP evidence showing a material ceiling and a credible expected improvement |
| Runtime self-modifying weights | Live adaptation weakens stability, approval, and fair comparison | Governed update policy, bounded changes, replay, rollback, and clear ownership |
| Advanced feedback and cross-run priors | Historical outcomes may introduce leakage, hidden bias, or unsafe data reuse | Approved data-use boundaries, leakage analysis, retention rules, and independent validation |
| Fine-grained pattern-specific calibration | Narrow segments may appear precise without enough evidence | Sufficient representative samples and stable held-out improvement |
| Advanced diversity optimization | Complex policies may suppress strong evidence or hide score incompatibility | Proof that simple declared limits are inadequate |
| Distributed ranking state and global ledgers | Distribution increases privacy, consistency, and governance obligations | Proven scale need and approved multi-run ownership and incident model |

Recovered plaintext must not become a learning asset without a separate approval covering purpose, dataset, access, retention, and research boundary.

Deferred capabilities should re-enter planning only through explicit evidence and a recorded decision.

## 9.3 MVP Acceptance Criteria

| # | Required outcome | Executive interpretation | Minimum proof |
|---:|---|---|---|
| 1 | At least two approved sources receive one deterministic global order | Function 8 demonstrates cross-source value | Controlled input and repeat run produce the same order |
| 2 | Every ranked proposal has valid scope, policy, and provenance | Leadership can explain why the proposal was eligible | Complete sample audit with no unattributed records |
| 3 | Confirmed exact duplicates do not appear twice | The queue protects finite resources and credible metrics | Duplicate and competing-selection tests |
| 4 | Likelihood, utility, confidence, and verified outcome remain distinct | Statistical evidence and operational preference cannot be confused | Reviewable records and reporting definitions |
| 5 | Every material ranking can be explained | Reviewers can understand why one proposal outranked another | Representative explanations without plaintext access |
| 6 | Identical evidence and versions reproduce identical results | Decisions can be investigated and defended | Successful replay report |
| 7 | Missing or invalid calibration remains visible | Lack of evidence is not concealed by a number | Negative tests and conservative fallback examples |
| 8 | The ranker cannot dispatch or override budgets | Function 8 remains advisory | Authority review and denied out-of-bound actions |
| 9 | Ranking records contain no candidate plaintext | Explainability does not create a new sensitive store | Redaction and log-inspection evidence |
| 10 | Evaluation compares with fixed sequencing and the best source | Investment decisions use strong, equal-budget evidence | Reproducible report covering benefits, uncertainty, and limitations |

Acceptance should be all-or-nothing for ranking influence. Partial completion may support continued research, but it should not be described as an accepted MVP when a governance, privacy, replay, or authority criterion remains unmet.

### Executive Decision

Approve this scope for controlled research and evaluation only after the control foundation is established. Do not approve deferred capabilities, operational autonomy, or performance claims as part of the initial build.

**Executive takeaway:** A modest result produced by trustworthy evaluation is more valuable than an apparently strong result that cannot be explained, replayed, or separated from leakage and duplicate effects.


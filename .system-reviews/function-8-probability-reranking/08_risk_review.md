# Section 8 — Risk Review

> **Executive purpose:** Identify the failures that could invalidate Function 8 and define the conditions for controlled use or immediate stop.

[Previous: Section 7 — MVP Boundary](07_mvp_boundary_and_critical_path.md) · [Review index](README.md) · [Next: Section 9 — Recommended MVP](09_recommended_mvp.md)

Function 8 influences which proposals receive scarce and sensitive verification resources. Its principal risks are broader than ranking accuracy. They include unauthorized influence, false confidence, wasted resources, irreproducible decisions, corrupted performance claims, and disclosure of sensitive information.

No performance result compensates for a failed authorization, privacy, exact-duplicate, or evidence-integrity control.

## 8.1 Highest-Risk Failure Modes and Controls

| Material risk | Executive consequence | Mandatory control | Proof required |
|---|---|---|---|
| Incompatible source scores | The global order becomes arbitrary while appearing objective | Source- and version-specific calibration with a visible unvalidated fallback | Held-out comparison for every admitted source class |
| Calibration leakage or drift | Performance appears stronger than it is and misdirects investment | Leakage-resistant evaluation, version pinning, validity windows, and drift review | Calibration report, split audit, and out-of-domain tests |
| Governance treated as a score penalty | A high score can bypass authorization or policy | Hard admission gates before ranking | Scope, source, context, and policy bypass tests |
| Duplicate races | Repeated work wastes resources and corrupts source-yield evidence | Pre-score lookup and atomic reservation before handoff | Concurrency and replay tests showing no duplicate dispatch |
| Context overweighting | Coverage narrows while privacy exposure increases | Explicit approval, contribution limits, disablement, and context-ablation tests | Context-on/context-off comparison and zero unapproved influence |
| Correlated evidence counted repeatedly | The ranker reports false confidence | Source-family awareness, overlap analysis, and bounded corroboration | Attribution and ablation evidence |
| Missing evidence treated as neutral | Silent bias alters decisions without visibility | Explicit unknown states and conservative fallback | Missing-evidence tests and complete explanations |
| Non-deterministic ties or live mutation | Decisions cannot be reproduced or defended | Stable tie-breaking, immutable snapshots, and pinned versions | Identical replay from identical evidence |
| Sensitive data in records | Candidate or contextual information is disclosed | Privacy-preserving references, redaction, least privilege, and export controls | Automated and manual leakage review |
| Ranker/scheduler authority confusion | Recommendation becomes uncontrolled spending or dispatch | Stable handoff contract and explicit ownership | Proof that the ranker cannot dispatch or override budgets |
| Feedback-loop instability | Early outcomes reinforce poor sources and suppress useful alternatives | Offline MVP feedback; bounded and approved updates later | Fixed behavior during the run and governed version changes |

Leadership should treat failures in authorization, exact reservation, sensitive-data handling, or deterministic replay as release blockers rather than ordinary defects.

## 8.2 Go/No-Go Criteria

### Go for Controlled MVP Influence Only If

- Scope, policy, source approval, and exact uniqueness cannot be overridden by scores.
- Ranking decisions are deterministic, versioned, explainable, and replayable.
- At least two approved source types can be compared under declared calibration states.
- Unvalidated or stale evidence is visibly separated from calibrated evidence.
- Likelihood remains distinct from novelty-, cost-, and uncertainty-adjusted utility.
- Ranking metadata, explanations, metrics, and logs contain no candidate plaintext.
- Duplicate reservation is atomic.
- Equal-budget baselines, failure tests, and replay evidence are available.
- Ranker, ledger, scheduler, verifier, and human authority boundaries are enforced.
- Limitations and applicable evaluation domains are visible to decision-makers.

### No-Go for Automated High-Cost or Efficacy-Critical Use If

- Calibration is absent, stale, out of domain, or trained with leaked evaluation targets.
- Explanations cannot reconstruct the ordering decision.
- Duplicate reservation is unreliable or the authoritative ledger is unavailable.
- Contextual evidence is unapproved, unbounded, or cannot be disabled.
- Missing evidence is silently imputed.
- Live feedback changes behavior without a new version and approval.
- The ranker can dispatch work or bypass scheduler budgets.
- Replay cannot reproduce the ranked batch.
- Sensitive values appear in ordinary ranking records.
- Performance claims rely on source-local scores, uncontrolled runs, or weak baselines.

### Executive Decision Standard

If any mandatory governance control is absent, Function 8 should remain confined to offline research and evaluation. Broader influence requires controlled evidence that it adds measurable decision value under equal budgets while maintaining zero scope bypass, zero plaintext leakage, deterministic replay, and clear separation of authority.

Performance claims and automated high-cost use require separate human approval even after the controlled MVP passes.

**Executive takeaway:** The acceptable risk posture is conservative by design. Function 8 earns influence through evidence; it does not receive influence merely because it can produce a ranking.


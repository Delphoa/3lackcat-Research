# Section 11 — Source Inventory and Traceability

> **Executive purpose:** Identify what supports this review, distinguish established design direction from new recommendations, and keep unresolved decisions visible.

[Previous: Section 10 — Final Recommendation](10_final_recommendation.md) · [Review index](README.md)

This section records the evidence base behind the Function 8 review. The collection combines source-supported architecture with proposed clarifications and unresolved research choices. It does not create new implementation evidence or certify the underlying system.

## Source Inventory

| Source | Type | Apparent version/date | Role in the review | Authority and limitation |
|---|---|---|---|---|
| `3lackcat_probability_ranked_password_recovery_orchestration_layer.md` | Research/design | Current workspace artifact | Ranker purpose, input families, conceptual score, outputs, value, feasibility, and metrics | Primary research source; exact formula and weights remain illustrative |
| `3lackcat_system_design_document.md` | System design | Draft v0.1 / 2026-07-09 | P1 role, dependencies, workflows, interfaces, acceptance, validation, and risks | Primary architecture authority among reviewed files; describes intent, not runtime proof |
| `3lackcat_functions_1_7_design_outline.md` | Upstream function design | Current workspace artifact | Candidate, semantic, PCFG, learned-generator, decoder, and calibration inputs | Strong upstream authority; does not settle Function 8's full design |
| `3lackcat_agent_implementation_document.md` | Implementation planning | Current workspace artifact | Global decision-point framing, unresolved risk, sequencing, and acceptance gates | Planning authority only; not evidence of completed implementation |
| `3lackcat_functions_8_14_design_outline.md` | Referenced but unavailable | Unknown | Expected detailed Function 8-14 source cited by the system design | Missing source; no claim here relies on unseen contents |
| `3lackcat_function_8_probability_reranking_executive_outline.md` | Consolidated executive review | Draft v0.1 / 2026-08-01 | Immediate editorial source for this split collection | Parent review; not a substitute for governing design sources |

## Source Authority

For executive decisions, the current authority order is:

1. Explicit scope, policy, privacy, and verification controls govern over ranking preferences.
2. The system design governs Function 8's role and interfaces in 3lackcat.
3. Upstream function designs govern the meaning and provenance of incoming proposals.
4. The implementation-planning document governs proposed sequencing and proof obligations.
5. The probability-ranking research document motivates the concept and metrics but does not settle the final method.
6. This executive collection clarifies decisions and boundaries; it does not silently override the governing sources.

Material conflicts should be recorded and resolved through an explicit project decision.

## Traceability Labels

### Source-Supported

- Function 8 is a P1 ranking component in the broader orchestration layer.
- It receives evidence from multiple candidate-source families.
- Cross-source comparison is a central purpose.
- Ranked records and batch outputs should preserve explanation and provenance.
- Heterogeneous raw values require calibration before comparison.
- Ranking remains separate from scheduling and deterministic verification.
- Fixed-budget evaluation is required before performance claims.
- Calibration and decision integrity remain material risks.

Source-supported means the design record provides a basis for the position. It does not mean the capability is implemented or empirically proved.

### Proposed Clarification

The review recommends keeping two outputs explicitly separate:

- **Estimated hit likelihood:** The defensible likelihood evidence within the declared evaluation context.
- **Priority utility:** The operational order after novelty, coverage, cost, and uncertainty are considered.

This prevents an operational tradeoff from being presented as statistical certainty.

### Proposed Resolution

The review resolves the apparent ranker/dedupe ordering conflict through two interactions:

1. Before scoring, the ledger determines exact ineligibility and supplies broader coverage evidence.
2. Before scheduler handoff, selected candidates are reserved so concurrent work cannot emit them again.

Broader similarity remains an advisory ranking signal rather than an exact exclusion. This remains a recommendation until confirmed in the governing interface design and validated through competing-selection tests.

### Proposed MVP Constraint

Verifier outcomes should update attributed metrics and offline evaluation during the MVP. They should not silently change ranking behavior during a run. Future adaptation requires a declared cadence, new version, preserved prior state, bounded influence, replay, rollback, and explicit approval.

### Unresolved Decisions

| Question | Why leadership should care | Required next evidence or decision |
|---|---|---|
| What exactly does likelihood mean? | Probability language may overstate what the system knows | Approved definition, evaluation population, and reporting language |
| Which evidence-fusion method should be used? | The choice affects clarity, stability, and correlated evidence | Compare simple interpretable alternatives on held-out data |
| What weights and contribution limits apply? | Arbitrary weights can distort coverage and confidence | Versioned rationale, sensitivity analysis, and approval limits |
| What calibration method and tolerance are acceptable? | Calibration determines whether probability language is defensible | Declared measures, held-out results, and drift limits |
| How much influence may approved context have? | Excessive context can narrow coverage and increase privacy risk | Contribution caps, ablation evidence, and governance approval |
| What diversity policy is required? | One source may dominate because of scale rather than evidence | Saturation analysis and simple-policy comparison |
| What batch size and reranking cadence are appropriate? | These affect responsiveness, stability, overhead, and comparability | Controlled operational experiments and scheduler constraints |
| What thresholds govern promotion? | Without them, the prototype may expand on anecdotal evidence | Approved scorecard covering value, calibration, privacy, replay, and authority |
| What is the status of the Functions 8-14 outline? | The missing source may contain constraints or indicate a stale reference | Locate, replace, or formally deprecate it |

## Evidence Sufficiency Summary

The current sources are sufficient for a bounded executive rationale, proposed authority model, MVP scope, risk plan, and conditional approval for controlled research.

They are not sufficient for a final scoring method, validated calibration claims, a declared performance gain, adaptive runtime behavior, production readiness, operational autonomy, or conclusions based on the missing Functions 8-14 document.

## Traceability Maintenance

When new research, design, implementation, or evaluation evidence becomes available, this section should record:

- artifact name and version;
- its decision or evidence role;
- whether it confirms, narrows, contradicts, or supersedes an existing position;
- affected section files;
- approval status of any changed recommendation.

Implementation evidence must remain distinct from design intent. Performance evidence should always identify the baseline, budget, dataset authority, calibration state, uncertainty, and replay reference needed for interpretation.

**Executive takeaway:** The current evidence is strong enough to define a controlled MVP decision, but not strong enough to settle the scoring method or support production and efficacy claims.


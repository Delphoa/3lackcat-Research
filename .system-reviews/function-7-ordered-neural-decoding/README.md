# Function 7 — Ordered Neural Decoding

> **Status:** Placeholder for the future Function 7 executive and system review. The function remains in the design and research phase.

## Executive Introduction

Function 7 converts outputs from an approved learned candidate model into a deterministic, probability-ranked stream of candidate proposals. Its purpose is to ensure that higher-value model outputs can be evaluated in a stable, explainable, and reproducible order rather than through uncontrolled random sampling.

Function 7 is the bridge between:

- **Function 6 — Learned Candidate Generator**, which provides model probabilities and candidate-generation capability; and
- **Function 8 — Candidate Ranker and Mixture Model**, which compares neural candidates with PCFG, normalization, rule-based, and other approved candidate sources.

## Intended Role

At a high level, Function 7 should:

- explore model outputs using bounded and reproducible decoding;
- preserve probability, rank, model version, and provenance;
- apply authorization, policy, and candidate-validity constraints;
- coordinate with deduplication and coverage controls;
- emit bounded candidate events and batches for Function 8;
- support checkpointing and deterministic replay for long-running research.

## Authority Boundary

Function 7 is an advisory candidate-source component.

It does **not**:

- authorize targets, datasets, or contextual information;
- allocate the overall verification budget;
- dispatch work directly to the deterministic verifier;
- establish whether a candidate is correct;
- override policy, scope, deduplication, or retention controls.

The scope gate determines what is permitted. Function 8 determines global cross-source priority. The scheduler controls bounded dispatch. The deterministic verifier remains the source of result truth.

## Planned Review Areas

The future Function 7 review is expected to cover:

1. Executive value and product fit.
2. Relationship to Functions 6 and 8.
3. Ordered-decoding lifecycle and decision boundaries.
4. Candidate-event, provenance, and replay requirements.
5. Policy filtering, deduplication, and batching.
6. Performance, calibration, and reproducibility evidence.
7. MVP boundary, risks, acceptance criteria, and go/no-go conditions.
8. Source inventory and unresolved design decisions.

## Current Evidence Posture

This README introduces the intended function; it does not claim that Function 7 has been implemented, benchmarked, calibrated, independently reviewed, or proven to improve recovery performance. Any efficacy claim must be supported by approved, held-out, fixed-budget evaluation against strong baselines.

No ranking or decoding score should be represented as verification truth.

# Function 8 Probability Re-Ranking Executive Review

> **Purpose:** Provide the initial executive review package for 3lackcat Function 8, the Candidate Ranker and Mixture Model.

This folder contains the first published portion of the section-level Function 8 review. It translates the design into executive language: strategic value, decision rights, material risks, proof requirements, and the choices leadership must make.

## Executive Position

Function 8 should be treated as a **P1 advisory decision component**. It compares candidate proposals from multiple approved sources and recommends a single, explainable order for evaluation. It does not authorize work, allocate final budgets, dispatch verification jobs, or decide whether a candidate is correct.

The recommended MVP is conditional: proceed only with hard authorization controls, comparable and versioned score calibration, deterministic replay, privacy-preserving explanations, and controlled baseline evaluation.

## Published Documents

| File | Executive focus |
|---|---|
| [Document Control](00_document_control.md) | Scope, source authority, evidence posture, and limitations |
| [Section 1 — Executive Summary](01_executive_summary.md) | Strategic case, value proposition, boundaries, and build classification |
| [Section 2 — Role in 3lackcat](02_system_role_in_3lackcat.md) | Function 8's position between candidate generation, governance, scheduling, and verification |

## Current Publication Scope

This initial package includes document control and Sections 1 and 2 only. Sections 3 through 11 remain outside this repository folder until separately published.

The broader review covers the operating model, data governance, scoring interpretation, MVP boundary, risk, recommendation, and source traceability. Their absence here should not be interpreted as approval of unresolved implementation or governance choices.

## Interpretation Rules

- **Verified** means supported by the system's designated authority, such as a valid scope decision, ledger state, or deterministic verification result.
- **Observed** means recorded directly from an approved source or system event.
- **Inferred** means estimated by calibration or ranking and therefore advisory.
- **Proposed** means recommended by the review but not yet approved or implemented.
- **Unresolved** means leadership, research, or security review is still required.

No Function 8 score should be presented as verification truth. No private or sensitive candidate content should be copied into executive reports, ranking explanations, or routine logs.

## Source Posture

These files are design and decision-support artifacts. They do not establish that Function 8 has been implemented, calibrated, independently reviewed, or proven to improve performance.

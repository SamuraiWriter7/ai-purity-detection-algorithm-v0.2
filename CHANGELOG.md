# Changelog

All notable changes to this repository will be documented in this file.

This project follows a draft-oriented versioning model while the specification remains experimental.

---

## [Unreleased]

### Planned

- Add additional v0.2 examples for:
  - high-confidence natural-source assessment
  - hybrid structural-originality assessment
  - disputed-origin assessment
  - declaration-conflict assessment
- Add a dedicated review-routing model document.
- Add relationship documents for:
  - CollapseMonitor
  - Royalty Readiness
  - Trace Protocol
  - Structure Fingerprint
- Extend the schema to support:
  - detailed scoring model output
  - warning-flag detail objects
  - recursive synthetic risk output
  - review-routing metadata

### Notes

The next stage should focus on making the v0.2 model more operational without turning purity scoring into automatic legal or financial judgment.

---

## [0.2.0] - 2026-05-25

### Added

- Added initial `README.md` for **AI Purity Detection Algorithm v0.2**.
- Added `docs/v0.2-roadmap.md` to define the proposed direction for the v0.2 specification.
- Added `docs/scoring-weighting-model.md` to define a draft signal-weighting and confidence-adjusted scoring model.
- Added `docs/warning-flag-severity-model.md` to define warning-flag severity levels, review routing, and downstream impact handling.
- Added `schemas/purity-assessment.schema.json` for validating purity assessment examples.
- Added `examples/purity-assessment.sample.yaml` as a standard purity assessment example.
- Added `examples/purity-assessment.low-confidence.sample.yaml` to demonstrate weak provenance, unclear origin, low confidence, review-required routing, and blocked royalty-readiness status.
- Added `examples/purity-assessment.recursive-synthetic-risk.sample.yaml` to demonstrate high recursive synthetic risk, weak primary-source provenance, high AI-pattern similarity, blocked training use, and blocked royalty-readiness status.
- Added `.github/workflows/validate-examples.yml` to validate YAML examples against the JSON Schema.
- Added `LICENSE`.

### Defined

- Defined `origin_purity_score` as a normalized estimate of source-origin composition.
- Defined `ai_generated_ratio` as a separate estimate of AI-generated or AI-assisted content ratio.
- Defined `warning_flags` as routing and review-support signals.
- Defined a draft signal-weighting model using:
  - `provenance_evidence_score`
  - `author_declaration_score`
  - `structural_originality_score`
  - `revision_lineage_score`
  - `citation_transparency_score`
  - `ai_pattern_risk_score`
  - `structure_fingerprint_distinctiveness_score`
  - `recursive_synthetic_risk_score`
  - `signal_confidence_quality_score`
- Defined warning severity levels:
  - `info`
  - `warning`
  - `review_required`
  - `blocking`
- Defined review-routing modes:
  - `none`
  - `recommended`
  - `required`
  - `blocking_review`

### Validation

- Added GitHub Actions validation for:
  - `examples/purity-assessment.sample.yaml`
  - `examples/purity-assessment.low-confidence.sample.yaml`
  - `examples/purity-assessment.recursive-synthetic-risk.sample.yaml`
- Confirmed that all three example files pass validation against:
  - `schemas/purity-assessment.schema.json`

### Notes

This release establishes **AI Purity Detection Algorithm v0.2** as a draft algorithmic layer for source-preservation systems.

The specification focuses on:

- origin-purity scoring
- natural / synthetic data separation
- hybrid data classification
- recursive synthetic risk detection
- warning-flag severity
- confidence handling
- review routing
- downstream-use guidance
- model-collapse monitoring support
- royalty-readiness review support

This release does not attempt to:

- prove legal authorship
- determine copyright ownership
- automatically assign royalties
- ban AI-assisted creation
- punish synthetic content
- perfectly detect AI-generated text
- replace human or multi-wing review

The core principle remains:

```text
Purity is not moral judgment.
Purity is ecological signal.

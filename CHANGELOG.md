# Changelog

All notable changes to this repository will be documented in this file.

This project follows a draft-oriented versioning model while the specification remains experimental.

---

## [Unreleased]

### Added

- Added `docs/relationship-to-consciousness-circle.md` to explain how AI Purity Detection relates to meaning-origin assessment, initial friction, resonance patterns, and Consciousness Circle.
- Added `docs/relationship-to-royalty-readiness.md` to explain how purity assessment supports royalty-readiness review without directly determining allocation or payment.
- Added `docs/relationship-to-collapse-monitor.md` to explain how source-level purity assessments may provide aggregate signals for CollapseMonitor and ecosystem-health monitoring.
- Added `docs/api-design-notes.md` to outline possible API endpoints, core objects, response structures, safety rules, and integration paths for future implementation.

### Changed

- Expanded the v0.2 relationship layer beyond scoring and warning flags.
- Clarified that AI Purity Detection can connect to:
  - Consciousness Circle
  - Royalty Readiness
  - CollapseMonitor
  - Trace Protocol
  - future API-based source-preservation systems
- Strengthened the distinction between:
  - assessment and judgment
  - purity scoring and royalty allocation
  - source integrity and meaning integrity
  - local source assessment and ecosystem-level monitoring

### Notes

The current `Unreleased` layer prepares the specification for broader integration.

The newly added relationship documents position AI Purity Detection Algorithm v0.2 as a bridge between:

```text
source-origin assessment
↓
meaning-structure assessment
↓
collapse-risk monitoring
↓
royalty-readiness review
↓
future API implementation

These documents do not turn purity scoring into an automatic legal, financial, or metaphysical decision system.

They preserve the core principle:

Expose evidence.
Expose uncertainty.
Route risk to review.
Do not automate judgment too early.
[0.2.0] - 2026-05-25
Added
Added initial README.md for AI Purity Detection Algorithm v0.2.
Added docs/v0.2-roadmap.md to define the proposed direction for the v0.2 specification.
Added docs/scoring-weighting-model.md to define a draft signal-weighting and confidence-adjusted scoring model.
Added docs/warning-flag-severity-model.md to define warning-flag severity levels, review routing, and downstream impact handling.
Added schemas/purity-assessment.schema.json for validating purity assessment examples.
Added examples/purity-assessment.sample.yaml as a standard purity assessment example.
Added examples/purity-assessment.low-confidence.sample.yaml to demonstrate weak provenance, unclear origin, low confidence, review-required routing, and blocked royalty-readiness status.
Added examples/purity-assessment.recursive-synthetic-risk.sample.yaml to demonstrate high recursive synthetic risk, weak primary-source provenance, high AI-pattern similarity, blocked training use, and blocked royalty-readiness status.
Added .github/workflows/validate-examples.yml to validate YAML examples against the JSON Schema.
Added LICENSE.
Added CITATION.cff.
Defined
Defined origin_purity_score as a normalized estimate of source-origin composition.
Defined ai_generated_ratio as a separate estimate of AI-generated or AI-assisted content ratio.
Defined warning_flags as routing and review-support signals.
Defined recursive_synthetic_risk as a key warning and ecosystem-risk signal.
Defined a draft signal-weighting model using:
provenance_evidence_score
author_declaration_score
structural_originality_score
revision_lineage_score
citation_transparency_score
ai_pattern_risk_score
structure_fingerprint_distinctiveness_score
recursive_synthetic_risk_score
signal_confidence_quality_score
Defined warning severity levels:
info
warning
review_required
blocking
Defined review-routing modes:
none
recommended
required
blocking_review
Validation
Added GitHub Actions validation for:
examples/purity-assessment.sample.yaml
examples/purity-assessment.low-confidence.sample.yaml
examples/purity-assessment.recursive-synthetic-risk.sample.yaml
Confirmed that all three example files pass validation against:
schemas/purity-assessment.schema.json
Notes

This release establishes AI Purity Detection Algorithm v0.2 as a draft algorithmic layer for source-preservation systems.

The specification focuses on:

origin-purity scoring
natural / synthetic data separation
hybrid data classification
recursive synthetic risk detection
warning-flag severity
confidence handling
review routing
downstream-use guidance
model-collapse monitoring support
royalty-readiness review support

This release does not attempt to:

prove legal authorship
determine copyright ownership
automatically assign royalties
ban AI-assisted creation
punish synthetic content
perfectly detect AI-generated text
replace human or multi-wing review

The core principle remains:

Purity is not moral judgment.
Purity is ecological signal.

This version provides a review-support and ecosystem-health layer for future AI source-preservation systems.

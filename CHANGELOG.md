# Changelog

All notable changes to this project will be documented in this file.

---

## [0.2.2] - 2026-05-26

### Added

- Added `docs/purity-ui-evolution-roadmap-v0.3.md`.
  - Introduces a future roadmap for evolving Purity UI beyond a basic platform display mock.
  - Defines possible v0.3 design directions:
    - Epicenter Layer
    - Proto-Friction Layer
    - Visibility Protocol
    - Circle Versioning
    - No-Inference Layer
    - Royalty OS Visibility
    - Epicenter Network
  - Positions future Purity UI as a creator-controlled origin interface.
  - Introduces the possibility of a future independent repository:
    - `purity-ui-control-architecture-v0.1`

### Updated

- Updated `README.md` to include `docs/purity-ui-evolution-roadmap-v0.3.md` in:
  - Repository Structure
  - Key Documents
  - Downstream Use Guidance
  - Relationship Map
  - Future Extensions
  - Recommended Reading Order
  - Reading Path by Role
  - Summary

### Clarified

- Clarified that Purity UI may evolve from a display layer into a creator-controlled origin interface.
- Clarified that future UI-control architecture may include:
  - creator-controlled visibility settings
  - no-inference policies
  - circle versioning
  - proto-friction capture
  - epicenter network visualization
  - royalty-readiness UI
  - AI-readable disclosure boundaries
- Clarified that future UI-control work is not part of the current production schema.

### Notes

- This release does not modify the core schema.
- This release does not modify existing examples.
- This release does not change the validation workflow.
- This is a documentation and future-roadmap update.

---

## [0.2.1] - 2026-05-26

### Added

- Added `docs/ui-mock-note-integration.md`.
  - Provides a platform UI mock for integrating Purity metadata into a note-style article page.
  - Shows how the following components may appear in a platform interface:
    - Purity Badge
    - Purity Breakdown
    - Consciousness Circle Panel
    - Trace Log
    - Royalty OS Preview
    - Creator Controls
  - Defines this UI mock as a reference design, not a mandatory implementation standard.
  - Clarifies that platform UI integration should preserve creator-controlled disclosure boundaries.

### Updated

- Updated `README.md` to include `docs/ui-mock-note-integration.md` in:
  - Repository Structure
  - Key Documents
  - Downstream Use Guidance
  - Relationship Map
  - Relationship to Platform UI Integration
  - API Design Direction
  - Non-Goals
  - Recommended Reading Order
  - Reading Path by Role
  - Summary

### Clarified

- Clarified that Purity metadata may support platform-facing displays, but should not be used to rank creators by purity score.
- Clarified that UI-facing Purity indicators should not treat AI assistance as negative by default.
- Clarified that Deep Layer and creator-sensitive semantic metadata should remain private by default.
- Clarified the distinction between:
  - backend purity assessment
  - semantic origin preservation
  - trace visibility
  - allocation-readiness preview
  - final royalty or payment execution

### Notes

- This release does not modify the core schema.
- This release does not modify existing examples.
- This release does not change the validation workflow.
- This is a documentation and platform-integration reference update.

---

## [0.2.0] - 2026-05-25

### Added

- Added `docs/v0.2-roadmap.md`.
  - Defines the proposed direction for AI Purity Detection Algorithm v0.2.
  - Outlines v0.1 baseline, v0.2 design goals, signal weighting, confidence handling, warning-flag severity, recursive synthetic risk detection, review routing, and relationship to adjacent systems.

- Added `docs/scoring-weighting-model.md`.
  - Defines the draft scoring model for calculating `origin_purity_score`.
  - Introduces weighted signals:
    - `provenance_evidence_score`
    - `author_declaration_score`
    - `structural_originality_score`
    - `revision_lineage_score`
    - `citation_transparency_score`
    - `ai_pattern_risk_score`
    - `structure_fingerprint_distinctiveness_score`
    - `recursive_synthetic_risk_score`
    - `signal_confidence_quality_score`
  - Defines confidence adjustment and recursive-risk adjustment.
  - Introduces interpretation bands and review-routing thresholds.

- Added `docs/warning-flag-severity-model.md`.
  - Defines warning-flag severity levels:
    - `info`
    - `warning`
    - `review_required`
    - `blocking`
  - Explains how warning flags affect review routing, downstream use, royalty-readiness transition, collapse monitoring, and uncertainty handling.

- Added `docs/relationship-to-consciousness-circle.md`.
  - Explains the relationship between AI Purity Detection and Consciousness Circle.
  - Distinguishes:
    - Purity Detection as the data-origin layer
    - Consciousness Circle as the meaning-origin layer
  - Connects origin purity with meaning depth, initial friction, resonance quality, boundary stability, and synthetic meaning risk.

- Added `docs/relationship-to-royalty-readiness.md`.
  - Explains how purity assessment may support Royalty Readiness.
  - Clarifies that `origin_purity_score` does not determine royalty entitlement.
  - Defines purity assessment as evidence preparation, not payment execution.

- Added `docs/relationship-to-collapse-monitor.md`.
  - Explains how source-level purity assessments may support ecosystem-level CollapseMonitor analysis.
  - Introduces possible aggregate metrics such as:
    - natural-data ratio
    - synthetic-data ratio
    - recursive synthetic risk rate
    - missing provenance rate
    - low-confidence assessment rate
    - review-required rate
    - training-use blocked rate
    - collapse-risk score
    - civilization-health index

- Added `docs/api-design-notes.md`.
  - Outlines possible API design for future implementation.
  - Includes preliminary notes on:
    - core API objects
    - proposed endpoints
    - purity assessment submission
    - assessment retrieval
    - batch assessment
    - source history
    - review routing
    - aggregate health signals
    - access control
    - privacy considerations
    - relationship to Trace Protocol, CollapseMonitor, Royalty Readiness, and Consciousness Circle

- Added `schemas/purity-assessment.schema.json`.
  - Provides JSON Schema validation for purity assessment outputs.
  - Validates required fields, score ranges, warning flags, review status, downstream-use permissions, optional v0.2 extensions, and ISO 8601 date-time format for `assessed_at`.

- Added example files:
  - `examples/purity-assessment.sample.yaml`
  - `examples/purity-assessment.low-confidence.sample.yaml`
  - `examples/purity-assessment.recursive-synthetic-risk.sample.yaml`

- Added GitHub Actions workflow:
  - `.github/workflows/validate-examples.yml`
  - Validates YAML examples against `schemas/purity-assessment.schema.json`.

### Updated

- Updated `README.md` for v0.2.
  - Added conceptual overview.
  - Added core principle.
  - Added design philosophy.
  - Added v0.2 focus.
  - Added repository structure.
  - Added key documents.
  - Added examples.
  - Added validation section.
  - Added scoring model overview.
  - Added warning severity overview.
  - Added review routing.
  - Added downstream-use guidance.
  - Added relationship map.
  - Added recommended reading order.
  - Added non-goals.

- Updated `CITATION.cff` for version `0.2.0`.

### Clarified

- Clarified that Purity is not a moral judgment.
- Clarified that AI-assisted creation should not be treated as invalid by default.
- Clarified that high AI-generated ratio does not automatically mean low value.
- Clarified that low AI-generated ratio does not automatically mean high originality.
- Clarified that warning flags are routing signals, not court verdicts.
- Clarified that purity assessment should support review and governance, not replace them.
- Clarified that Purity Detection does not determine:
  - legal authorship
  - copyright ownership
  - royalty allocation
  - final governance decisions
  - AI consciousness

### Notes

- Version 0.2.0 expands the project from a basic purity assessment concept into a weighted, review-aware, risk-sensitive model.
- The release introduces bridges to:
  - Consciousness Circle
  - Royalty Readiness
  - CollapseMonitor
  - future API implementation
- This release establishes the main v0.2 documentation structure.

---

## [0.1.0] - 2026-05-24

### Added

- Initial draft of AI Purity Detection Algorithm.
- Introduced the basic concept of estimating source-origin composition.
- Defined early purity assessment concepts:
  - origin purity
  - AI-generated ratio
  - warning flags
  - review status
  - downstream-use guidance
- Added initial schema and sample assessment structure.
- Added initial validation direction.

### Core Concepts

- Purity assessment as source-preservation support.
- Distinction between human-origin, AI-assisted, hybrid, and synthetic-heavy content.
- Recognition of recursive synthetic risk as a source-ecology problem.
- Early separation between:
  - source assessment
  - legal authorship
  - copyright ownership
  - royalty allocation
  - final governance decisions

### Notes

- Version 0.1.0 established the minimum conceptual foundation.
- Later v0.2 work expands this foundation into weighted scoring, severity modeling, review routing, and relationship documents.

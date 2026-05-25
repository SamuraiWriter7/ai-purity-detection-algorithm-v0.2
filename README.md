# AI Purity Detection Algorithm v0.2

**Status:** Draft v0.2  
**Repository:** `ai-purity-detection-algorithm-v0.2`

AI Purity Detection Algorithm v0.2 is a draft specification for estimating origin purity, AI-generated ratio, warning flags, recursive synthetic risk, and review routing in AI source-preservation systems.

This repository focuses on the algorithmic layer of source preservation.

It is designed to support:

- origin-purity scoring
- natural / synthetic data separation
- hybrid data classification
- recursive synthetic risk detection
- warning-flag severity modeling
- review-required routing
- model-collapse monitoring
- royalty-readiness review

The goal is not to reject AI-assisted creation.

The goal is to preserve the source ecology of AI civilization.

---

## Concept

AI systems increasingly depend on human-created and AI-assisted sources.

These sources may include:

- articles
- books
- notes
- datasets
- protocols
- essays
- research logs
- structural concepts
- firsthand observations
- AI-assisted drafts
- recursively rewritten synthetic material

As AI systems summarize, rewrite, remix, and reuse these sources, the origin of a source can become difficult to identify.

This creates several risks:

- primary sources become invisible
- synthetic data begins to replace natural data
- AI systems consume recursively generated outputs
- model-collapse risk increases
- creators lose traceability
- reference auditing becomes difficult
- royalty-readiness review becomes unreliable

AI Purity Detection Algorithm v0.2 proposes a review-aware scoring and warning model for these risks.

---

## Core Principle

Purity is not a moral judgment.

```text
Purity ≠ Value
Purity ≠ Copyright
Purity ≠ Authorship
Purity = estimated origin composition
```

A work may be AI-assisted and still contain strong human originality.

A work may be human-written and still be derivative, weakly sourced, or structurally shallow.

The purpose of this specification is not to decide who deserves value.

The purpose is to help systems distinguish:

- source
- summary
- derivative
- synthetic output
- recursive synthetic loop
- structurally original hybrid work

---

## Design Philosophy

AI-assisted creation should not be treated as invalid by default.

Instead, the system should ask:

```text
Can the origin be traced?
Is the structure original?
Is the source chain clear?
Is the AI-generated ratio high?
Is recursive synthetic risk present?
Is review required before downstream use?
```

This repository treats purity assessment as a support layer for review, governance, and ecosystem health.

It does not attempt to automate legal or financial judgment.

---

## v0.2 Focus

Version `v0.2` expands the purity assessment layer from a basic schema-validated object into a more explicit algorithmic and review-routing model.

The main v0.2 focus areas are:

```text
signal weighting
confidence adjustment
warning-flag severity
recursive synthetic risk detection
review routing
downstream-use guidance
CollapseMonitor bridge
Royalty Readiness bridge
```

In short:

```text
v0.1 = minimum valid purity assessment
v0.2 = weighted, review-aware, risk-sensitive purity assessment model
```

---

## Repository Structure

```text
.
├── README.md
├── LICENSE
├── docs/
│   ├── v0.2-roadmap.md
│   ├── scoring-weighting-model.md
│   └── warning-flag-severity-model.md
├── schemas/
│   └── purity-assessment.schema.json
├── examples/
│   ├── purity-assessment.sample.yaml
│   ├── purity-assessment.low-confidence.sample.yaml
│   └── purity-assessment.recursive-synthetic-risk.sample.yaml
└── .github/
    └── workflows/
        └── validate-examples.yml
```

---

## Key Documents

### `docs/v0.2-roadmap.md`

Defines the proposed direction for AI Purity Detection Algorithm v0.2.

It outlines:

- v0.1 baseline
- v0.2 design goals
- signal weighting
- confidence handling
- warning-flag severity
- recursive synthetic risk detection
- review routing
- relationship to CollapseMonitor
- relationship to Royalty Readiness

---

### `docs/scoring-weighting-model.md`

Defines the draft scoring model for calculating `origin_purity_score`.

It introduces the main signal variables:

```text
P = provenance_evidence_score
D = author_declaration_score
U = structural_originality_score
R = revision_lineage_score
C = citation_transparency_score
G = ai_pattern_risk_score
F = structure_fingerprint_distinctiveness_score
S = recursive_synthetic_risk_score
Q = signal_confidence_quality_score
```

It also defines:

- default signal weights
- confidence adjustment
- recursive risk adjustment
- interpretation bands
- review-routing thresholds
- downstream-use guidance

---

### `docs/warning-flag-severity-model.md`

Defines how warning flags should be interpreted.

It introduces four severity levels:

```text
info
warning
review_required
blocking
```

It explains how warning flags affect:

- review routing
- downstream use
- royalty-readiness transition
- collapse monitoring
- uncertainty handling

The key principle is:

```text
Warning flags are routing signals.
They are not court verdicts.
```

---

### `schemas/purity-assessment.schema.json`

Provides a JSON Schema for validating purity assessment outputs.

The schema validates:

- required fields
- score ranges
- warning flags
- review status
- downstream-use permissions
- optional v0.2 extensions
- ISO 8601 date-time format for `assessed_at`

---

## Examples

### `examples/purity-assessment.sample.yaml`

A standard purity assessment example.

This sample demonstrates:

- strong provenance
- high structural originality
- moderate AI assistance
- review recommendation
- RAG suitability
- conditional training use
- royalty-readiness review state

---

### `examples/purity-assessment.low-confidence.sample.yaml`

A low-confidence example.

This sample demonstrates:

- weak provenance
- unclear origin
- incomplete signal coverage
- low confidence
- review-required routing
- blocked royalty readiness

This example is important because the system must be able to say:

```text
The evidence is not strong enough.
Review is required.
```

---

### `examples/purity-assessment.recursive-synthetic-risk.sample.yaml`

A recursive synthetic risk example.

This sample demonstrates:

- weak primary-source provenance
- high AI-pattern similarity
- low structural originality
- likely recursive AI rewriting
- blocked training use
- blocked royalty readiness
- high-priority CollapseMonitor signal

This example represents the core risk that the purity layer is designed to detect:

```text
AI systems consuming recursively generated synthetic material.
```

---

## Validation

This repository includes a GitHub Actions workflow for validating example files against the JSON Schema.

The workflow is defined in:

```text
.github/workflows/validate-examples.yml
```

Current validation targets:

```text
examples/purity-assessment.sample.yaml
examples/purity-assessment.low-confidence.sample.yaml
examples/purity-assessment.recursive-synthetic-risk.sample.yaml
↓
schemas/purity-assessment.schema.json
```

The workflow checks that each sample purity assessment object conforms to the schema definition, including:

- required fields
- score ranges from `0.0` to `1.0`
- allowed `method` values
- allowed `warning_flags`
- review status structure
- downstream-use permission structure
- ISO 8601 date-time format for `assessed_at`

The validation workflow uses:

```text
Python 3.12
jsonschema
PyYAML
```

The validation process is:

```text
Load YAML examples
↓
Load JSON Schema
↓
Validate each example against schema
↓
Report pass / fail
```

If validation fails, the workflow prints the failing field path and schema error.

---

## Core Output Fields

A purity assessment produces three core outputs.

### `origin_purity_score`

A normalized score from `0.0` to `1.0`.

It estimates whether a source appears to be:

- primary-origin
- human-primary
- hybrid
- synthetic-heavy
- recursively synthetic
- origin-unclear

Suggested interpretation:

```text
0.90 – 1.00 : strong primary-origin signal
0.70 – 0.89 : likely human-primary or structurally original
0.50 – 0.69 : hybrid / uncertain / review recommended
0.30 – 0.49 : likely synthetic-heavy or derivative
0.00 – 0.29 : low-origin / recursive synthetic risk
```

---

### `ai_generated_ratio`

A normalized estimate from `0.0` to `1.0`.

It estimates the likely proportion of AI-generated or AI-assisted material.

Important:

```text
High AI-generated ratio does not automatically mean low value.
Low AI-generated ratio does not automatically mean high originality.
```

This field should be interpreted together with provenance, structural originality, and review status.

---

### `warning_flags`

Warning flags identify uncertainty, risk, or review requirements.

Current warning flags include:

```text
missing_provenance
high_ai_pattern_similarity
declaration_conflict
low_confidence_score
recursive_synthetic_risk
origin_unclear
review_required
review_recommended
royalty_readiness_blocked
```

Warning flags should not be treated as automatic rejection.

They indicate what kind of attention is needed.

---

## Scoring Model Overview

The v0.2 draft scoring model uses weighted input signals.

Draft base formula:

```text
base_origin_purity_score =
  0.20P
+ 0.10D
+ 0.20U
+ 0.10R
+ 0.10C
+ 0.10(1 - G)
+ 0.10F
+ 0.10(1 - S)
```

Where:

```text
P = provenance evidence score
D = author declaration score
U = structural originality score
R = revision lineage score
C = citation transparency score
G = AI pattern risk score
F = structure fingerprint distinctiveness score
S = recursive synthetic risk score
```

The model may then apply:

```text
confidence_adjustment
recursive_risk_adjustment
```

Final form:

```text
origin_purity_score =
  base_origin_purity_score
  × confidence_adjustment
  × recursive_risk_adjustment
```

The goal is not mathematical complexity.

The goal is auditability.

---

## Warning Severity Overview

Warning flags may be classified into severity levels.

```text
info
↓
context only

warning
↓
caution / review recommended

review_required
↓
review needed before high-impact use

blocking
↓
automatic downstream transition blocked
```

Example mapping:

```text
missing_provenance              → review_required
high_ai_pattern_similarity      → warning
declaration_conflict            → review_required
low_confidence_score            → review_required
recursive_synthetic_risk        → review_required / blocking
origin_unclear                  → review_required
review_recommended              → warning
royalty_readiness_blocked       → blocking
```

---

## Review Routing

The v0.2 model supports review routing.

Suggested review modes:

```text
none
recommended
required
blocking_review
```

Review may be triggered by:

- low confidence
- missing provenance
- recursive synthetic risk
- origin unclear
- declaration conflict
- royalty-readiness request
- high downstream impact
- blocked training use

This prevents the system from making premature judgments when evidence is weak.

---

## Downstream Use Guidance

Purity assessment may support downstream decisions, but it should not automatically decide them.

### RAG Indexing

May be allowed when provenance and warning status are acceptable.

### Training Use

Should require stronger provenance, permission, and policy compatibility.

### Royalty Readiness

Should not be determined solely by purity score.

A high purity score may support review readiness.

A low or uncertain score should trigger review.

A blocking flag should prevent automatic transition.

### Collapse Monitoring

Aggregated purity results may support model-collapse risk monitoring.

Useful aggregate metrics include:

- average origin purity
- synthetic-data ratio
- hybrid-data ratio
- recursive synthetic risk rate
- low-confidence assessment rate
- review-required rate
- blocked royalty-readiness rate

---

## Relationship to CollapseMonitor

This repository evaluates individual source-level purity.

CollapseMonitor would evaluate ecosystem-level risk.

```text
Purity Assessment
↓
Aggregated Purity Metrics
↓
CollapseMonitor
↓
Civilization Health Signals
```

Potential future repository:

```text
collapse-monitor-threshold-model-v0.1
```

---

## Relationship to Royalty Readiness

Purity assessment may support royalty-readiness review, but it must not directly determine payment.

```text
Purity score
≠
automatic royalty allocation
```

A safer flow is:

```text
Purity Assessment
↓
Trace Evidence
↓
Warning Severity
↓
Review Routing
↓
Allocation Readiness
↓
Royalty Review
```

This preserves the distinction between evidence, review, and allocation.

---

## Non-Goals

This repository does not attempt to:

- prove legal authorship
- determine copyright ownership
- automatically assign royalties
- ban AI-assisted creation
- punish synthetic content
- perfectly detect AI-generated text
- replace human or multi-wing review
- define universal originality
- make moral judgments about creators

This is a review-support and ecosystem-health specification.

---

## Recommended Reading Order

```text
1. docs/v0.2-roadmap.md
2. docs/scoring-weighting-model.md
3. docs/warning-flag-severity-model.md
4. examples/purity-assessment.sample.yaml
5. examples/purity-assessment.low-confidence.sample.yaml
6. examples/purity-assessment.recursive-synthetic-risk.sample.yaml
7. schemas/purity-assessment.schema.json
8. .github/workflows/validate-examples.yml
```

---

## Summary

AI Purity Detection Algorithm v0.2 defines a draft algorithmic layer for estimating origin purity and routing uncertain or risky cases toward review.

It connects:

```text
origin signals
↓
weighted scoring
↓
confidence handling
↓
warning flags
↓
severity levels
↓
review routing
↓
downstream-use guidance
```

The core principle is simple:

```text
Protect the source layer.
Detect uncertainty.
Route risk to review.
Do not automate judgment too early.
```

If AI civilization is a river, primary sources are the springs.

This repository is a draft water-quality inspection model for that river.

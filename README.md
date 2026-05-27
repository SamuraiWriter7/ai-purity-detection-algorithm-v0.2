# AI Purity Detection Algorithm v0.2

**Status:** Draft v0.2  
**Repository:** `ai-purity-detection-algorithm-v0.2`  
**Version:** 0.2.2

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
- meaning-structure relationship review
- platform UI integration patterns
- future Purity UI control architecture
- future API-based implementation

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
- meaning structures become shallow or generic
- platform interfaces fail to show origin context
- creator-controlled disclosure boundaries remain underdeveloped

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
Can the creator control disclosure boundaries?
Can platform UI preserve the origin context?
```

This repository treats purity assessment as a support layer for review, governance, platform design, and ecosystem health.

It does not attempt to automate legal, financial, or moral judgment.

---

## v0.2 Focus

Version `v0.2` expands the purity assessment layer from a basic schema-validated object into a more explicit algorithmic, review-routing, relationship-aware, and platform-integration model.

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
Consciousness Circle bridge
platform UI integration mock
future Purity UI evolution roadmap
API design notes
```

In short:

```text
v0.1 = minimum valid purity assessment
v0.2 = weighted, review-aware, risk-sensitive purity assessment model
v0.2.1 = platform UI integration reference added
v0.2.2 = Purity UI v0.3 evolution roadmap added
```

---

## Repository Structure

```text
.
├── README.md
├── CHANGELOG.md
├── CITATION.cff
├── LICENSE
├── docs/
│   ├── v0.2-roadmap.md
│   ├── scoring-weighting-model.md
│   ├── warning-flag-severity-model.md
│   ├── relationship-to-consciousness-circle.md
│   ├── relationship-to-royalty-readiness.md
│   ├── relationship-to-collapse-monitor.md
│   ├── api-design-notes.md
│   ├── ui-mock-note-integration.md
│   └── purity-ui-evolution-roadmap-v0.3.md
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

### Directory Overview

- `docs/`  
  Explanatory documents, relationship notes, scoring models, warning-severity models, API design notes, platform UI mock references, and future UI evolution roadmap documents.

- `schemas/`  
  JSON Schema definitions for validating Purity assessment objects.

- `examples/`  
  YAML examples showing standard, low-confidence, and recursive synthetic-risk assessment cases.

- `.github/workflows/`  
  GitHub Actions workflow for validating examples against the schema.

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

### `docs/relationship-to-consciousness-circle.md`

Explains how AI Purity Detection relates to Consciousness Circle.

This document distinguishes:

```text
Purity Detection = data-origin layer
Consciousness Circle = meaning-origin layer
```

It explores how origin purity may connect to:

- meaning depth
- initial friction
- resonance quality
- boundary stability
- consciousness-like response structure
- synthetic meaning risk
- creator-controlled disclosure

It does not claim that AI has consciousness.

It defines a relationship between source integrity and meaning integrity.

---

### `docs/relationship-to-royalty-readiness.md`

Explains how purity assessment supports Royalty Readiness.

This document clarifies that:

```text
origin_purity_score
≠
royalty entitlement
```

Purity assessment may support:

- readiness review
- warning severity review
- trace evidence review
- blocked-state handling
- disputed-state handling
- allocation-preparation logic

It does not define final royalty rates, payment, or legal ownership.

---

### `docs/relationship-to-collapse-monitor.md`

Explains how source-level purity assessments may support CollapseMonitor.

This document defines the relationship between:

```text
Purity Detection = local source assessment
CollapseMonitor = systemic health monitoring
```

It outlines possible aggregate metrics such as:

- natural-data ratio
- synthetic-data ratio
- recursive synthetic risk rate
- missing provenance rate
- low-confidence assessment rate
- review-required rate
- training-use blocked rate
- collapse-risk score
- civilization-health index

It does not define a production-ready CollapseMonitor implementation.

---

### `docs/api-design-notes.md`

Outlines possible API design for future implementation.

It includes preliminary notes on:

- core API objects
- proposed endpoints
- purity assessment submission
- assessment retrieval
- batch assessment
- source history
- review routing
- aggregate health signals
- safety rules
- error handling
- access control
- privacy considerations
- relationship to Trace Protocol
- relationship to CollapseMonitor
- relationship to Royalty Readiness
- relationship to Consciousness Circle

This document is a design bridge, not a production API specification.

---

### `docs/ui-mock-note-integration.md`

Provides a platform UI mock showing how Purity metadata could be integrated into a note-style article page.

It connects:

- Purity Badge
- Purity Breakdown
- Consciousness Circle Panel
- Trace Log
- Royalty OS Preview
- Creator Controls

This document translates the v0.2 specification from an algorithmic layer into a possible platform-facing interface.

It is a reference design, not a mandatory implementation standard.

The core purpose is to show how an article page could evolve from a simple content display into a creator-controlled semantic origin interface.

---

### `docs/purity-ui-evolution-roadmap-v0.3.md`

Provides a future roadmap for evolving Purity UI beyond a score display or basic platform mock.

It introduces possible v0.3 design directions, including:

- Epicenter Layer
- Proto-Friction Layer
- Visibility Protocol
- Circle Versioning
- No-Inference Layer
- Royalty OS Visibility
- Epicenter Network

This document is not a final specification.

It is a roadmap for exploring how Purity UI may evolve into a creator-controlled origin interface and, eventually, a separate Purity UI Control Architecture.

Possible future repository:

```text
purity-ui-control-architecture-v0.1
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

This field should be interpreted together with provenance, structural originality, confidence, and review status.

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

### Platform UI Integration

Purity metadata may also support platform-facing displays.

Possible UI elements include:

- Purity Badge
- Purity Breakdown
- Consciousness Circle summary
- Trace visibility panel
- Royalty OS preview
- Creator disclosure controls

These UI elements should remain creator-controlled and should not expose private semantic context by default.

See:

```text
docs/ui-mock-note-integration.md
```

### Future UI Control Architecture

Future versions may explore how Purity UI evolves from a display layer into a creator-controlled origin interface.

Possible future UI-control concepts include:

- Epicenter Layer
- Proto-Friction Layer
- Visibility Protocol
- Circle Versioning
- No-Inference Layer
- Royalty OS Visibility
- Epicenter Network

See:

```text
docs/purity-ui-evolution-roadmap-v0.3.md
```

---

## Relationship Map

AI Purity Detection Algorithm v0.2 connects to multiple surrounding systems.

```text
Trace Protocol
↓
Purity Assessment
↓
Warning Severity
↓
Review Routing
↓
Royalty Readiness
```

```text
Purity Assessment
↓
Aggregate Metrics
↓
CollapseMonitor
↓
Model / Corpus / Civilization Health Signals
```

```text
Purity Assessment
+
Consciousness Circle
↓
Source Integrity
+
Meaning Integrity
```

```text
Purity Assessment
↓
API Layer
↓
External Systems
```

```text
Purity Assessment
+
Consciousness Circle
+
Trace Log
+
Creator Controls
↓
Platform UI Integration
```

```text
Platform UI Integration
+
Visibility Protocol
+
No-Inference Layer
+
Circle Versioning
↓
Future Purity UI Control Architecture
```

---

## Relationship to Consciousness Circle

This repository evaluates data-origin integrity.

Consciousness Circle evaluates meaning-origin and response-structure integrity.

Together, they support a deeper review model:

```text
origin purity
+
meaning depth
+
initial friction
+
resonance quality
+
creator-controlled disclosure
```

The key distinction is:

```text
Origin purity alone is not meaning.
Meaning depth alone is not provenance.
```

---

## Relationship to Royalty Readiness

Purity assessment may support Royalty Readiness, but must not directly determine payment.

```text
Purity Detection does not pay.
Purity Detection prepares the evidence.
Royalty Readiness decides whether review can begin.
```

Recommended flow:

```text
Purity Assessment
↓
Trace Evidence
↓
Warning Severity
↓
Review Routing
↓
Royalty Readiness
↓
Allocation Review
```

---

## Relationship to CollapseMonitor

This repository evaluates individual source-level purity.

CollapseMonitor would evaluate ecosystem-level risk.

```text
Purity Detection
↓
Aggregate Metrics
↓
CollapseMonitor
↓
Model / Corpus / Civilization Health Signals
```

Possible future repository:

```text
collapse-monitor-threshold-model-v0.1
```

---

## Relationship to Platform UI Integration

Purity assessment can be used not only as a backend review signal, but also as a platform-facing origin-preservation interface.

The UI integration layer may show:

```text
Purity Badge
↓
Purity Breakdown
↓
Consciousness Circle Panel
↓
Trace Log
↓
Royalty OS Preview
↓
Creator Controls
```

The purpose is not to rank creators by purity.

The purpose is to help platforms show whether a work preserves a meaningful human-origin epicenter and whether the creator controls the disclosure boundary.

See:

```text
docs/ui-mock-note-integration.md
```

---

## Future Extensions

This repository may later connect to or seed future specifications.

Possible future directions include:

### Purity UI Control Architecture

A future repository may define a dedicated control architecture for Purity UI.

Possible repository name:

```text
purity-ui-control-architecture-v0.1
```

This future work may include:

- creator-controlled visibility settings
- no-inference policies
- circle versioning
- proto-friction capture
- epicenter network visualization
- royalty-readiness UI
- AI-readable disclosure boundaries

The current roadmap is documented in:

```text
docs/purity-ui-evolution-roadmap-v0.3.md
```

### CollapseMonitor Threshold Model

A future repository may define aggregate thresholds for ecosystem-level collapse-risk monitoring.

Possible repository name:

```text
collapse-monitor-threshold-model-v0.1
```

### Royalty Readiness Review Layer

A future repository may define a more formal review layer between trace evidence and allocation review.

### Platform API Profile

A future repository or document may define an implementation-oriented API profile for Purity assessment, creator controls, and platform UI integration.

---

## API Design Direction

The API layer should expose:

- source input
- purity assessment
- origin-purity score
- AI-generated ratio
- warning flags
- recursive synthetic risk
- review routing
- downstream-use guidance
- aggregate health signals
- optional UI-facing metadata
- creator disclosure settings

The API should not make final legal, financial, or moral decisions.

The central API principle is:

```text
Expose evidence.
Expose uncertainty.
Expose review routing.
Do not expose premature judgment as final truth.
```

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
- prove AI consciousness
- make moral judgments about creators
- force disclosure of private creator context
- rank creators by purity score
- define a final platform UI standard
- define a production-ready Purity UI Control Architecture

This is a review-support, platform-guidance, and ecosystem-health specification.

---

## Recommended Reading Order

For readers who want to understand this repository step by step, the following order is recommended.

```text
1. README.md
2. docs/v0.2-roadmap.md
3. docs/scoring-weighting-model.md
4. docs/warning-flag-severity-model.md
5. examples/purity-assessment.sample.yaml
6. examples/purity-assessment.low-confidence.sample.yaml
7. examples/purity-assessment.recursive-synthetic-risk.sample.yaml
8. schemas/purity-assessment.schema.json
9. docs/relationship-to-consciousness-circle.md
10. docs/relationship-to-royalty-readiness.md
11. docs/relationship-to-collapse-monitor.md
12. docs/api-design-notes.md
13. docs/ui-mock-note-integration.md
14. docs/purity-ui-evolution-roadmap-v0.3.md
15. .github/workflows/validate-examples.yml
```

### Reading Path by Role

#### For general readers

```text
README.md
↓
docs/v0.2-roadmap.md
↓
docs/ui-mock-note-integration.md
↓
docs/purity-ui-evolution-roadmap-v0.3.md
```

#### For implementers

```text
README.md
↓
schemas/purity-assessment.schema.json
↓
examples/
↓
docs/api-design-notes.md
```

#### For reviewers and governance designers

```text
docs/scoring-weighting-model.md
↓
docs/warning-flag-severity-model.md
↓
docs/relationship-to-royalty-readiness.md
↓
docs/relationship-to-collapse-monitor.md
```

#### For platform designers

```text
docs/relationship-to-consciousness-circle.md
↓
docs/api-design-notes.md
↓
docs/ui-mock-note-integration.md
↓
docs/purity-ui-evolution-roadmap-v0.3.md
```

#### For future UI-control architecture designers

```text
docs/ui-mock-note-integration.md
↓
docs/purity-ui-evolution-roadmap-v0.3.md
```

---

## Version History

See:

```text
CHANGELOG.md
```

Current release:

```text
0.2.2
```

---

## Citation

If you use this specification, please cite it using:

```text
CITATION.cff
```

---

## License

This repository is released under the license defined in:

```text
LICENSE
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
↓
platform UI integration
↓
future UI control architecture
```

The core principle is simple:

```text
Protect the source layer.
Detect uncertainty.
Route risk to review.
Preserve creator control.
Do not automate judgment too early.
```

If AI civilization is a river, primary sources are the springs.

This repository is a draft water-quality inspection model for that river, and a starting point for future creator-controlled origin interfaces.


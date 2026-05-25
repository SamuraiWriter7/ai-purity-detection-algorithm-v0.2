# Scoring Weighting Model v0.2 Draft

## Status

Draft specification.

This document defines the proposed scoring and weighting model for **Purity Detection Algorithm v0.2**.

It extends the v0.1.1 purity assessment structure by making the scoring process more explicit, auditable, and review-aware.

This document does not define legal authorship, copyright ownership, or final royalty allocation.

It defines a review-support model for estimating origin purity and routing uncertain cases toward human or multi-wing review.

---

## 1. Purpose

The purpose of the Scoring Weighting Model is to define how different purity signals may contribute to an `origin_purity_score`.

Version `v0.1.1` established the basic structure:

```text
signals
↓
origin_purity_score
↓
ai_generated_ratio
↓
warning_flags
↓
review status
↓
downstream_use
```

Version `v0.2` strengthens this structure by defining:

- default signal weights
- confidence adjustment
- recursive synthetic risk adjustment
- warning-flag influence
- review-routing thresholds
- downstream interpretation rules

The goal is not to create a perfect detector.

The goal is to create an auditable scoring framework.

---

## 2. Core Principle

Purity scoring must remain separate from value judgment.

```text
origin_purity_score
≠
content value

origin_purity_score
≠
legal authorship

origin_purity_score
≠
royalty entitlement
```

The score estimates the likely origin composition of an Epicenter.

It is an ecological and provenance signal.

It should be used to support:

- source preservation
- RAG corpus management
- model-collapse monitoring
- reference auditing
- royalty-readiness review
- dispute-aware governance

It should not be used as an automatic enforcement mechanism.

---

## 3. Input Signals

The v0.2 model uses the following primary signals.

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

Each signal should be normalized from `0.0` to `1.0`.

---

## 4. Signal Definitions

### 4.1 Provenance Evidence Score `P`

Measures how clearly the origin of the Epicenter can be verified.

Strong evidence may include:

- publication timestamp
- platform metadata
- version history
- archive record
- signed attestation
- cryptographic hash
- traceable source URL

Suggested scale:

```text
1.0 = timestamped, archived, versioned, and traceable
0.8 = timestamped and publicly verifiable
0.6 = platform metadata exists but limited history
0.4 = weak metadata
0.2 = unverifiable claim
0.0 = no provenance evidence
```

---

### 4.2 Author Declaration Score `D`

Measures the clarity and usefulness of the creator's declaration regarding AI assistance and source composition.

This score measures disclosure quality, not human purity.

Suggested scale:

```text
1.0 = detailed declaration of AI use and source composition
0.8 = clear general declaration
0.6 = partial declaration
0.4 = ambiguous declaration
0.2 = inconsistent declaration
0.0 = no declaration
```

---

### 4.3 Structural Originality Score `U`

Measures whether the Epicenter contains original structure, concept formation, argument design, taxonomy, protocol design, or non-generic synthesis.

Strong indicators include:

- original framework
- new conceptual vocabulary
- unique layered structure
- non-obvious synthesis
- reusable protocol design
- distinctive philosophical architecture

Suggested scale:

```text
1.0 = clearly original framework / protocol / concept
0.8 = strong original synthesis
0.6 = moderate original arrangement
0.4 = mostly derivative explanation
0.2 = generic reformulation
0.0 = no identifiable original structure
```

---

### 4.4 Revision Lineage Score `R`

Measures whether the development history of the Epicenter can be observed.

Suggested scale:

```text
1.0 = full revision history available
0.8 = major revisions visible
0.6 = limited version records
0.4 = publication timestamp only
0.2 = weak lineage
0.0 = no lineage evidence
```

---

### 4.5 Citation Transparency Score `C`

Measures whether dependencies, citations, prior sources, or conceptual influences are clearly disclosed.

This score does not penalize influence.

It rewards transparency.

Suggested scale:

```text
1.0 = dependencies and references clearly stated
0.8 = major references stated
0.6 = partial references
0.4 = vague references
0.2 = weak attribution
0.0 = no attribution despite apparent dependency
```

---

### 4.6 AI Pattern Risk Score `G`

Measures similarity to known synthetic or generic AI-generated patterns.

Potential indicators include:

- generic explanatory structure
- excessive symmetry
- high template similarity
- repeated AI rhetorical scaffolding
- low specificity
- shallow summarization pattern
- generic conclusion structure

Suggested scale:

```text
1.0 = very high similarity to known synthetic patterns
0.8 = high synthetic pattern similarity
0.6 = moderate similarity
0.4 = low similarity
0.2 = very low similarity
0.0 = no synthetic pattern detected
```

This score is inverted when calculating origin purity:

```text
1 - G
```

---

### 4.7 Structure Fingerprint Distinctiveness Score `F`

Measures whether the structure fingerprint of the Epicenter appears distinctive compared with known generic or synthetic structures.

Suggested scale:

```text
1.0 = highly distinctive structure fingerprint
0.8 = strong distinctive pattern
0.6 = moderately distinctive
0.4 = weak distinctiveness
0.2 = generic or common structure
0.0 = indistinguishable from synthetic/common patterns
```

This signal is especially important for works where originality exists at the structural level rather than surface wording.

---

### 4.8 Recursive Synthetic Risk Score `S`

Measures the likelihood that the Epicenter is derived from multiple layers of AI-generated or AI-rewritten material.

Potential indicators include:

- weak primary-source provenance
- repeated summarization patterns
- shallow citation chain
- high AI-pattern similarity
- absence of firsthand observation
- derivative phrasing across multiple sources
- low structural originality
- evidence of recursive AI rewriting

Suggested scale:

```text
1.0 = critical recursive synthetic risk
0.8 = high recursive synthetic risk
0.6 = moderate recursive synthetic risk
0.4 = low recursive synthetic risk
0.2 = very low recursive synthetic risk
0.0 = no recursive synthetic risk detected
```

This score is also inverted or used as a penalty factor.

---

### 4.9 Signal Confidence Quality Score `Q`

Measures the reliability of the available signal set.

This is not the same as origin purity.

It measures how much confidence the system should place in the assessment.

Suggested scale:

```text
1.0 = strong signal coverage and high reliability
0.8 = good signal coverage
0.6 = moderate signal coverage
0.4 = weak or incomplete signal coverage
0.2 = very weak signal coverage
0.0 = insufficient evidence
```

---

## 5. Default Weighting Model

The v0.2 draft model uses the following default weights.

```text
P = 0.20
D = 0.10
U = 0.20
R = 0.10
C = 0.10
G = 0.10
F = 0.10
S = 0.10
```

Total:

```text
0.20 + 0.10 + 0.20 + 0.10 + 0.10 + 0.10 + 0.10 + 0.10 = 1.00
```

Risk signals are inverted:

```text
G becomes (1 - G)
S becomes (1 - S)
```

---

## 6. Draft Formula

The base score is calculated as:

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

Then clamp the result:

```text
base_origin_purity_score =
  min(1.0, max(0.0, base_origin_purity_score))
```

---

## 7. Confidence Adjustment

The model should not treat low-confidence results as equally reliable.

A confidence adjustment may be applied after calculating the base score.

Suggested confidence bands:

```text
0.85 – 1.00 : high confidence
0.70 – 0.84 : moderate confidence
0.50 – 0.69 : low confidence
0.00 – 0.49 : unreliable / review required
```

Suggested adjustment:

```text
if Q >= 0.85:
  confidence_adjustment = 1.00

if 0.70 <= Q < 0.85:
  confidence_adjustment = 0.95

if 0.50 <= Q < 0.70:
  confidence_adjustment = 0.85

if Q < 0.50:
  confidence_adjustment = 0.70
```

Adjusted score:

```text
adjusted_origin_purity_score =
  base_origin_purity_score × confidence_adjustment
```

This prevents incomplete evidence from producing overly strong claims.

---

## 8. Recursive Risk Adjustment

Recursive synthetic risk should influence both score and review routing.

If recursive synthetic risk is high, the assessment should become more conservative.

Suggested adjustment:

```text
if S < 0.40:
  recursive_risk_adjustment = 1.00

if 0.40 <= S < 0.60:
  recursive_risk_adjustment = 0.95

if 0.60 <= S < 0.80:
  recursive_risk_adjustment = 0.85

if S >= 0.80:
  recursive_risk_adjustment = 0.70
```

Final score:

```text
origin_purity_score =
  base_origin_purity_score
  × confidence_adjustment
  × recursive_risk_adjustment
```

Then clamp:

```text
origin_purity_score =
  min(1.0, max(0.0, origin_purity_score))
```

---

## 9. Warning-Flag Influence

Warning flags should not always reduce the score directly.

Some warning flags should affect review routing instead.

### 9.1 Score-Relevant Flags

These may influence the score:

```text
high_ai_pattern_similarity
recursive_synthetic_risk
origin_unclear
missing_provenance
```

### 9.2 Review-Relevant Flags

These may trigger review without directly changing the score:

```text
declaration_conflict
low_confidence_score
review_required
royalty_readiness_blocked
```

### 9.3 Suggested Behavior

```text
missing_provenance
↓
reduce confidence and trigger review

high_ai_pattern_similarity
↓
increase AI-pattern risk and trigger review recommendation

declaration_conflict
↓
trigger review required

recursive_synthetic_risk
↓
apply recursive risk adjustment and possibly block royalty readiness

origin_unclear
↓
trigger review required

royalty_readiness_blocked
↓
prevent downstream royalty-readiness transition
```

---

## 10. Interpretation Bands

The final `origin_purity_score` may be interpreted as follows.

```text
0.90 – 1.00 : strong primary-origin signal
0.70 – 0.89 : likely human-primary or structurally original
0.50 – 0.69 : hybrid / uncertain / review recommended
0.30 – 0.49 : likely synthetic-heavy or derivative
0.00 – 0.29 : low-origin / recursive synthetic risk
```

These bands are interpretive only.

They should not be used as automatic legal or financial thresholds.

---

## 11. Review Routing Thresholds

Suggested routing model:

```text
origin_purity_score >= 0.70 and Q >= 0.70
↓
review recommended only if warning flags are present

0.50 <= origin_purity_score < 0.70
↓
review recommended

origin_purity_score < 0.50
↓
review required

Q < 0.50
↓
review required

S >= 0.80
↓
blocking review required

declaration_conflict present
↓
review required

royalty_readiness_blocked present
↓
block royalty readiness
```

Review modes:

```text
none
recommended
required
blocking_review
```

---

## 12. Downstream Use Guidance

### 12.1 RAG Indexing

RAG indexing may be allowed when provenance is sufficient and no blocking flag is present.

Suggested state:

```yaml
rag_indexing:
  allowed: true
  notes: "Suitable for RAG reference with provenance metadata."
```

### 12.2 Training Use

Training use should require stronger consent, platform policy compatibility, and provenance clarity.

Suggested state:

```yaml
training_use:
  allowed: "conditional"
  notes: "Allowed only if creator permission and platform policy permit training use."
```

### 12.3 Royalty Readiness

Royalty readiness should never be determined solely by purity score.

Suggested states:

```text
not_ready
review_ready
ready
blocked
disputed
```

Recommended rules:

```text
high purity + strong trace + sufficient provenance
↓
review_ready

low confidence or origin unclear
↓
not_ready

recursive synthetic risk high
↓
blocked or review_required

dispute present
↓
disputed
```

### 12.4 Collapse Monitoring

CollapseMonitor may use aggregated purity scores, but individual scores should not be overinterpreted.

Useful aggregate metrics:

- average origin purity
- natural-data ratio
- synthetic-data ratio
- hybrid-data ratio
- recursive synthetic risk rate
- low-confidence assessment rate
- review-required rate

---

## 13. Example Calculation

Example input:

```yaml
signals:
  provenance_evidence_score: 0.85
  author_declaration_score: 0.80
  structural_originality_score: 0.92
  revision_lineage_score: 0.70
  citation_transparency_score: 0.65
  ai_pattern_risk_score: 0.22
  structure_fingerprint_distinctiveness_score: 0.88
  recursive_synthetic_risk_score: 0.18
  signal_confidence_quality_score: 0.74
```

Base calculation:

```text
base_origin_purity_score =
  0.20(0.85)
+ 0.10(0.80)
+ 0.20(0.92)
+ 0.10(0.70)
+ 0.10(0.65)
+ 0.10(1 - 0.22)
+ 0.10(0.88)
+ 0.10(1 - 0.18)
```

Result:

```text
base_origin_purity_score = 0.817
```

Confidence adjustment:

```text
Q = 0.74
confidence_adjustment = 0.95
```

Recursive risk adjustment:

```text
S = 0.18
recursive_risk_adjustment = 1.00
```

Final score:

```text
origin_purity_score =
  0.817 × 0.95 × 1.00
  = 0.776
```

Interpretation:

```text
likely human-primary or structurally original
```

Review routing:

```text
review recommended
```

Reason:

```text
Moderate confidence. Strong structural originality. Low recursive synthetic risk.
```

---

## 14. Schema Implications

Future schema extensions may include:

```yaml
scoring_model:
  version: "0.2.0"
  base_score: 0.817
  confidence_adjustment: 0.95
  recursive_risk_adjustment: 1.00
  final_score: 0.776

signal_weights:
  provenance_evidence_score: 0.20
  author_declaration_score: 0.10
  structural_originality_score: 0.20
  revision_lineage_score: 0.10
  citation_transparency_score: 0.10
  ai_pattern_risk_score: 0.10
  structure_fingerprint_distinctiveness_score: 0.10
  recursive_synthetic_risk_score: 0.10

review_routing:
  mode: "recommended"
  reason: "Moderate confidence with strong structural originality."
```

These fields may be added in a future schema version.

---

## 15. Non-Goals

This model does not attempt to:

- detect AI-generated text perfectly
- prove legal authorship
- define copyright ownership
- determine royalty allocation
- ban AI-assisted creation
- punish synthetic content
- replace human review
- define universal originality
- make moral judgments about creators

This model is a review-support and ecosystem-health mechanism.

---

## 16. Design Philosophy

The purpose of the scoring model is not to create a purity police.

The purpose is to prevent AI civilization from losing its source layer.

A useful purity model should be:

- transparent
- auditable
- cautious
- review-aware
- non-punitive
- provenance-sensitive
- resistant to recursive synthetic collapse

In short:

```text
The model should measure water quality.
It should not declare who owns the river.
```

---

## 17. Summary

Version `v0.2` should make purity scoring more explicit.

The proposed model introduces:

```text
weighted signals
confidence adjustment
recursive risk adjustment
warning-flag influence
review-routing thresholds
downstream-use guidance
```

The key principle remains:

```text
Purity is not moral judgment.
Purity is ecological signal.
```

This model is intended to support source preservation, reference auditing, collapse monitoring, and royalty-readiness review without automating final legal or financial decisions.

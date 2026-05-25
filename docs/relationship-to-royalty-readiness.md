# Relationship to Royalty Readiness

## Status

Draft relationship document.

This document explains how **AI Purity Detection Algorithm v0.2** relates to **Royalty Readiness**.

AI Purity Detection estimates origin purity, AI-generated ratio, warning flags, recursive synthetic risk, and review-routing status.

Royalty Readiness determines whether a source or Epicenter is sufficiently prepared for value-circulation review.

This document does not define legal authorship, copyright ownership, or final royalty allocation.

It defines how purity assessment may support royalty-readiness review without becoming an automatic payment mechanism.

---

## 1. Purpose

The purpose of this document is to clarify the relationship between:

```text
AI Purity Detection Algorithm
```

and:

```text
Royalty Readiness
```

AI Purity Detection asks:

```text
What is the likely origin composition of this source?
Is it human-primary, AI-assisted, hybrid, synthetic, or recursively synthetic?
Are there warning flags?
Is review required?
```

Royalty Readiness asks:

```text
Is this source ready to proceed toward value-circulation review?
Is there enough trace evidence?
Is the origin sufficiently clear?
Are there unresolved warnings or disputes?
Should royalty processing be allowed, deferred, blocked, or disputed?
```

In short:

```text
Purity Detection = evidence and risk layer
Royalty Readiness = allocation-preparation gate
```

---

## 2. Core Principle

Purity assessment must not directly determine royalty allocation.

```text
origin_purity_score
≠
royalty entitlement
```

```text
ai_generated_ratio
≠
automatic exclusion
```

```text
warning_flags
≠
final judgment
```

Purity assessment may support review.

It may strengthen or weaken readiness.

It may trigger review.

It may block automatic transition.

But it should not directly decide payment.

---

## 3. Why This Separation Matters

If purity scoring directly controls payment, the system becomes dangerous.

Possible risks:

- false positives may unfairly block creators
- AI-assisted but original work may be misclassified
- low-confidence assessments may be overused
- synthetic-risk detection may become punitive
- disputes may be bypassed
- governance may be replaced by opaque scoring

Therefore, the safer structure is:

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
↓
Royalty Decision
```

This preserves the distinction between:

```text
measurement
review
allocation
settlement
```

---

## 4. Layer Mapping

| Layer | Role |
|---|---|
| Purity Detection | Estimates origin composition and risk |
| Trace Protocol | Records reference or usage events |
| Warning Severity | Classifies review urgency |
| Review Routing | Determines whether review is needed |
| Royalty Readiness | Determines whether allocation review can proceed |
| Allocation Review | Evaluates contribution and distribution logic |
| Royalty Record | Represents possible settlement output |

---

## 5. Core Fields from Purity Detection

Royalty Readiness may consume the following fields from purity assessment.

### 5.1 `origin_purity_score`

A normalized score from `0.0` to `1.0`.

Possible use:

```text
High score
↓
may support review readiness

Low score
↓
may require review or block readiness
```

Important:

```text
High origin purity strengthens readiness.
It does not prove payment entitlement.
```

---

### 5.2 `ai_generated_ratio`

A normalized estimate of AI-generated or AI-assisted content ratio.

Possible use:

```text
Low or moderate AI-generated ratio
↓
may support readiness if structure and provenance are strong

High AI-generated ratio
↓
may require review, especially if provenance is weak
```

Important:

```text
AI assistance alone should not block royalty readiness.
```

A source may be AI-assisted and still contain:

- original structure
- human judgment
- distinctive concept design
- firsthand experience
- meaningful synthesis

---

### 5.3 `warning_flags`

Warning flags indicate uncertainty or risk.

Examples:

```text
missing_provenance
high_ai_pattern_similarity
declaration_conflict
low_confidence_score
recursive_synthetic_risk
origin_unclear
review_required
royalty_readiness_blocked
```

Possible use:

```text
warning flags
↓
determine review requirements
```

Important:

```text
Warning flags are routing signals.
They are not final verdicts.
```

---

### 5.4 `recursive_synthetic_risk`

Recursive synthetic risk is especially relevant to Royalty Readiness.

If a source appears to be derived from multiple layers of AI-generated or AI-rewritten material, royalty readiness should become conservative.

Possible interpretation:

```text
high recursive synthetic risk
↓
block or defer royalty-readiness transition
```

This protects the system from allocating value to unclear synthetic loops before source origin is reviewed.

---

## 6. Royalty Readiness States

The following readiness states are recommended.

```text
not_ready
review_ready
ready
blocked
disputed
```

---

### 6.1 `not_ready`

The source is not ready for royalty review.

Possible causes:

- weak provenance
- low confidence
- incomplete trace evidence
- missing creator declaration
- unclear origin
- insufficient metadata

Example:

```yaml
royalty_readiness:
  status: "not_ready"
  reason: "Trace evidence and provenance are insufficient."
```

---

### 6.2 `review_ready`

The source may proceed to review.

This does not mean payment is approved.

It means the source has enough evidence to be reviewed.

Possible conditions:

- sufficient provenance
- no blocking flags
- acceptable confidence
- trace evidence available
- review recommended but not blocked

Example:

```yaml
royalty_readiness:
  status: "review_ready"
  reason: "Source has sufficient provenance and no blocking warning flags."
```

---

### 6.3 `ready`

The source has passed required review and may proceed toward allocation processing.

Possible conditions:

- strong trace evidence
- clear provenance
- warning flags resolved
- review completed
- no active dispute
- allocation review approved

Example:

```yaml
royalty_readiness:
  status: "ready"
  reason: "Review completed and source is eligible for allocation processing."
```

---

### 6.4 `blocked`

The source must not proceed toward royalty review or allocation processing.

Possible causes:

- `royalty_readiness_blocked`
- high recursive synthetic risk
- unresolved origin uncertainty
- unresolved declaration conflict
- insufficient provenance
- active blocking review

Example:

```yaml
royalty_readiness:
  status: "blocked"
  reason: "Recursive synthetic risk and origin uncertainty remain unresolved."
```

---

### 6.5 `disputed`

The source is under dispute.

Possible causes:

- competing origin claims
- attribution conflict
- contributor disagreement
- provenance challenge
- lineage dispute
- platform or governance review

Example:

```yaml
royalty_readiness:
  status: "disputed"
  reason: "Origin claim is under dispute and requires governance review."
```

---

## 7. Suggested Readiness Rules

### 7.1 Review Ready

A source may become `review_ready` when:

```text
origin_purity_score >= 0.70
confidence >= 0.70
no blocking flags
trace evidence exists
provenance is sufficient
```

Suggested output:

```yaml
royalty_readiness:
  status: "review_ready"
  notes: "May proceed to review after trace verification."
```

---

### 7.2 Not Ready

A source should remain `not_ready` when:

```text
confidence < 0.60
or
missing provenance is unresolved
or
origin is unclear
or
trace evidence is incomplete
```

Suggested output:

```yaml
royalty_readiness:
  status: "not_ready"
  notes: "Additional provenance and trace evidence are required."
```

---

### 7.3 Blocked

A source should be `blocked` when:

```text
royalty_readiness_blocked flag is present
or
recursive_synthetic_risk is high or critical
or
declaration_conflict remains unresolved
or
blocking review is active
```

Suggested output:

```yaml
royalty_readiness:
  status: "blocked"
  notes: "Royalty-readiness transition is blocked until review is completed."
```

---

### 7.4 Disputed

A source should be `disputed` when:

```text
origin claim is contested
or
multiple Epicenter candidates exist
or
lineage relation is challenged
or
creator attribution is unresolved
```

Suggested output:

```yaml
royalty_readiness:
  status: "disputed"
  notes: "Origin or contribution claim requires dispute resolution."
```

---

## 8. Relationship to Warning Severity

Warning severity should strongly influence royalty readiness.

Suggested mapping:

```text
info
↓
no readiness effect by itself

warning
↓
review recommended

review_required
↓
not_ready until reviewed

blocking
↓
blocked until resolved
```

Example:

```text
high_ai_pattern_similarity
+
strong provenance
+
strong structural originality
=
review_ready with caution
```

```text
high_ai_pattern_similarity
+
missing_provenance
+
low_confidence_score
=
not_ready or blocked
```

```text
recursive_synthetic_risk
+
royalty_readiness_blocked
=
blocked
```

---

## 9. Relationship to Trace Evidence

Royalty Readiness requires more than purity.

A source may have high purity but no reference evidence.

In that case, it may not yet support royalty review.

Minimum trace evidence may include:

- reference event ID
- Epicenter ID
- model or system ID
- timestamp
- usage type
- reference weight
- context hash or retrieval record
- audit trail

Suggested flow:

```text
Purity Assessment
↓
Trace Evidence
↓
Reference Weight
↓
Review Routing
↓
Royalty Readiness
```

Without trace evidence, value allocation becomes speculative.

---

## 10. Relationship to Allocation Readiness

Royalty Readiness is close to Allocation Readiness, but they are not identical.

### Royalty Readiness

Asks:

```text
Can this source proceed toward royalty review?
```

### Allocation Readiness

Asks:

```text
Is the evidence sufficient to support a candidate allocation decision?
```

Possible distinction:

```text
Royalty Readiness = gate before allocation review
Allocation Readiness = gate before distribution logic
```

Suggested flow:

```text
Trace
↓
Purity
↓
Warning Severity
↓
Royalty Readiness
↓
Allocation Readiness
↓
Royalty Record
```

---

## 11. Relationship to RoyaltyRecord

A `RoyaltyRecord` should not be created solely because purity is high.

A safer sequence is:

```text
1. Epicenter is identified.
2. ReferenceEvent is recorded.
3. Purity Assessment is performed.
4. Warning flags are reviewed.
5. Royalty Readiness is evaluated.
6. Allocation Readiness is reviewed.
7. RoyaltyRecord may be generated.
```

This avoids premature accounting.

---

## 12. Example Readiness Evaluation

```yaml
royalty_readiness_evaluation:
  epicenter_id: "epicenter_001"
  purity_assessment_id: "purity_assessment_001"
  trace_evidence_id: "reference_event_001"

  inputs:
    origin_purity_score: 0.80
    ai_generated_ratio: 0.28
    confidence: 0.74
    warning_flags:
      - "review_recommended"

  trace_evidence:
    available: true
    reference_weight_available: true
    usage_type: "rag"

  decision:
    status: "review_ready"
    reason: "Purity, provenance, and trace evidence are sufficient for review. No blocking flags are present."

  next_action:
    type: "human_or_multi_wing_review"
    required: false
    recommended: true
```

---

## 13. Blocked Example

```yaml
royalty_readiness_evaluation:
  epicenter_id: "epicenter_recursive_synthetic_001"
  purity_assessment_id: "purity_assessment_recursive_synthetic_risk_001"

  inputs:
    origin_purity_score: 0.24
    ai_generated_ratio: 0.81
    confidence: 0.61
    warning_flags:
      - "missing_provenance"
      - "high_ai_pattern_similarity"
      - "recursive_synthetic_risk"
      - "origin_unclear"
      - "review_required"
      - "royalty_readiness_blocked"

  trace_evidence:
    available: false
    reference_weight_available: false
    usage_type: "unknown"

  decision:
    status: "blocked"
    reason: "Recursive synthetic risk, unclear origin, missing provenance, and insufficient trace evidence block royalty-readiness transition."

  next_action:
    type: "blocking_review"
    required: true
    recommended: true
```

---

## 14. Anti-Automation Principle

The most important rule is:

```text
Do not convert purity score directly into payment.
```

Unsafe pattern:

```text
origin_purity_score
↓
automatic royalty payment
```

Safer pattern:

```text
origin_purity_score
↓
warning severity
↓
trace evidence
↓
review routing
↓
royalty readiness
↓
allocation review
↓
royalty record
```

This protects:

- creators
- platforms
- AI providers
- reviewers
- downstream systems
- the credibility of the protocol itself

---

## 15. Relationship to Dispute Handling

Royalty Readiness should connect to dispute handling.

Disputes may arise when:

- multiple sources claim origin
- contribution is blended
- attribution is unclear
- AI assistance is contested
- synthetic derivation is suspected
- reference logs conflict

When dispute exists, the readiness state should become:

```text
disputed
```

The system should then route to:

- human review
- multi-wing review
- governance review
- dispute registry
- provenance audit
- lineage analysis

---

## 16. Relationship to CollapseMonitor

CollapseMonitor may use royalty-readiness outcomes as ecosystem signals.

Useful aggregate metrics:

- blocked royalty-readiness rate
- not-ready rate
- disputed source rate
- recursive synthetic risk rate
- low-confidence assessment rate
- missing-provenance rate

These metrics may indicate:

```text
source ecology weakening
```

or:

```text
synthetic material entering value-circulation pathways too early
```

Thus, Royalty Readiness is not only an accounting gate.

It is also a health signal for the AI source ecosystem.

---

## 17. Non-Goals

This document does not attempt to:

- define final royalty rates
- calculate actual payment
- prove legal authorship
- determine copyright ownership
- resolve disputes automatically
- replace human review
- define contribution percentages
- generate legally binding settlement records
- claim that purity equals entitlement

This document defines a readiness relationship, not a final allocation mechanism.

---

## 18. Design Principle

The central design principle is:

```text
Evidence first.
Review second.
Allocation later.
```

Purity Detection helps prepare evidence.

Royalty Readiness determines whether the evidence is sufficient to move forward.

Allocation and payment require additional governance.

---

## 19. Summary

AI Purity Detection Algorithm v0.2 supports Royalty Readiness by providing:

- origin-purity scoring
- AI-generated ratio
- warning flags
- recursive synthetic risk
- confidence signals
- review-routing information
- downstream-use guidance

Royalty Readiness uses these signals to determine whether a source is:

```text
not_ready
review_ready
ready
blocked
disputed
```

The relationship is simple:

```text
Purity Detection does not pay.
Purity Detection prepares the evidence.
Royalty Readiness decides whether review can begin.
```

In short:

```text
Purity protects the source.
Royalty Readiness protects the transition from source evidence to value circulation.
```

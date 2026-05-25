# Relationship to CollapseMonitor

## Status

Draft relationship document.

This document explains how **AI Purity Detection Algorithm v0.2** relates to **CollapseMonitor**.

AI Purity Detection evaluates individual sources or Epicenters.

CollapseMonitor evaluates aggregate ecosystem-level risk.

In short:

```text
Purity Detection = local source assessment
CollapseMonitor = systemic health monitoring
```

This document does not define a complete CollapseMonitor implementation.

It defines how purity assessment outputs may provide input signals for future collapse-risk monitoring.

---

## 1. Purpose

The purpose of this document is to clarify the relationship between:

```text
AI Purity Detection Algorithm
```

and:

```text
CollapseMonitor
```

AI Purity Detection asks:

```text
What is the likely origin composition of this source?
Is it natural, synthetic, hybrid, or recursively synthetic?
Are there warning flags?
Is review required?
```

CollapseMonitor asks:

```text
Is the wider AI source ecosystem becoming unstable?
Is natural data declining?
Is synthetic data dominating?
Is recursive synthetic material increasing?
Are models becoming dependent on low-origin or unclear sources?
```

Together, these systems help prevent AI systems from consuming increasingly diluted, recursively generated, or source-unclear material.

---

## 2. Core Distinction

The two systems operate at different scales.

### AI Purity Detection

AI Purity Detection operates at the level of a single assessment.

It evaluates:

- one source
- one Epicenter
- one document
- one record
- one purity assessment object

Its outputs include:

```text
origin_purity_score
ai_generated_ratio
warning_flags
recursive_synthetic_risk
review_routing
downstream_use
```

---

### CollapseMonitor

CollapseMonitor operates at the aggregate level.

It evaluates:

- corpus-level purity
- model-level training data quality
- ecosystem-level synthetic-data growth
- recursive synthetic risk trends
- source-production decline
- reference-health patterns

Its outputs may include:

```text
natural_data_ratio
synthetic_data_ratio
recursive_synthetic_risk_rate
low_confidence_assessment_rate
collapse_risk_score
civilization_health_index
```

---

## 3. Why This Relationship Matters

A single low-purity source does not necessarily indicate collapse.

A single AI-assisted source is not dangerous by itself.

The danger appears when many sources across a corpus begin to show the same pattern:

```text
weak provenance
+
high AI-pattern similarity
+
low structural originality
+
recursive synthetic risk
+
declining natural-data ratio
```

AI Purity Detection provides local measurements.

CollapseMonitor detects whether those local measurements form a systemic pattern.

---

## 4. Data Flow

Recommended flow:

```text
1. Source or Epicenter is registered.
   ↓
2. Purity Detection evaluates the source.
   ↓
3. Purity assessment outputs are stored.
   ↓
4. CollapseMonitor aggregates many assessments.
   ↓
5. Corpus-level and model-level health metrics are calculated.
   ↓
6. Alerts are generated when risk thresholds are exceeded.
   ↓
7. Human / multi-wing / governance review is triggered if needed.
```

---

## 5. Input Signals from Purity Detection

CollapseMonitor may consume the following fields from purity assessments.

### 5.1 `origin_purity_score`

A normalized estimate of source-origin composition.

Aggregate use:

```text
average_origin_purity_score
median_origin_purity_score
low_origin_source_rate
high_origin_source_rate
```

Possible interpretation:

```text
declining average origin purity
↓
source ecology may be weakening
```

---

### 5.2 `ai_generated_ratio`

A normalized estimate of AI-generated or AI-assisted content.

Aggregate use:

```text
average_ai_generated_ratio
high_ai_generated_ratio_rate
hybrid_source_ratio
synthetic_heavy_source_ratio
```

Important:

```text
AI-generated ratio alone does not indicate collapse.
```

The signal becomes more important when combined with:

- weak provenance
- low originality
- recursive synthetic risk
- low confidence
- origin uncertainty

---

### 5.3 `warning_flags`

Warning flags provide risk classification.

Aggregate use:

```text
missing_provenance_rate
high_ai_pattern_similarity_rate
declaration_conflict_rate
low_confidence_score_rate
recursive_synthetic_risk_rate
origin_unclear_rate
review_required_rate
royalty_readiness_blocked_rate
```

These rates help CollapseMonitor detect systemic deterioration.

---

### 5.4 `recursive_synthetic_risk`

This is one of the most important signals for CollapseMonitor.

Recursive synthetic risk indicates that a source may derive from multiple layers of AI-generated or AI-rewritten material.

Aggregate use:

```text
recursive_synthetic_risk_rate
high_recursive_risk_rate
critical_recursive_risk_rate
recursive_risk_growth_rate
```

Possible interpretation:

```text
recursive_synthetic_risk_rate rising
↓
model-collapse risk may be increasing
```

---

### 5.5 `review.required`

Review-required rates can indicate ecosystem uncertainty.

Aggregate use:

```text
review_required_rate
blocking_review_rate
review_recommended_rate
```

Possible interpretation:

```text
review_required_rate rising
↓
source trust is weakening
```

---

### 5.6 `downstream_use`

Downstream-use decisions may serve as health indicators.

Useful aggregate metrics:

```text
training_use_blocked_rate
training_use_conditional_rate
rag_indexing_conditional_rate
royalty_readiness_blocked_rate
collapse_monitoring_include_rate
```

These metrics show whether sources are increasingly unsuitable for high-impact downstream use.

---

## 6. Proposed Aggregate Metrics

CollapseMonitor may compute the following aggregate metrics.

### 6.1 Natural Data Ratio

Estimated ratio of high-origin, human-primary, or structurally original sources.

Possible formula:

```text
natural_data_ratio =
  count(origin_purity_score >= 0.70 and recursive_synthetic_risk not high)
  /
  total_assessed_sources
```

This is a draft metric.

It should not be treated as a perfect measurement of “human content.”

---

### 6.2 Synthetic Data Ratio

Estimated ratio of synthetic-heavy or AI-primary sources.

Possible formula:

```text
synthetic_data_ratio =
  count(ai_generated_ratio >= 0.70 and origin_purity_score < 0.50)
  /
  total_assessed_sources
```

This should be interpreted cautiously.

AI-assisted sources may still contain original structure.

---

### 6.3 Recursive Synthetic Risk Rate

Estimated ratio of sources flagged for recursive synthetic risk.

Possible formula:

```text
recursive_synthetic_risk_rate =
  count("recursive_synthetic_risk" in warning_flags)
  /
  total_assessed_sources
```

This is one of the strongest collapse-risk indicators.

---

### 6.4 Low-Confidence Assessment Rate

Estimated ratio of assessments with low confidence.

Possible formula:

```text
low_confidence_assessment_rate =
  count(origin_purity_score.confidence < 0.60)
  /
  total_assessed_sources
```

A rising low-confidence rate may indicate that provenance infrastructure is insufficient.

---

### 6.5 Missing Provenance Rate

Estimated ratio of sources with insufficient provenance.

Possible formula:

```text
missing_provenance_rate =
  count("missing_provenance" in warning_flags)
  /
  total_assessed_sources
```

This is important because collapse risk increases when the system cannot identify its source layer.

---

### 6.6 Review Required Rate

Estimated ratio of assessments requiring review.

Possible formula:

```text
review_required_rate =
  count(review.required == true)
  /
  total_assessed_sources
```

A high review-required rate does not automatically mean collapse.

It means the ecosystem needs more review capacity.

---

### 6.7 Training Use Blocked Rate

Estimated ratio of sources blocked from training use.

Possible formula:

```text
training_use_blocked_rate =
  count(downstream_use.training_use.allowed == false)
  /
  total_assessed_sources
```

This may indicate that a corpus is becoming less suitable for safe training use.

---

## 7. Draft Collapse Risk Bands

CollapseMonitor may classify risk into bands.

```text
0.00 – 0.19 : stable
0.20 – 0.39 : watch
0.40 – 0.59 : elevated
0.60 – 0.79 : high
0.80 – 1.00 : critical
```

These bands are preliminary and should be calibrated later.

They should not be treated as universal thresholds.

---

## 8. Draft Collapse Risk Score

A future CollapseMonitor may define:

```text
collapse_risk_score
```

Possible draft structure:

```text
collapse_risk_score =
  0.25(recursive_synthetic_risk_rate)
+ 0.20(synthetic_data_ratio)
+ 0.15(missing_provenance_rate)
+ 0.15(low_confidence_assessment_rate)
+ 0.15(review_required_rate)
+ 0.10(training_use_blocked_rate)
```

Then clamp:

```text
collapse_risk_score =
  min(1.0, max(0.0, collapse_risk_score))
```

This is a conceptual draft.

The final formula should be defined in a dedicated CollapseMonitor repository or specification.

---

## 9. Civilization Health Index

A future model may define:

```text
civilization_health_index
```

This could be calculated as the inverse or complement of collapse risk, adjusted by natural data ratio.

Possible draft:

```text
civilization_health_index =
  0.50(natural_data_ratio)
+ 0.25(1 - recursive_synthetic_risk_rate)
+ 0.15(1 - missing_provenance_rate)
+ 0.10(1 - low_confidence_assessment_rate)
```

Interpretation:

```text
higher score
↓
healthier source ecosystem
```

This metric should remain advisory.

It should support review and governance, not replace them.

---

## 10. Alert Conditions

CollapseMonitor may emit alerts when thresholds are exceeded.

### 10.1 Natural Data Decline Alert

```text
natural_data_ratio below threshold
```

Possible alert:

```text
natural_data_ratio_below_threshold
```

Meaning:

```text
The corpus may be losing high-origin or primary-source material.
```

---

### 10.2 Recursive Synthetic Risk Alert

```text
recursive_synthetic_risk_rate above threshold
```

Possible alert:

```text
recursive_synthetic_risk_high
```

Meaning:

```text
The corpus may contain too much AI-generated material derived from prior AI-generated material.
```

---

### 10.3 Provenance Weakness Alert

```text
missing_provenance_rate above threshold
```

Possible alert:

```text
provenance_weakness_high
```

Meaning:

```text
The system cannot reliably trace enough source origins.
```

---

### 10.4 Review Bottleneck Alert

```text
review_required_rate above threshold
```

Possible alert:

```text
review_capacity_required
```

Meaning:

```text
The system needs more human, multi-wing, or governance review capacity.
```

---

### 10.5 Training Safety Alert

```text
training_use_blocked_rate above threshold
```

Possible alert:

```text
training_corpus_quality_risk
```

Meaning:

```text
The corpus may not be suitable for high-confidence training use without review.
```

---

## 11. Relationship to ModelProfile

In the broader Epicenter Preservation OS, `ModelProfile` may contain fields such as:

```text
training_data_purity
collapse_risk_score
epicenter_dependency_index
```

Purity Detection can supply source-level measurements.

CollapseMonitor can aggregate them into model-level profile signals.

Example flow:

```text
Purity Assessments
↓
Aggregate Metrics
↓
CollapseMonitor
↓
ModelProfile.training_data_purity
↓
ModelProfile.collapse_risk_score
```

This creates a bridge between source-level evidence and model-level risk.

---

## 12. Relationship to RAG Systems

RAG systems may use CollapseMonitor outputs to evaluate corpus health.

Possible uses:

- prioritize high-origin sources
- flag low-confidence sources
- reduce recursive synthetic ingestion
- require provenance metadata
- separate primary sources from summaries
- avoid over-indexing derivative material
- report corpus-health metrics

Recommended RAG policy:

```text
Do not remove AI-assisted sources by default.
Separate them, label them, and monitor their aggregate ratio.
```

---

## 13. Relationship to Royalty Readiness

CollapseMonitor may also observe value-circulation risk.

If many sources are blocked from royalty readiness because of unclear origin or recursive synthetic risk, this may indicate that the ecosystem lacks sufficient traceability.

Possible aggregate metrics:

```text
royalty_readiness_blocked_rate
not_ready_rate
disputed_rate
review_ready_rate
```

Possible interpretation:

```text
royalty_readiness_blocked_rate rising
↓
source-to-value circulation pathway may be weakening
```

CollapseMonitor can therefore help identify where Royalty OS needs better trace, provenance, or review infrastructure.

---

## 14. Relationship to Consciousness Circle

If Consciousness Circle is used, CollapseMonitor may eventually observe meaning-level degradation in addition to data-level degradation.

Possible meaning-level metrics:

- shallow-resonance rate
- low-initial-friction rate
- generic-response-pattern rate
- boundary-instability rate
- low-meaning-depth rate

Combined monitoring:

```text
data collapse
+
meaning collapse
```

This distinction matters.

AI civilization may degrade in two ways:

```text
The source becomes synthetic.
The meaning becomes shallow.
```

Purity Detection supports the first monitoring path.

Consciousness Circle may support the second.

---

## 15. Non-Goals

This document does not attempt to:

- define final CollapseMonitor thresholds
- provide production-ready health scoring
- prove model collapse mathematically
- classify all AI-assisted content as harmful
- ban synthetic data
- determine legal authorship
- determine royalty allocation
- replace human review
- define universal corpus health

This is a relationship document and draft bridge model.

---

## 16. Anti-Automation Principle

CollapseMonitor should not automatically delete, block, or punish sources.

Unsafe pattern:

```text
collapse_risk_score high
↓
automatic removal
```

Safer pattern:

```text
collapse_risk_score high
↓
alert
↓
review
↓
policy decision
↓
documented action
```

The system should support governance, not replace it.

---

## 17. Design Principle

The central design principle is:

```text
Local purity signals become useful only when aggregated carefully.
```

A single assessment can be wrong.

A pattern across many assessments may reveal ecosystem risk.

Therefore:

```text
Purity Detection measures drops of water.
CollapseMonitor watches the river.
```

---

## 18. Summary

AI Purity Detection Algorithm v0.2 supports CollapseMonitor by providing source-level signals such as:

- `origin_purity_score`
- `ai_generated_ratio`
- `warning_flags`
- `recursive_synthetic_risk`
- confidence values
- review-required status
- downstream-use decisions

CollapseMonitor aggregates these signals to monitor ecosystem-level health.

The relationship is:

```text
Purity Detection
↓
Aggregate Metrics
↓
CollapseMonitor
↓
Model / Corpus / Civilization Health Signals
```

In short:

```text
Purity protects the source.
CollapseMonitor protects the ecosystem.
```

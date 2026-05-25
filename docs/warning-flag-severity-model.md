# Warning Flag Severity Model v0.2 Draft

## Status

Draft specification.

This document defines the proposed warning-flag severity model for **Purity Detection Algorithm v0.2**.

Version `v0.1.1` introduced `warning_flags` as part of the purity assessment output.

Version `v0.2` expands those flags into a review-aware severity model.

The goal is to clarify:

- how warning flags should be interpreted
- which flags require review
- which flags affect downstream use
- which flags may block royalty-readiness transition
- how warning flags relate to confidence, recursive synthetic risk, and provenance uncertainty

This document does not define legal authorship, copyright ownership, or final royalty allocation.

---

## 1. Purpose

The purpose of the Warning Flag Severity Model is to prevent purity assessment outputs from being overinterpreted.

A warning flag should not automatically mean that an Epicenter is invalid.

A warning flag means:

```text
Something requires attention.
```

Different flags require different levels of response.

Some flags are informational.

Some suggest review.

Some require review.

Some block downstream use until resolved.

The v0.2 model makes these differences explicit.

---

## 2. Core Principle

Warning flags are not punishments.

They are routing signals.

```text
warning_flag
≠
guilt

warning_flag
≠
low value

warning_flag
≠
copyright violation

warning_flag
=
review / caution / routing signal
```

The system should avoid automatic exclusion unless a blocking condition is clearly defined.

---

## 3. Severity Levels

The v0.2 model defines four severity levels.

```text
info
warning
review_required
blocking
```

---

### 3.1 info

An `info` flag records useful context but does not require review by itself.

Example:

```text
ai_assistance_declared
```

Meaning:

```text
The creator declared AI assistance.
This is useful metadata, not a negative signal.
```

---

### 3.2 warning

A `warning` flag indicates a possible issue that should be noted.

It may trigger review if combined with other flags or low confidence.

Example:

```text
high_ai_pattern_similarity
```

Meaning:

```text
The content resembles known AI-generated patterns.
This does not prove synthetic origin.
```

---

### 3.3 review_required

A `review_required` flag means the assessment should not proceed to high-impact downstream decisions without review.

Example:

```text
declaration_conflict
```

Meaning:

```text
The creator declaration conflicts with detected signals.
Human or multi-wing review is required.
```

---

### 3.4 blocking

A `blocking` flag prevents a specific downstream transition until resolved.

Example:

```text
royalty_readiness_blocked
```

Meaning:

```text
The assessment may not proceed toward royalty-readiness status until the issue is reviewed or cleared.
```

Blocking does not necessarily mean the Epicenter is invalid.

It means the system must stop automatic progression.

---

## 4. Standard Warning Flags

The following warning flags are defined in v0.2 draft.

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

Future versions may add additional flags.

---

## 5. Default Severity Mapping

Suggested default mapping:

```text
missing_provenance              → review_required
high_ai_pattern_similarity      → warning
declaration_conflict            → review_required
low_confidence_score            → review_required
recursive_synthetic_risk        → review_required / blocking
origin_unclear                  → review_required
review_required                 → review_required
review_recommended              → warning
royalty_readiness_blocked       → blocking
```

Context may raise or lower severity.

For example:

```text
high_ai_pattern_similarity
+
low_confidence_score
+
missing_provenance
=
review_required
```

---

## 6. Flag Definitions

## 6.1 missing_provenance

### Meaning

The Epicenter lacks sufficient origin evidence.

This may include missing or weak:

- publication timestamp
- platform metadata
- archive record
- revision history
- creator declaration
- source URL
- traceable provenance chain

### Default Severity

```text
review_required
```

### Recommended Action

- request additional provenance
- inspect platform metadata
- check archive records
- review revision lineage
- defer royalty-readiness transition

### Downstream Impact

```text
RAG indexing: conditional
training use: conditional or blocked
royalty readiness: not_ready or review_required
collapse monitoring: include as low-confidence signal
```

---

## 6.2 high_ai_pattern_similarity

### Meaning

The Epicenter shows strong similarity to known AI-generated or templated structures.

This may include:

- generic explanatory symmetry
- repetitive rhetorical scaffolding
- shallow summary structure
- template-like paragraph progression
- low specificity
- common AI conclusion patterns

### Default Severity

```text
warning
```

### Recommended Action

- compare structure fingerprint
- check provenance
- inspect structural originality
- combine with confidence and recursive-risk signals

### Downstream Impact

```text
RAG indexing: allowed with caution
training use: conditional
royalty readiness: review recommended
collapse monitoring: include
```

### Notes

This flag must not be treated as proof of AI generation.

Human writing can resemble AI patterns.

AI-assisted writing can still contain strong original structure.

---

## 6.3 declaration_conflict

### Meaning

The creator’s declaration conflicts with detected signals.

Examples:

```text
creator declares no AI assistance
↓
high AI-pattern risk and weak provenance detected
```

or:

```text
creator declares full AI generation
↓
strong provenance and distinctive human revision lineage detected
```

### Default Severity

```text
review_required
```

### Recommended Action

- request clarification
- inspect revision history
- compare structural fingerprint
- route to human or multi-wing review

### Downstream Impact

```text
RAG indexing: conditional
training use: conditional
royalty readiness: not_ready until reviewed
collapse monitoring: include as uncertain signal
```

---

## 6.4 low_confidence_score

### Meaning

The assessment has insufficient signal quality.

This may occur when:

- metadata is missing
- signal coverage is weak
- model confidence is low
- evidence is contradictory
- scoring inputs are incomplete

### Default Severity

```text
review_required
```

### Recommended Action

- collect additional evidence
- rerun assessment
- request human review
- avoid final downstream decisions

### Downstream Impact

```text
RAG indexing: conditional
training use: conditional or blocked
royalty readiness: not_ready
collapse monitoring: include as low-confidence metric
```

---

## 6.5 recursive_synthetic_risk

### Meaning

The Epicenter may derive from multiple layers of AI-generated or AI-rewritten content.

Potential indicators:

- repeated summarization structure
- weak primary-source trail
- derivative phrasing
- shallow citation chain
- high AI-pattern similarity
- low structural originality
- no firsthand observation
- evidence of AI-to-AI rewriting loops

### Default Severity

```text
review_required
```

May become:

```text
blocking
```

when risk is high or critical.

### Recommended Action

- inspect source chain
- compare against primary sources
- evaluate recursive-risk score
- route to review
- block royalty-readiness transition if risk is high

### Downstream Impact

```text
RAG indexing: conditional or blocked
training use: blocked if high risk
royalty readiness: blocked if high risk
collapse monitoring: include as high-priority signal
```

---

## 6.6 origin_unclear

### Meaning

The system cannot identify the likely source origin.

This may happen when:

- no Epicenter can be verified
- the text is widely duplicated
- attribution is missing
- multiple possible sources exist
- the content appears heavily recombined

### Default Severity

```text
review_required
```

### Recommended Action

- run lineage analysis
- inspect timestamp ordering
- compare source candidates
- request creator clarification
- defer downstream decisions

### Downstream Impact

```text
RAG indexing: conditional
training use: conditional or blocked
royalty readiness: not_ready
collapse monitoring: include as uncertain source
```

---

## 6.7 review_required

### Meaning

The assessment cannot safely proceed without review.

This flag may be emitted directly or derived from other flags.

### Default Severity

```text
review_required
```

### Recommended Action

Route to one of:

- human review
- domain expert review
- multi-wing review
- governance review
- dispute registry process

### Downstream Impact

```text
RAG indexing: conditional
training use: conditional
royalty readiness: not_ready until reviewed
collapse monitoring: include
```

---

## 6.8 review_recommended

### Meaning

The assessment may proceed, but review is recommended before high-impact use.

### Default Severity

```text
warning
```

### Recommended Action

- optional human review
- inspect high-risk signals
- verify downstream use permissions

### Downstream Impact

```text
RAG indexing: allowed
training use: conditional
royalty readiness: review_ready
collapse monitoring: include
```

---

## 6.9 royalty_readiness_blocked

### Meaning

The assessment must not proceed toward royalty-readiness transition.

This may be caused by:

- unresolved origin dispute
- high recursive synthetic risk
- missing provenance
- declaration conflict
- low confidence
- insufficient trace evidence

### Default Severity

```text
blocking
```

### Recommended Action

- block automatic transition
- require review
- request additional evidence
- resolve dispute or provenance issue
- re-run assessment after update

### Downstream Impact

```text
RAG indexing: may still be allowed depending on policy
training use: conditional or blocked
royalty readiness: blocked
collapse monitoring: include
```

---

## 7. Severity Escalation Rules

Severity may escalate when multiple flags appear together.

### 7.1 Example Escalation

```text
high_ai_pattern_similarity
+
missing_provenance
=
review_required
```

```text
recursive_synthetic_risk
+
low_confidence_score
=
review_required or blocking
```

```text
declaration_conflict
+
royalty_readiness request
=
blocking
```

```text
origin_unclear
+
recursive_synthetic_risk
+
training_use requested
=
blocking
```

---

## 8. Severity Downgrade Rules

Severity may be downgraded when additional evidence resolves uncertainty.

Examples:

```text
missing_provenance
+
verified archive record
=
warning or resolved
```

```text
high_ai_pattern_similarity
+
strong structural originality
+
clear creator declaration
=
warning only
```

```text
declaration_conflict
+
creator clarification
+
revision history
=
resolved or warning
```

Resolved flags may be preserved in audit history rather than deleted.

---

## 9. Proposed Flag Detail Object

Version `v0.2` may extend the schema with a detailed warning flag object.

Example:

```yaml
warning_flag_details:
  - flag: "missing_provenance"
    severity: "review_required"
    status: "open"
    explanation: "Publication timestamp exists, but revision lineage is unavailable."
    recommended_action: "Request additional provenance or archive evidence."
    downstream_impact:
      rag_indexing: "conditional"
      training_use: "conditional"
      royalty_readiness: "not_ready"
      collapse_monitoring: "include"
```

---

## 10. Suggested Schema Shape

Future schema extension:

```json
{
  "warning_flag_details": [
    {
      "flag": "missing_provenance",
      "severity": "review_required",
      "status": "open",
      "explanation": "string",
      "recommended_action": "string",
      "downstream_impact": {
        "rag_indexing": "allowed | conditional | blocked",
        "training_use": "allowed | conditional | blocked",
        "royalty_readiness": "ready | review_ready | not_ready | blocked | disputed",
        "collapse_monitoring": "include | exclude"
      }
    }
  ]
}
```

---

## 11. Flag Status

Each warning flag may have a status.

Suggested statuses:

```text
open
under_review
resolved
dismissed
superseded
```

### 11.1 open

The issue has been detected and remains unresolved.

### 11.2 under_review

The issue is being reviewed.

### 11.3 resolved

The issue has been addressed by additional evidence or review.

### 11.4 dismissed

The issue was judged not relevant after review.

### 11.5 superseded

The issue has been replaced by a newer assessment or flag.

---

## 12. Relationship to Review Routing

Warning severity should directly inform review routing.

Suggested mapping:

```text
info
↓
no review required

warning
↓
review optional or recommended

review_required
↓
review required before high-impact use

blocking
↓
automatic downstream transition blocked
```

Review modes:

```text
none
recommended
required
blocking_review
```

---

## 13. Relationship to Scoring Weighting Model

Warning flags should not always reduce the score directly.

Instead:

- scoring model estimates origin composition
- warning flags explain caution areas
- severity model determines routing
- review model determines next action

```text
score
↓
confidence
↓
warning severity
↓
review routing
↓
downstream use
```

This separation prevents the score from becoming an opaque punishment system.

---

## 14. Relationship to CollapseMonitor

CollapseMonitor may aggregate warning flags across many Epicenters.

Useful aggregate metrics:

- missing provenance rate
- high AI-pattern similarity rate
- recursive synthetic risk rate
- low-confidence assessment rate
- origin-unclear rate
- royalty-readiness-blocked rate
- review-required rate

These metrics can help detect ecosystem-level degradation.

Example:

```text
recursive_synthetic_risk rate rises
↓
natural-data ratio may be declining
↓
collapse risk may increase
```

---

## 15. Relationship to Royalty Readiness

Royalty readiness should be blocked when high-severity flags remain unresolved.

Suggested behavior:

```text
no blocking flags
+
sufficient trace evidence
+
acceptable confidence
=
review_ready

blocking flag present
=
blocked

review_required flag present
=
not_ready until reviewed

dispute present
=
disputed
```

This prevents purity assessment from becoming automatic payment logic.

---

## 16. Example Flag Set

Example:

```yaml
warning_flags:
  - "missing_provenance"
  - "high_ai_pattern_similarity"
  - "review_required"

warning_flag_details:
  - flag: "missing_provenance"
    severity: "review_required"
    status: "open"
    explanation: "The source has a publication timestamp but no revision lineage."
    recommended_action: "Request additional provenance evidence."

  - flag: "high_ai_pattern_similarity"
    severity: "warning"
    status: "open"
    explanation: "The structure resembles known AI-generated explanatory patterns."
    recommended_action: "Compare structure fingerprint and inspect originality."

  - flag: "review_required"
    severity: "review_required"
    status: "open"
    explanation: "Multiple uncertainty signals are present."
    recommended_action: "Route to human or multi-wing review."
```

---

## 17. Non-Goals

This model does not attempt to:

- prove legal authorship
- determine copyright ownership
- automatically reject AI-assisted content
- automatically assign royalties
- punish synthetic content
- replace human review
- define universal originality
- make moral judgments about creators

It is a routing and review-support layer.

---

## 18. Design Philosophy

A good warning system should not shout all the time.

If every flag is treated as a crisis, the system becomes useless.

The purpose of severity classification is to distinguish:

```text
context
caution
review need
hard stop
```

In short:

```text
Warning flags are traffic signals.
They are not court verdicts.
```

---

## 19. Summary

Version `v0.2` should treat warning flags as structured review signals.

The proposed model introduces:

- severity levels
- escalation rules
- downgrade rules
- flag status
- downstream impact
- review routing
- relationship to scoring
- relationship to CollapseMonitor
- relationship to Royalty Readiness

The core principle remains:

```text
A warning flag does not invalidate an Epicenter.
It tells the system what kind of attention is needed.
```

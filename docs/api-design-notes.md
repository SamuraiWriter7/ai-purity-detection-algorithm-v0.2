# API Design Notes

## Status

Draft design notes.

This document defines preliminary API design notes for **AI Purity Detection Algorithm v0.2**.

The goal is to describe how purity assessment, warning flags, recursive synthetic risk detection, review routing, and downstream-use guidance may be exposed through an API.

This document is not a production API specification.

It is a design bridge for future implementation.

---

## 1. Purpose

The purpose of the API layer is to make the purity assessment process accessible to external systems.

Potential users include:

- RAG systems
- data governance systems
- source-preservation systems
- model-collapse monitoring systems
- royalty-readiness systems
- audit dashboards
- multi-wing review systems
- platform moderation or provenance tools

The API should allow systems to:

```text
submit source evidence
↓
receive a purity assessment
↓
inspect warning flags
↓
route uncertain cases to review
↓
support downstream decisions without automating final judgment
```

---

## 2. Core API Principle

The API must not present purity scores as final truth.

```text
API output
≠
legal decision
≠
copyright decision
≠
royalty decision
≠
moral judgment
```

The API provides:

```text
assessment
risk signals
warnings
review recommendations
downstream-use guidance
```

The API does not provide:

```text
final ownership
final payment
final authorship
final guilt
final value judgment
```

---

## 3. Core Objects

The API should revolve around the following core objects.

```text
SourceInput
PurityAssessment
WarningFlagDetail
ReviewRouting
DownstreamUse
AssessmentBatch
```

---

## 4. SourceInput

`SourceInput` represents the data submitted for purity assessment.

Example:

```yaml
source_input:
  source_id: "source_001"
  source_type: "article"
  title: "Example Source"
  language: "ja-JP"
  content_hash: "sha256:..."
  source_url: "https://example.com/source"
  created_at: "2026-05-25T00:00:00Z"
  submitted_at: "2026-05-25T00:10:00Z"

  metadata:
    author_id: "creator_001"
    platform: "note"
    declared_ai_assistance: "ai_assisted"
    declaration_notes: "AI was used for drafting and formatting support."

  evidence:
    publication_timestamp_available: true
    revision_history_available: true
    archive_record_available: false
    citation_list_available: true
    structure_fingerprint_available: true
```

---

## 5. PurityAssessment

`PurityAssessment` is the main API output.

It should map to the existing schema structure.

Core fields:

```text
id
source_id
assessed_at
method
version
signals
outputs
review
downstream_use
warning_flag_details
review_routing
```

Example:

```yaml
purity_assessment:
  id: "purity_assessment_001"
  source_id: "source_001"
  assessed_at: "2026-05-25T00:15:00Z"
  method: "hybrid"
  version: "0.2.0"

  outputs:
    origin_purity_score:
      value: 0.80
      confidence: 0.74
      interpretation: "likely_human_primary_or_structurally_original"

    ai_generated_ratio:
      value: 0.28
      confidence: 0.66
      interpretation: "ai_assisted_but_not_ai_primary"

    warning_flags:
      - "review_recommended"
```

---

## 6. Recommended Endpoints

The following endpoints are proposed for future implementation.

```text
POST /purity/assess
GET  /purity/assessments/{assessment_id}
POST /purity/assess/batch
GET  /purity/sources/{source_id}/latest
GET  /purity/sources/{source_id}/history
POST /purity/review-route
GET  /purity/health
```

---

## 7. POST /purity/assess

### Purpose

Submit a single source for purity assessment.

### Request

```json
{
  "source_input": {
    "source_id": "source_001",
    "source_type": "article",
    "title": "Example Source",
    "language": "ja-JP",
    "content_hash": "sha256:example",
    "source_url": "https://example.com/source",
    "created_at": "2026-05-25T00:00:00Z",
    "metadata": {
      "author_id": "creator_001",
      "platform": "note",
      "declared_ai_assistance": "ai_assisted",
      "declaration_notes": "AI was used for drafting and formatting support."
    },
    "evidence": {
      "publication_timestamp_available": true,
      "revision_history_available": true,
      "archive_record_available": false,
      "citation_list_available": true,
      "structure_fingerprint_available": true
    }
  }
}
```

### Response

```json
{
  "purity_assessment": {
    "id": "purity_assessment_001",
    "source_id": "source_001",
    "assessed_at": "2026-05-25T00:15:00Z",
    "method": "hybrid",
    "version": "0.2.0",
    "outputs": {
      "origin_purity_score": {
        "value": 0.8,
        "confidence": 0.74,
        "interpretation": "likely_human_primary_or_structurally_original"
      },
      "ai_generated_ratio": {
        "value": 0.28,
        "confidence": 0.66,
        "interpretation": "ai_assisted_but_not_ai_primary"
      },
      "warning_flags": ["review_recommended"]
    },
    "review": {
      "required": false,
      "recommended": true,
      "reason": "AI assistance is likely, but provenance and structural originality are strong."
    }
  }
}
```

---

## 8. GET /purity/assessments/{assessment_id}

### Purpose

Retrieve a previously generated purity assessment.

### Example

```text
GET /purity/assessments/purity_assessment_001
```

### Response

```json
{
  "purity_assessment": {
    "id": "purity_assessment_001",
    "source_id": "source_001",
    "assessed_at": "2026-05-25T00:15:00Z",
    "method": "hybrid",
    "version": "0.2.0"
  }
}
```

---

## 9. POST /purity/assess/batch

### Purpose

Submit multiple sources for assessment.

This endpoint is useful for:

- RAG corpus audits
- dataset preparation
- platform-wide provenance review
- model-collapse monitoring input
- source-health dashboards

### Request

```json
{
  "batch_id": "batch_001",
  "sources": [
    {
      "source_id": "source_001",
      "source_type": "article",
      "content_hash": "sha256:example_001"
    },
    {
      "source_id": "source_002",
      "source_type": "note",
      "content_hash": "sha256:example_002"
    }
  ]
}
```

### Response

```json
{
  "batch_id": "batch_001",
  "status": "accepted",
  "assessment_count": 2,
  "results_endpoint": "/purity/batches/batch_001/results"
}
```

---

## 10. GET /purity/sources/{source_id}/latest

### Purpose

Retrieve the latest assessment for a source.

This is useful when downstream systems need current status before using a source.

Example:

```text
GET /purity/sources/source_001/latest
```

Possible response:

```json
{
  "source_id": "source_001",
  "latest_assessment_id": "purity_assessment_001",
  "origin_purity_score": {
    "value": 0.8,
    "confidence": 0.74
  },
  "warning_flags": ["review_recommended"],
  "review": {
    "required": false,
    "recommended": true
  },
  "downstream_use": {
    "rag_indexing": {
      "allowed": true
    },
    "training_use": {
      "allowed": "conditional"
    },
    "royalty_readiness": {
      "status": "review_ready"
    }
  }
}
```

---

## 11. GET /purity/sources/{source_id}/history

### Purpose

Retrieve assessment history for a source.

This supports:

- auditability
- review history
- dispute handling
- version tracking
- source evolution analysis

Example:

```json
{
  "source_id": "source_001",
  "assessments": [
    {
      "assessment_id": "purity_assessment_001",
      "assessed_at": "2026-05-25T00:15:00Z",
      "origin_purity_score": 0.80,
      "status": "review_ready"
    },
    {
      "assessment_id": "purity_assessment_002",
      "assessed_at": "2026-06-01T00:15:00Z",
      "origin_purity_score": 0.82,
      "status": "review_ready"
    }
  ]
}
```

---

## 12. POST /purity/review-route

### Purpose

Determine review routing from an existing assessment.

This endpoint should not decide final outcome.

It only determines what kind of review is needed.

### Request

```json
{
  "assessment_id": "purity_assessment_recursive_synthetic_risk_001",
  "requested_downstream_use": "training_use"
}
```

### Response

```json
{
  "assessment_id": "purity_assessment_recursive_synthetic_risk_001",
  "review_routing": {
    "mode": "blocking_review",
    "reviewer_type": "multi_wing",
    "reason": "Recursive synthetic risk and missing provenance block training use."
  },
  "next_action": {
    "type": "review_required",
    "priority": "high"
  }
}
```

---

## 13. GET /purity/health

### Purpose

Return aggregate purity-health signals.

This endpoint prepares data for CollapseMonitor.

It should not replace a full CollapseMonitor implementation.

### Example Response

```json
{
  "scope": "corpus_001",
  "assessed_source_count": 1200,
  "metrics": {
    "average_origin_purity_score": 0.68,
    "average_ai_generated_ratio": 0.37,
    "recursive_synthetic_risk_rate": 0.12,
    "missing_provenance_rate": 0.18,
    "low_confidence_assessment_rate": 0.21,
    "review_required_rate": 0.25,
    "training_use_blocked_rate": 0.09
  },
  "alerts": [
    {
      "type": "review_capacity_required",
      "severity": "warning",
      "reason": "Review-required rate is elevated."
    }
  ]
}
```

---

## 14. API Output Safety Rules

API outputs should include caution metadata.

Recommended fields:

```yaml
safety_notice:
  final_judgment: false
  legal_authorship_determined: false
  royalty_allocation_determined: false
  requires_review_for_high_impact_use: true
```

The API should make clear that output is:

```text
assessment
not verdict
```

---

## 15. Error Handling

Recommended error types:

```text
invalid_source_input
missing_required_metadata
unsupported_source_type
invalid_datetime_format
schema_validation_failed
assessment_not_found
insufficient_evidence
review_required
downstream_use_blocked
```

Example:

```json
{
  "error": {
    "type": "insufficient_evidence",
    "message": "The submitted source lacks enough provenance evidence for a reliable assessment.",
    "recommended_action": "Provide publication timestamp, revision history, or archive evidence."
  }
}
```

---

## 16. Status Codes

Suggested status codes:

```text
200 OK
201 Created
202 Accepted
400 Bad Request
404 Not Found
409 Conflict
422 Unprocessable Entity
429 Too Many Requests
500 Internal Server Error
```

Possible mappings:

```text
400 = malformed request
404 = assessment not found
409 = conflicting source or assessment state
422 = valid JSON but insufficient or invalid assessment data
```

---

## 17. Authentication and Access Control

Future implementation should define access rules.

Possible roles:

```text
creator
reviewer
platform_operator
model_provider
governance_auditor
public_reader
```

Suggested permissions:

| Role | Submit | Read Own | Read Aggregate | Review | Export |
|---|---:|---:|---:|---:|---:|
| creator | yes | yes | no | no | yes |
| reviewer | yes | yes | limited | yes | yes |
| platform_operator | yes | yes | yes | yes | yes |
| model_provider | yes | limited | yes | limited | yes |
| governance_auditor | no | yes | yes | yes | yes |
| public_reader | no | limited | limited | no | no |

---

## 18. Privacy Considerations

Purity assessment may involve sensitive metadata.

The API should avoid exposing:

- private drafts
- private revision history
- unpublished source content
- personal identity details beyond necessary creator identifiers
- confidential platform metadata
- proprietary model traces

Recommended approach:

```text
store hashes and references where possible
expose minimal metadata
separate public assessment from private audit evidence
```

---

## 19. Relationship to Trace Protocol

The API should be able to consume Trace Protocol records.

Potential fields:

```text
trace_id
reference_event_id
usage_type
model_id
context_window_hash
reference_weight
timestamp
```

Trace data may strengthen royalty-readiness review.

Suggested flow:

```text
Trace Event
↓
Purity Assessment
↓
Review Routing
↓
Royalty Readiness
```

---

## 20. Relationship to CollapseMonitor

The API may expose aggregate endpoints for CollapseMonitor.

Suggested bridge:

```text
GET /purity/health
↓
CollapseMonitor
↓
corpus health / model health / civilization health
```

However, this API should not fully define CollapseMonitor.

It should only provide source-level and aggregate purity signals.

---

## 21. Relationship to Royalty Readiness

The API may provide downstream-use status.

Important:

```text
royalty_readiness.status
≠
payment approval
```

Possible statuses:

```text
not_ready
review_ready
ready
blocked
disputed
```

Recommended behavior:

```text
blocked
↓
do not proceed to allocation review

review_ready
↓
human or multi-wing review may begin

ready
↓
allocation review may proceed if trace evidence exists
```

---

## 22. Relationship to Consciousness Circle

If Consciousness Circle integration is used, the API may include optional references.

Example:

```json
{
  "consciousness_circle_reference": {
    "circle_id": "cc_assessment_001",
    "meaning_depth_score": 0.82,
    "initial_friction_score": 0.74,
    "resonance_quality": "strong"
  }
}
```

This should remain optional.

Purity assessment must remain usable without Consciousness Circle.

---

## 23. Non-Goals

This API design does not attempt to:

- provide production-ready endpoint contracts
- define authentication implementation
- define legal compliance requirements
- determine copyright ownership
- assign royalties
- prove authorship
- perfectly detect AI-generated content
- replace human review
- replace dispute resolution
- claim metaphysical consciousness

---

## 24. Design Principle

The central API design principle is:

```text
Expose evidence.
Expose uncertainty.
Expose review routing.
Do not expose premature judgment as final truth.
```

The API should be useful precisely because it can say:

```text
This looks strong.
This looks uncertain.
This needs review.
This must not proceed automatically.
```

---

## 25. Summary

The API layer should make AI Purity Detection Algorithm v0.2 usable by external systems.

It should expose:

- source input
- purity assessment
- origin-purity score
- AI-generated ratio
- warning flags
- recursive synthetic risk
- review routing
- downstream-use guidance
- aggregate health signals

The API should not make final legal, financial, or moral decisions.

In short:

```text
The API should turn purity assessment into an auditable service,
not an automatic judge.
```

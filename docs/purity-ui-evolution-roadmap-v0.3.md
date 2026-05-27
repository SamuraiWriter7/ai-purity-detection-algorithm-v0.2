# Purity UI Evolution Roadmap v0.3

## 1. Purpose

This document defines a future evolution roadmap for Purity UI beyond the current platform integration mock.

The current `docs/ui-mock-note-integration.md` shows how Purity metadata, Consciousness Circle metadata, Trace logs, Royalty OS previews, and Creator Controls may appear in a note-style article interface.

This roadmap explores the next stage:

> From Purity as a scoring display  
> to Purity as a creator-controlled civilization OS interface.

This document is not a final specification.  
It is a roadmap for a possible v0.3 design direction.

---

## 2. Background

AI Purity Detection Algorithm v0.2 focuses on estimating origin purity, AI-generated ratio, warning flags, recursive synthetic risk, and review routing.

Version 0.2.1 adds a platform UI integration reference.

However, once Purity appears in a platform interface, several deeper design questions emerge:

- How should the source epicenter be visualized?
- How can pre-verbal or incomplete friction be preserved?
- How can creators define granular disclosure boundaries?
- How should evolving meaning structures be versioned?
- How can AI inference be explicitly restricted?
- How can Trace and Royalty OS flows become visible without becoming final payment claims?
- How can multiple epicenters form a network of resonance?

These questions suggest that Purity UI must evolve from a display layer into a control layer.

---

## 3. Core Thesis

Purity UI should not merely show whether a work appears human-origin, hybrid, or synthetic-dominant.

A mature Purity UI should help preserve and control:

```text
epicenter
friction
question
meaning structure
visibility boundaries
AI inference permissions
trace visibility
royalty-readiness preview
epicenter network relationships
```

In short:

```text
Purity UI v0.2.1 = display mock
Purity UI v0.3   = creator-controlled origin interface
```

---

## 4. Roadmap Overview

The proposed v0.3 evolution consists of seven layers:

| Layer | Purpose |
|---|---|
| Epicenter Layer | Visualize the source structure of a work |
| Proto-Friction Layer | Preserve pre-verbal or incomplete friction |
| Visibility Protocol | Define granular disclosure and access levels |
| Circle Versioning | Track evolution of meaning structures |
| No-Inference Layer | Prevent unauthorized AI interpretation |
| Royalty OS Visibility | Show trace-to-allocation readiness flow |
| Epicenter Network | Visualize resonance between source structures |

Together, these layers turn Purity UI into a platform-level control interface.

---

## 5. Epicenter Layer

### 5.1 Problem

The current Purity UI can show a score such as:

```text
Purity: 87 / High Natural
```

However, a score alone does not show the structure of the source epicenter.

It does not show:

- what friction generated the work
- what question organized the work
- what meaning structure was formed
- what boundaries the creator defined

### 5.2 Proposed Direction

Introduce an Epicenter Layer with three visible or semi-visible levels:

```text
Friction Layer
↓
Question Layer
↓
Meaning Layer
```

### 5.3 Friction Layer

The Friction Layer records the initial contact point between the creator and reality.

Possible friction types:

```text
emotion
body_sensation
social_conflict
cognitive_dissonance
unresolved_question
field_observation
creative_pressure
ethical_discomfort
```

### 5.4 Question Layer

The Question Layer records the core question and related sub-questions.

Possible fields:

```text
core_question
sub_questions
question_origin
question_scope
question_status
```

### 5.5 Meaning Layer

The Meaning Layer records how the creator defines the meaning boundary.

Possible fields:

```text
meaning_claim
interpretation_boundary
non_public_context
creator_defined_scope
meaning_integrity_notes
```

### 5.6 UI Direction

The Epicenter Layer may be represented as a three-ring structure:

```text
Outer Ring  : Friction
Middle Ring : Question
Inner Ring  : Meaning
```

This may be described as an Enso-like structure, or Consciousness Circle view.

---

## 6. Proto-Friction Layer

### 6.1 Problem

Not all meaningful friction is immediately verbalized.

Some creators may have:

- discomfort without words
- unfinished intuition
- bodily tension
- fragmented notes
- silence
- vague resistance
- pre-conceptual awareness

If Purity UI only accepts polished text, it may exclude important early-stage human-origin signals.

### 6.2 Proposed Direction

Introduce a Proto-Friction Layer for incomplete or pre-verbal signals.

Possible UI controls:

```text
[ ] I cannot verbalize this yet
[ ] Save as unresolved friction
[ ] Do not allow AI completion
[ ] Allow private creator-only note
[ ] Allow later conversion into core question
```

### 6.3 Possible Field

```yaml
proto_friction:
  status: unresolved
  input_type: fragment
  ai_completion_allowed: false
  visibility: private
  creator_note: "A vague discomfort that has not yet become a question."
```

### 6.4 Design Principle

The system should not force creators to prematurely explain their friction.

Unfinished friction may itself be a source signal.

---

## 7. Visibility Protocol

### 7.1 Problem

A simple public/private switch is not enough for AI-mediated platforms.

Creators may want to expose some parts of a work to readers, some parts to AI systems, and some parts to no one.

### 7.2 Proposed Visibility Levels

The following five-level visibility model is proposed:

| Level | Label | Description |
|---|---|---|
| 1 | Public | Visible to readers and AI systems |
| 2 | AI-Readable | Hidden from public UI, readable by authorized AI systems |
| 3 | Summary-Only | Only a summary may be used by AI systems |
| 4 | Friction-Only | Only the friction category or abstract signal may be disclosed |
| 5 | Private | Not visible to readers or AI systems |

### 7.3 Example

```yaml
visibility_protocol:
  core_question: public
  initial_friction: friction_only
  deep_layer: private
  rotation_dynamics: summary_only
  trace_log: public
  royalty_preview: public
```

### 7.4 Design Principle

Creator-defined visibility should be authoritative.

AI systems may infer, classify, or summarize only within the permitted boundary.

---

## 8. Circle Versioning

### 8.1 Problem

Meaning structures evolve.

A creator's original friction, question, and interpretation may change over time.

Without versioning, platforms may freeze a creator's early thought into a static identity.

### 8.2 Proposed Direction

Introduce Circle Versioning.

Example version sequence:

```text
circle_v0.1
circle_v0.2
circle_v0.3
```

Each version may track:

- friction change
- question refinement
- meaning boundary shift
- disclosure change
- AI-use permission change
- relationship to previous version

### 8.3 Example

```yaml
circle_version:
  id: circle_v0.2
  previous_version: circle_v0.1
  change_type:
    - question_refinement
    - visibility_update
  summary: "The original emotional friction evolved into a design question."
```

### 8.4 UI Direction

The platform may show:

```text
Version History
- v0.1: Initial friction recorded
- v0.2: Core question refined
- v0.3: Deep Layer moved to private
```

### 8.5 Design Principle

A creator's meaning structure should be allowed to evolve.

Versioning prevents false permanence.

---

## 9. No-Inference Layer

### 9.1 Problem

AI systems often infer missing context.

This may be useful in ordinary tasks, but it is dangerous when handling creator-defined meaning structures.

Risks include:

- unauthorized interpretation
- over-completion
- false attribution
- invented intention
- private context reconstruction
- meaning boundary violation

### 9.2 Proposed Direction

Introduce a No-Inference Layer.

Possible controls:

```text
[ ] Do not infer beyond this field
[ ] Do not reconstruct private context
[ ] Do not convert friction into psychological diagnosis
[ ] Do not summarize Deep Layer
[ ] Do not use this field for training
```

### 9.3 Example

```yaml
no_inference_policy:
  enabled: true
  protected_fields:
    - initial_friction
    - deep_layer
    - private_creator_note
  prohibited_actions:
    - infer_intent
    - reconstruct_private_context
    - summarize_protected_fields
    - use_for_training
```

### 9.4 Design Principle

AI should assist within the creator-defined boundary.

AI should not silently expand that boundary.

---

## 10. Royalty OS Visibility

### 10.1 Problem

Royalty or allocation-related information can easily be misunderstood as guaranteed payment.

However, trace and contribution data may still be useful as transparency signals.

### 10.2 Proposed Direction

Introduce a Royalty OS Visibility layer that shows allocation-readiness, not final entitlement.

Possible UI elements:

```text
Trace events
Reference depth
Contribution score
Allocation-readiness status
Estimated preview
Review status
Dispute status
```

### 10.3 Required Disclaimer

Any royalty-related UI must clearly state:

```text
This preview is an estimation only.
It does not guarantee payment, ownership, entitlement, or final allocation.
```

### 10.4 Example

```yaml
royalty_visibility:
  trace_contribution_score: 4.1
  allocation_readiness: review_required
  estimated_preview:
    amount: 128
    currency: JPY
    guaranteed: false
  disclaimer_required: true
```

### 10.5 Design Principle

Trace evidence and allocation readiness must remain separate from final payment execution.

---

## 11. Epicenter Network

### 11.1 Problem

Individual articles may contain epicenters.

But in AI-mediated knowledge ecosystems, multiple epicenters may resonate, diverge, influence each other, or form clusters.

A platform may need to show not only individual purity, but also epicenter relationships.

### 11.2 Proposed Direction

Introduce an Epicenter Network view.

Possible network signals:

```text
epicenter_similarity
question_resonance
friction_overlap
meaning_distance
trace_connection
influence_path
version_relationship
```

### 11.3 Example

```yaml
epicenter_network:
  related_epicenters:
    - id: epicenter_001
      relation_type: question_resonance
      strength: 0.82
    - id: epicenter_002
      relation_type: friction_overlap
      strength: 0.67
```

### 11.4 UI Direction

The platform may visualize:

```text
This article resonates with:
- similar questions
- adjacent friction patterns
- shared meaning structures
- trace-linked references
```

### 11.5 Design Principle

The purpose is not to rank creators.

The purpose is to map meaning relationships and source structures.

---

## 12. Relationship to Current Repository

This roadmap extends the current repository in the following way:

```text
AI Purity Detection Algorithm v0.2
= scoring, warning, review-routing layer

docs/ui-mock-note-integration.md
= platform UI mock reference

docs/purity-ui-evolution-roadmap-v0.3.md
= future creator-control and epicenter-interface roadmap
```

The roadmap may later become a separate specification or repository.

Possible future repository:

```text
purity-ui-control-architecture-v0.1
```

---

## 13. Suggested Future Repository Scope

A future independent repository may define:

```text
Purity UI Control Architecture
Visibility Protocol
No-Inference Policy
Circle Versioning
Epicenter Layer
Proto-Friction Layer
Royalty OS Visibility
Epicenter Network
Creator Control Dashboard
```

Possible repository name:

```text
purity-ui-control-architecture-v0.1
```

Possible structure:

```text
.
├── README.md
├── LICENSE
├── CHANGELOG.md
├── CITATION.cff
├── spec/
│   └── purity-ui-control-architecture-v0.1.yaml
├── docs/
│   ├── architecture-overview.md
│   ├── epicenter-layer.md
│   ├── proto-friction-layer.md
│   ├── visibility-protocol.md
│   ├── circle-versioning.md
│   ├── no-inference-layer.md
│   ├── royalty-os-visibility.md
│   └── epicenter-network.md
├── schemas/
│   └── purity-ui-control.schema.json
└── examples/
    ├── basic-article-ui.example.yaml
    ├── creator-controls.example.yaml
    ├── visibility-settings.example.yaml
    └── no-inference-policy.example.yaml
```

---

## 14. Non-Goals

This roadmap does not attempt to:

- define a final UI standard
- replace the current Purity scoring model
- define production-ready API endpoints
- guarantee royalty payment
- rank creators by epicenter strength
- expose private creator context
- force creators to disclose deep meaning structures
- allow AI systems to infer beyond permitted boundaries
- determine legal authorship or ownership
- define a final network graph algorithm

This is a roadmap for future design exploration.

---

## 15. Summary

Purity UI can evolve from a simple score display into a creator-controlled origin interface.

The v0.3 direction introduces:

```text
Epicenter Layer
Proto-Friction Layer
Visibility Protocol
Circle Versioning
No-Inference Layer
Royalty OS Visibility
Epicenter Network
```

The purpose is to connect:

```text
human friction
↓
question formation
↓
meaning structure
↓
creator control
↓
AI-readable boundaries
↓
trace visibility
↓
value circulation
```

In short:

> Purity UI should not only show the origin of content.  
> It should help creators preserve, control, version, and circulate the source structure of meaning.

This roadmap is the bridge between Purity Detection and a future Purity UI Control Architecture.

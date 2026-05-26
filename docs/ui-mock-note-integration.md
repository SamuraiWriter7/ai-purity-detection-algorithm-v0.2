# UI Mock for Platform Integration: note, Purity, and Consciousness Circle

## 1. Purpose

This document provides a conceptual UI mock for integrating the AI Purity Detection Algorithm v0.2 into a note-style article platform.

The purpose of this mock is to illustrate how Purity metadata, Consciousness Circle metadata, Trace logs, Royalty OS previews, and Creator Controls could be presented within an article page and creator dashboard.

This is not an implementation requirement.  
It is a reference design for platform-level integration.

The core idea is simple:

> An article should not only display content.  
> It should also preserve the human origin, question structure, trace context, and creator-controlled boundaries behind that content.

---

## 2. Conceptual Overview

In AI-mediated knowledge ecosystems, articles may be read, summarized, retrieved, embedded, cited, and reused by AI systems.

This creates several important questions:

- Was the article grounded in human-origin primary experience?
- What question or friction generated the article?
- Which parts of the semantic structure may be disclosed?
- How has the article been referenced by AI systems?
- Can trace data contribute to future allocation or royalty-readiness?
- Does the creator retain control over disclosure and reuse boundaries?

This UI mock explores one possible interface pattern for answering those questions.

The integration model consists of five visible layers:

1. **Purity Badge**
2. **Purity Breakdown Panel**
3. **Consciousness Circle Panel**
4. **Trace and Royalty OS Preview**
5. **Creator Controls**

Together, these layers form a platform-level interface for preserving source integrity, semantic origin, and creator sovereignty.

---

## 3. Article Page Mock

The following is a simplified text-based mock of a note-style article page with Purity integration.

```text
──────────────────────────────────────────────
[Article Title]

AI and Morning Habits:
Why I Failed Many Times Before Building a Sustainable Routine

[Purity Badge - Article Header]
● Purity: 87 / High Natural
  Human-origin primary context is strongly detected.
──────────────────────────────────────────────

[Purity Breakdown - Collapsible Panel]
▼ Purity Breakdown
  - Epicenter Strength: 0.92
  - Human-Origin Confidence: 0.88
  - AI-Assisted Ratio: 0.12
  - Unverified Synthetic Influence: 0.03
  - Meaning Integrity Risk: Low

  Note:
  These indicators are derived from primary experience signals,
  initial friction, contextual depth, and semantic structure.
──────────────────────────────────────────────

[Consciousness Circle]
▼ Consciousness Structure
  Displayed only within the creator-authorized disclosure range.

  ● Core Question
    "Why have I repeatedly failed to maintain a morning routine?"

  ● Initial Friction
    - Type: emotion
    - Summary: Frustration with repeated short-term failure

  ● Deep Layer
    - Disclosure: partially disclosed
    - Summary: Low self-efficacy and past failure patterns

  ● Rotation Dynamics
    - Friction → Question → Structure → Insight
    - Dominant Axis: emotion → design
──────────────────────────────────────────────

[Article Body]
Normal article content appears here.
──────────────────────────────────────────────

[Trace Log]
▼ AI Reference History
  Disclosure: creator-authorized

  - Gemini-like retrieval system referenced this article on 2026-05-12
  - Platform AI editor referenced this article on 2026-05-14
  - RAG-based knowledge system referenced this article on 2026-05-15

  Note:
  Reference data may be used for future allocation-readiness analysis.
──────────────────────────────────────────────

[Royalty OS Preview]
▼ Estimated Allocation Readiness

  - Trace contribution score: 4.1
  - Estimated allocation preview: ¥128
  - Source categories: AI retrieval / platform AI / RAG system

  Disclaimer:
  This preview is only an estimation and does not guarantee actual payment.
──────────────────────────────────────────────

[Creator Controls]
▼ Disclosure and Usage Settings

  [x] Core Question: public
  [x] Initial Friction: partially public
  [ ] Deep Layer: private
  [x] Allow Trace visibility
  [x] Allow Royalty OS participation
  [ ] Allow AI training use

  Note:
  The creator retains control over disclosure boundaries.
──────────────────────────────────────────────

4. Purity Badge

The Purity Badge provides a lightweight reader-facing signal.

Example:

● Purity: 87 / High Natural
Human-origin primary context is strongly detected.

The badge should not be interpreted as an anti-AI label.

The purpose is not to punish AI-assisted writing.
The purpose is to indicate whether a work preserves a meaningful human-origin epicenter.

Recommended display levels:

Score Range	Label	Meaning
80–100	High Natural	Strong human-origin signals detected
60–79	Mixed Natural	Human-origin signals detected with notable AI assistance
40–59	Hybrid	Human and synthetic signals are strongly mixed
20–39	Synthetic-Dominant	Synthetic structure may dominate the content
0–19	Low Origin Confidence	Human-origin signals are weak or unclear
5. Purity Breakdown Panel

The Purity Breakdown Panel provides a more transparent view of the underlying indicators.

Suggested fields:

Field	Description
epicenter_strength	Degree to which the article appears to originate from a distinct human question, experience, or friction
human_origin_confidence	Confidence that the article preserves human-origin context
ai_assisted_ratio	Estimated degree of AI assistance in composition or structuring
unverified_synthetic_influence	Degree of synthetic influence that lacks clear creator-origin grounding
meaning_integrity_risk	Risk that the original semantic structure has been diluted, distorted, or overwritten

Recommended wording:

This score estimates the preservation of human-origin context.
It does not judge whether AI assistance was used.
6. Consciousness Circle Panel

The Consciousness Circle Panel represents the semantic origin layer behind an article.

It may include:

Core Question
Initial Friction
Deep Layer
Rotation Dynamics
Disclosure Scope
Creator Notes

Example:

▼ Consciousness Structure

Core Question:
"Why have I repeatedly failed to maintain a morning routine?"

Initial Friction:
- Type: emotion
- Summary: Frustration with repeated short-term failure

Deep Layer:
- Disclosure: partially disclosed
- Summary: Low self-efficacy and past failure patterns

Rotation Dynamics:
Friction → Question → Structure → Insight
Dominant Axis: emotion → design

This panel should be creator-controlled.

The platform should never require creators to disclose private internal context.
The Deep Layer should remain private by default.

7. Trace Log Panel

The Trace Log Panel shows how an article has been referenced, retrieved, or reused by AI-mediated systems.

Possible trace categories:

Category	Description
retrieval_reference	The article was retrieved by an AI search or RAG system
summary_reference	The article was used in AI-generated summary context
citation_reference	The article was cited or linked in an output
influence_reference	The article may have influenced generated structure without explicit citation
platform_reference	The article was processed by an internal platform AI feature

Example:

▼ AI Reference History

- Retrieval reference detected: 2026-05-12
- Platform AI editor reference detected: 2026-05-14
- RAG system reference detected: 2026-05-15

Trace visibility should be controlled by the creator or platform policy.

8. Royalty OS Preview

The Royalty OS Preview provides an allocation-readiness view based on Purity and Trace signals.

Example:

▼ Estimated Allocation Readiness

Trace contribution score: 4.1
Estimated allocation preview: ¥128
Source categories: AI retrieval / platform AI / RAG system

This section must include a disclaimer:

This preview is an estimation only.
It does not guarantee actual payment, compensation, or allocation.

The purpose of this section is not to define final royalty distribution.

The purpose is to show that trace data may become relevant for future value circulation systems.

9. Creator Controls

Creator Controls are essential to this UI model.

The creator should be able to define:

Which metadata fields are public
Which fields are partially disclosed
Which fields remain private
Whether AI reference logs may be displayed
Whether the article participates in allocation-readiness systems
Whether the article may be used for AI training
Whether deep semantic metadata can be exposed to external systems

Example:

▼ Disclosure and Usage Settings

[x] Core Question: public
[x] Initial Friction: partially public
[ ] Deep Layer: private
[x] Allow Trace visibility
[x] Allow Royalty OS participation
[ ] Allow AI training use

The key principle:

AI systems may assist, infer, and classify.
But creator-defined disclosure boundaries must remain authoritative.

10. Design Principles

This UI mock follows the principles below.

10.1 Creator Sovereignty

The creator controls disclosure scope, semantic boundaries, and participation in trace or allocation systems.

10.2 Human-Origin Preservation

The interface should preserve human-origin signals such as friction, lived experience, and question formation.

10.3 AI Assistance Neutrality

AI assistance should not be treated as negative by default.

The problem is not AI usage itself.
The problem is when synthetic structure overwrites or obscures human-origin context.

10.4 Privacy by Design

Deep semantic context must be private by default.

Platforms should not force creators to disclose personal, sensitive, emotional, or biographical context.

10.5 Allocation Readiness, Not Automatic Payment

Trace and Purity data may support future royalty-readiness analysis.

However, this UI does not define automatic payment logic.

10.6 Interpretability

Readers should be able to understand why a Purity level is shown.

Opaque scoring should be avoided.

11. Non-Goals

This UI mock does not attempt to:

Prove legal authorship
Replace copyright law
Guarantee royalty payments
Penalize AI-assisted writing
Expose private creator context
Rank creators by purity
Claim that high Purity means higher quality
Claim that low Purity means low value
Detect all forms of AI generation with certainty
Define a final implementation standard for note or any other platform

This document is a conceptual integration mock.

12. Relationship to Consciousness Circle Metadata

This UI mock depends on Consciousness Circle metadata as the semantic structure layer behind Purity scoring.

Relevant concepts include:

core_question
initial_friction
deep_layer
rotation_dynamics
disclosure_scope
creator_control

The Consciousness Circle layer provides the human-origin semantic context that Purity scoring alone cannot fully represent.

Purity answers:

How strongly does this article preserve human-origin signals?

Consciousness Circle answers:

What question, friction, and semantic structure generated this article?

Together, they form a stronger origin-preservation model.

13. Relationship to Trace Architecture

Trace data records how an article is referenced, retrieved, summarized, or reused by AI systems.

Purity and Consciousness Circle metadata describe the origin-side structure.
Trace architecture describes the downstream usage-side structure.

Together:

Origin Structure → Purity Detection → Trace Recording → Allocation Readiness

This flow supports future creator-centered value circulation systems.

14. Relationship to Royalty OS

Royalty OS is not implemented by this UI mock.

However, the mock shows how Purity and Trace signals may become inputs for future allocation-readiness systems.

Possible flow:

Human-Origin Context
        ↓
Purity Metadata
        ↓
Consciousness Circle Metadata
        ↓
Trace Log
        ↓
Allocation Readiness
        ↓
Royalty OS Preview

The UI should clearly distinguish between:

trace evidence
allocation readiness
actual payment execution

These should not be collapsed into a single automatic process.

15. Suggested Platform Layers

A practical implementation may separate the UI into three layers.

Layer 1: Reader-Facing Minimal Display
Purity: 87 / High Natural
Human-origin primary context is strongly detected.
Layer 2: Reader-Facing Details
Purity Breakdown
Consciousness Circle summary
Trace visibility, if authorized
Layer 3: Creator Dashboard
Disclosure controls
AI training permissions
Trace visibility controls
Royalty OS participation controls
Deep Layer privacy controls

This separation helps prevent privacy leakage while still allowing meaningful transparency.

16. Future Extensions

Possible future extensions include:

UI mock for creator dashboard
UI mock for AI crawler access settings
JSON examples for platform-side Purity display objects
Integration with RAG metadata
Integration with allocation-readiness review
Integration with dispute or correction flows
Accessibility-friendly UI labels
Multilingual display fields
17. Summary

This UI mock demonstrates how a note-style article page could evolve from a simple content display into a creator-controlled semantic origin interface.

The proposed interface connects:

Purity detection
Consciousness Circle metadata
Trace logs
Royalty OS previews
Creator Controls

The result is a platform pattern where articles are not treated merely as content, but as human-origin semantic nodes in AI-mediated knowledge ecosystems.

In short:

The article becomes a preserved epicenter of question, friction, trace, and value circulation.

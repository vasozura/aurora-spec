# AFL Prompt Export Intent Specification

Document ID: AFL-000010  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 06-AI/AFL-000010_PROMPT_EXPORT_INTENT_SPEC.md  
Document Type: Aurora Film Language Specification  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, 01-Product/GLOSSARY.md, 01-Product/ROADMAP.md, 02-Architecture/ARCHITECTURE.md, 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md, 06-AI/AFL-000002_SCENE_MODEL_SPEC.md, 06-AI/AFL-000003_SHOT_MODEL_SPEC.md, 06-AI/AFL-000004_EMOTION_MODEL_SPEC.md, 06-AI/AFL-000005_CAMERA_MODEL_SPEC.md, 12-Templates/SPEC_TEMPLATE.md  

---

## 1. Purpose

This document defines Prompt Export Intent inside Aurora Film Language.

Prompt Export Intent describes how structured AFL meaning may be converted into external prompt text, provider-specific request structures, shot lists, storyboards or other export outputs.

Prompt Export Intent is not the internal source of truth.

AFL is the source structure.

Prompts are outputs.

Prompt Export Intent is the controlled bridge between AFL and export targets.

---

## 2. Authority

This specification is subordinate to the Aurora Constitution, AES, Review Standard, Architecture and prior AFL foundation specifications.

If this specification conflicts with the Aurora Constitution, the Constitution takes precedence.

This document defines the conceptual Prompt Export Intent model only.

Implementation requires later data, API, plugin, event and test specifications.

---

## 3. Scope

This specification defines:

- What Prompt Export Intent is
- What Prompt Export Intent is not
- Export responsibility
- Target export types
- Target provider concept
- Provider independence
- Detail level
- Prompt style
- Constraint handling
- Negative constraints
- Safety constraints
- Reference asset usage
- Duration and aspect ratio intent
- Continuity emphasis
- Provider limitation handling
- Relationship to Scene, Shot, Emotion, Camera, Composition, Symbol, Motion and Transition
- Validation expectations
- Error handling expectations
- Offline-first expectations
- Security expectations
- Testing expectations
- Implementation readiness

---

## 4. Non-Scope

This specification does not define:

- Python classes
- JSON schema
- Database schema
- GUI prompt editor
- Actual provider prompt templates
- WAN prompt syntax
- Veo prompt syntax
- Kling prompt syntax
- Runway prompt syntax
- OpenAI API request format
- Provider adapter implementation
- Prompt ranking algorithm
- Automatic quality scoring
- Prompt execution
- Video generation API calls
- Plugin SDK behavior
- Persistence format
- Serialization format
- Validation code
- Implementation code

Those topics require later specifications.

---

## 5. Definitions

| Term | Meaning |
|---|---|
| Prompt Export Intent | Structured guidance for converting AFL meaning into external outputs. |
| Export Target | The intended output format or provider family. |
| Provider Target | A specific AI provider or model family selected for export. |
| Prompt Detail Level | The intended amount of detail in exported prompt text. |
| Prompt Style | The language style or formatting approach used during export. |
| Negative Constraint | A condition describing what should be avoided. |
| Safety Constraint | A rule ensuring export respects user, platform or policy constraints. |
| Reference Asset Usage | Rules for whether and how reference assets may be included in export. |
| Provider Limitation | Known constraint of a target provider or model. |
| Export Artifact | The generated output, such as prompt text, JSON request, shot list or storyboard instruction. |

---

## 6. Prompt Export Intent Responsibility

Prompt Export Intent is responsible for controlling export behavior without replacing AFL meaning.

It may influence:

- Prompt text
- Provider request structure
- Shot list output
- Storyboard output
- Negative prompt output
- Reference asset packaging
- Duration and aspect ratio guidance
- Provider-specific adaptation
- Export validation
- Review and reporting

Prompt Export Intent must not modify core AFL meaning.

Prompt Export Intent must not introduce provider-specific fields into AFL core concepts unless explicitly approved.

Prompt Export Intent must remain separate from provider plugin implementation.

---

## 7. Prompt Is Output

Bad internal model:

```text
Scene = prompt text
```

Correct model:

```text
AFL Scene + AFL Shot + Emotion + Camera + Composition + Motion + Symbol + Transition
  ↓
Prompt Export Intent
  ↓
Provider-specific prompt or request
```

Prompt text may change while AFL meaning remains stable.

This separation is mandatory.

---

## 8. Export Target Types

Possible export target types may include:

- Text prompt
- Negative prompt
- Provider request object
- Shot list
- Storyboard description
- Director notes
- Production breakdown
- Timeline instruction
- Batch generation request
- Asset generation request

This list is not final.

A future export interface specification must define supported target types.

---

## 9. Provider Target

Provider Target may identify the intended export destination.

Examples:

- Generic video model
- Generic image model
- WAN-compatible exporter
- Veo-compatible exporter
- Kling-compatible exporter
- Runway-compatible exporter
- OpenAI-compatible exporter
- Local model exporter
- Storyboard text exporter
- Human-readable director notes

Provider Target must be optional until export is needed.

AFL core must not depend on a provider target.

---

## 10. Provider Independence

Prompt Export Intent may reference provider targets, but AFL core must remain provider-independent.

Provider-specific adaptation belongs in plugins or approved adapters.

If a provider requires special syntax, that syntax belongs in provider export logic, not in Scene, Shot, Emotion, Camera, Composition, Symbol, Motion or Transition core fields.

---

## 11. Prompt Detail Level

Prompt Detail Level controls how much detail export should include.

Conceptual levels may include:

- Minimal
- Compact
- Balanced
- Detailed
- Highly detailed
- Technical
- Director-facing
- Model-facing
- Human-readable

Detail level must not change AFL meaning.

It changes output expression.

---

## 12. Prompt Style

Prompt Style controls language and formatting of exported prompt text.

Possible styles may include:

- Cinematic descriptive
- Technical shot list
- Natural language
- Provider-optimized
- Compact tag-based
- Structured paragraph
- Bullet format
- JSON-like request
- Human review format

This specification does not define actual provider templates.

---

## 13. Negative Constraints

Negative Constraints define what export should avoid.

They may include:

- Avoid extra characters
- Avoid camera shake
- Avoid text artifacts
- Avoid distorted anatomy
- Avoid changing character identity
- Avoid modern objects
- Avoid low-light noise
- Avoid excessive motion
- Avoid provider-specific failure patterns

Negative Constraints must be tied to export behavior, not hidden in core meaning.

---

## 14. Safety Constraints

Safety Constraints define export rules that protect users, projects and platforms.

They may include:

- Do not send private reference assets without permission.
- Do not include disallowed content.
- Do not expose internal notes unless required.
- Do not send unnecessary project data to online providers.
- Do not include sensitive metadata unless approved.
- Respect user ownership of creative work.

Safety Constraints must be explicit and reviewable.

---

## 15. Reference Asset Usage

Reference Asset Usage defines how references may be used during export.

It may include:

- Required reference
- Optional reference
- Character reference
- Location reference
- Object reference
- Style reference
- Composition reference
- Motion reference
- Do not export reference
- Local-only reference
- Provider-allowed reference

Missing required references must be reported before export.

---

## 16. Duration Intent

Prompt Export Intent may carry duration guidance.

Duration guidance may include:

- Approximate duration
- Fixed duration
- Provider-limited duration
- Shot duration target
- Sequence duration target
- Long take preference
- Short insert preference

Duration Intent must not be treated as guaranteed output duration unless provider specification says so.

---

## 17. Aspect Ratio Intent

Aspect Ratio Intent may define visual output shape.

Possible values may include:

- 16:9
- 9:16
- 1:1
- 4:3
- 2.39:1
- Custom
- Provider default

Aspect ratio must be export guidance unless a later specification makes it project-level requirement.

---

## 18. Continuity Emphasis

Continuity Emphasis controls how strongly export should preserve continuity.

It may include:

- Character identity
- Costume
- Location
- Prop
- Symbol
- Camera language
- Lighting
- Emotion
- Motion
- Time
- Sound motif

Continuity Emphasis must be explicit when model output may drift.

---

## 19. Provider Limitation Handling

Provider Limitation Handling defines how export should respond to known provider constraints.

Possible responses:

- Simplify prompt
- Split into multiple shots
- Reduce motion complexity
- Reduce character count
- Remove unsupported parameter
- Use generic wording
- Report unsupported intent
- Require user review
- Choose alternative export target

Provider limitations must not change AFL source meaning.

They may affect export artifact only.

---

## 20. Export Artifact Separation

Export artifacts must be separated from AFL core meaning.

Export artifacts may include:

- Prompt text
- Negative prompt text
- Provider request body
- Provider parameter set
- Generation batch file
- Storyboard text
- Shot list export
- Human-readable report

Export artifacts may be regenerated from AFL and Prompt Export Intent.

They must not become the only source of meaning.

---

## 21. Relationship To Scene

Scene may define broad export intent.

Scene-level Prompt Export Intent may specify:

- Export mode
- Scene-level detail
- Shot breakdown preference
- Continuity emphasis
- Target provider
- Safety constraints
- Reference usage
- Scene-level negative constraints

Scene export must preserve Scene Purpose, Narrative Context, Emotional Arc and Visual Strategy.

---

## 22. Relationship To Shot

Shot may define specific export intent.

Shot-level Prompt Export Intent may specify:

- Shot prompt detail level
- Camera emphasis
- Composition emphasis
- Motion emphasis
- Duration target
- Reference usage
- Negative constraints
- Provider target
- Output format

Shot export must preserve Shot Purpose and Subject Focus.

---

## 23. Relationship To Emotion

Emotion may be translated into prompt language, but Emotion remains source meaning.

Export may express:

- Dominant emotion
- Hidden emotion
- Surface emotion
- Audience emotion
- Intensity
- Visibility
- Emotional arc
- Contradiction

Export must not flatten complex emotion into one vague word if the target output requires nuance.

---

## 24. Relationship To Camera And Composition

Prompt Export Intent may decide how strongly to include Camera and Composition.

Examples:

- Camera-first prompt
- Character-first prompt
- Composition-heavy prompt
- Motion-heavy prompt
- Emotion-first prompt
- Minimal camera prompt

Export emphasis must be explicit when important.

---

## 25. Relationship To Symbol, Motion And Transition

Export may include Symbol, Motion and Transition meaning when relevant.

Symbol export must preserve meaning-critical symbols.

Motion export must preserve movement intent and avoid impossible or overloaded motion when provider limitations exist.

Transition export must preserve relationship between units when generating sequences or shot lists.

---

## 26. Provider Plugin Boundary

Provider plugins may consume AFL structures and Prompt Export Intent through approved interfaces.

Provider plugins may generate provider-specific export artifacts.

Provider plugins must not modify AFL core meaning.

Provider plugins must not introduce provider-specific syntax into AFL core fields.

Provider-specific exporter behavior must be isolated.

---

## 27. Validation Expectations

Future validation should check:

1. Export target is defined when export is requested.
2. Provider target is valid when provider-specific export is requested.
3. Detail level is valid.
4. Reference asset requirements are satisfied.
5. Safety constraints are present when needed.
6. Negative constraints are valid.
7. Duration guidance is compatible with provider target when known.
8. Aspect ratio is compatible with provider target when known.
9. Continuity emphasis is defined when identity or scene continuity matters.
10. Provider-specific syntax is isolated to export layer.
11. Export does not modify AFL source meaning.
12. Export can be prepared offline when no online provider call is required.

This specification does not define validation code.

---

## 28. Error Handling Expectations

Potential errors:

| Error Condition | Required Behavior |
|---|---|
| Missing export target | Report incomplete export intent. |
| Unknown provider target | Report unsupported provider target. |
| Missing required reference asset | Report missing dependency. |
| Provider limitation conflicts with requested export | Report unsupported intent or require simplification. |
| Safety constraint missing for sensitive export | Report blocked export preparation. |
| Provider-specific syntax found in AFL core fields | Report specification violation. |
| Export would require online provider while offline-only mode is active | Report blocked online operation. |

Errors must not silently rewrite AFL meaning.

---

## 29. Security Requirements

Prompt Export Intent may expose private creative work.

Exports may contain:

- Story details
- Character details
- Emotional design
- Symbolic meaning
- Private references
- Prompt text
- Provider request data
- User creative decisions

Provider plugins must receive only the data required for selected export.

Online export must not happen without user-initiated or approved operation.

---

## 30. Offline-First Requirements

Prompt Export Intent creation, editing, saving, loading, validation and review must work offline whenever technically possible.

Local prompt export may work offline.

Online provider execution may require Internet access, but the export intent itself must remain local and usable.

---

## 31. Testing Requirements

Future Prompt Export implementation must include tests for:

- Export Intent creation
- Export target validation
- Provider target validation
- Detail level validation
- Negative constraint validation
- Safety constraint validation
- Reference asset validation
- Duration and aspect ratio compatibility
- Continuity emphasis validation
- Provider-specific syntax isolation
- Export artifact separation from AFL source
- Offline export preparation behavior
- Backward compatibility for versioned Prompt Export Intent data

This specification does not create test files.

---

## 32. Example Conceptual Prompt Export Intent

```text
Export Owner:
Shot: Hand on the Door Handle

Export Target:
Text prompt for video generation.

Provider Target:
Generic video model.

Prompt Detail Level:
Detailed but compact.

Prompt Style:
Cinematic descriptive paragraph.

Continuity Emphasis:
Character sleeve, old door texture, stillness, restrained emotion.

Camera Emphasis:
Static close-up, slightly low angle.

Composition Emphasis:
Hand in lower third, old door dominates frame.

Motion Emphasis:
Tiny finger movement only.

Negative Constraints:
No extra people. No dramatic camera shake. No text artifacts.

Safety Constraints:
Do not include private production notes.

Reference Asset Usage:
Use character sleeve reference if available.
```

This example is not a schema.

---

## 33. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This specification defines the conceptual Prompt Export Intent model only.

Implementation cannot begin until data, API, plugin boundary, event and test specifications exist and are reviewed.

---

## 34. Acceptance Criteria

This specification is acceptable when:

1. Prompt Export Intent purpose is defined.
2. Prompt Export Intent non-scope is explicit.
3. Prompt Export Intent responsibility is defined.
4. Prompt is explicitly defined as output.
5. Export Target Types are defined.
6. Provider Target is defined.
7. Provider independence is defined.
8. Prompt Detail Level is defined.
9. Prompt Style is defined.
10. Negative Constraints are defined.
11. Safety Constraints are defined.
12. Reference Asset Usage is defined.
13. Duration Intent is defined.
14. Aspect Ratio Intent is defined.
15. Continuity Emphasis is defined.
16. Provider Limitation Handling is defined.
17. Export Artifact Separation is defined.
18. Relationships to Scene, Shot, Emotion, Camera, Composition, Symbol, Motion and Transition are defined.
19. Provider plugin boundary is defined.
20. Validation expectations are defined.
21. Error handling expectations are defined.
22. Security expectations are defined.
23. Offline-first expectations are defined.
24. Testing expectations are defined.
25. Implementation readiness is explicitly marked Not Ready.

---

## 35. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

---

## 36. Summary

Prompt Export Intent is the controlled bridge from AFL to external outputs.

AFL is source meaning.

Prompts are export artifacts.

Provider-specific syntax belongs in export plugins or approved adapters, not in AFL core.

Future implementation must build from approved data, API, plugin and test specifications.

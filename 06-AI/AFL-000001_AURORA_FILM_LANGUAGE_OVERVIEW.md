# Aurora Film Language Overview

Document ID: AFL-000001  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md  
Document Type: Aurora Film Language Specification  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, 01-Product/GLOSSARY.md, 01-Product/ROADMAP.md, 02-Architecture/ARCHITECTURE.md, 12-Templates/SPEC_TEMPLATE.md  

---

## 1. Purpose

This document defines the foundation of Aurora Film Language, abbreviated as AFL.

AFL is the internal structured language used by Aurora Studio to represent cinematic intent before that intent is exported to prompts, provider-specific requests, scripts, timelines, shot lists or other external formats.

AFL exists because prompts are not a stable internal model.

AI providers, model syntax and generation tools may change.

Cinematic meaning must remain stable.

AFL is the layer that preserves meaning.

---

## 2. Authority

This document is subordinate to:

- 00-Governance/AURORA_CONSTITUTION.md
- 00-Governance/AURORA_ENGINEERING_STANDARD.md
- 00-Governance/REVIEW_STANDARD.md
- 02-Architecture/ARCHITECTURE.md

If this document conflicts with the Aurora Constitution, the Constitution takes precedence.

If this document conflicts with the Architecture document, implementation must stop until the conflict is reviewed.

This document is the starting point for all future AFL specifications.

---

## 3. Core Principle

Aurora Film Language is not prompt text.

Aurora Film Language is not JSON.

Aurora Film Language is not a provider API.

Aurora Film Language is not a video model syntax.

Aurora Film Language is the internal representation of cinematic meaning.

Prompts are exports.

Provider requests are exports.

Shot lists are exports.

AFL is the source structure from which those outputs may be generated.

---

## 4. Scope

This document defines:

- The purpose of AFL
- The role of AFL inside Aurora
- The difference between AFL and prompts
- The core conceptual areas of AFL
- The first required AFL document family
- The relationship between AFL, modules, data models and plugins
- The principles that future AFL specifications must follow
- Initial acceptance criteria for AFL foundation readiness

This document applies to:

- Aurora Film Language
- Prompt export architecture
- Future AFL modules
- Future AFL data specifications
- Future provider export plugins
- Future scene, shot, emotion, camera and composition specifications

---

## 5. Non-Scope

This document does not define:

- Final AFL schema
- JSON format
- Python classes
- Database schema
- GUI design
- Provider-specific prompt syntax
- WAN prompt syntax
- Veo prompt syntax
- Kling prompt syntax
- Runway prompt syntax
- OpenAI API request format
- Plugin SDK details
- Full scene model fields
- Full shot model fields
- Implementation code
- Validation code
- Export algorithms

Those must be defined in later specifications.

---

## 6. Definitions

| Term | Meaning |
|---|---|
| AFL | Aurora Film Language. The internal structured language of cinematic meaning in Aurora. |
| Cinematic Intent | The planned meaning, emotion, visual structure and narrative role of a cinematic unit. |
| Scene | A meaningful dramatic, visual or narrative unit within a film. |
| Shot | A smaller cinematic unit usually representing one camera perspective or generated video segment. |
| Prompt | Text exported from Aurora structures for use in an AI system. |
| Prompt Export Intent | The structured intention that guides how AFL is translated into provider-specific prompt text. |
| Provider Export | Conversion from AFL into a provider-specific output format. |
| AFL Core Concept | A fundamental concept such as Scene, Shot, Emotion, Symbol, Camera, Composition, Motion or Transition. |
| Visual Meaning | The intended interpretation carried by visual elements, composition, symbolism, movement, lighting or cinematic structure. |
| Provider-Specific Syntax | The unique prompt, API or parameter style required by a specific AI generation system. |

---

## 7. Why AFL Exists

Without AFL, Aurora would depend on prompt text as the internal product model.

That would create serious problems:

1. Prompt formats change.
2. AI providers use different syntax.
3. A prompt is difficult to validate.
4. A prompt is difficult to version structurally.
5. A prompt mixes meaning, style, technical instruction and provider-specific tricks.
6. A prompt cannot reliably represent timeline, scene logic, character continuity or symbolic structure.
7. A prompt is output, not design.

AFL solves this by separating cinematic meaning from export format.

Aurora designs meaning first.

Then Aurora exports that meaning into prompts or other external formats.

---

## 8. AFL Position In Aurora Architecture

AFL belongs to Aurora's internal product meaning.

AFL concepts live primarily in the Domain Layer.

AFL processing may be coordinated by Aurora Core and Application Services.

AFL export to specific AI providers must happen through plugins or approved adapters.

AFL must not depend on any specific AI provider.

AFL must not require online services.

AFL must remain usable offline.

Provider-specific export belongs outside AFL core.

---

## 9. AFL Relationship To Prompts

A prompt is not the source of truth.

A prompt is an export artifact.

AFL may produce different prompts for different targets while preserving the same cinematic intent.

Example:

```text
AFL Scene Intent
  ↓
WAN prompt
  ↓
Veo prompt
  ↓
Kling prompt
  ↓
Runway prompt
  ↓
Storyboard text
  ↓
Shot list
```

The same AFL structure may produce multiple outputs.

The output may change.

The internal meaning must remain stable.

---

## 10. AFL Core Concept Families

The first AFL foundation must include the following concept families:

1. Scene
2. Shot
3. Character Presence
4. Emotion
5. Symbol
6. Camera
7. Composition
8. Motion
9. Transition
10. Sound Intent
11. Style Intent
12. Prompt Export Intent

Each concept family must later receive its own specification or be explicitly included in a broader approved AFL specification.

---

## 11. Scene Concept

A Scene represents a meaningful dramatic, visual or narrative unit.

A Scene may contain:

- Purpose
- Narrative role
- Emotional direction
- Characters
- Location
- Time context
- Visual tone
- Symbolic elements
- Shot list
- Sound intent
- Transition intent
- Export intent

A Scene is not merely a prompt.

A Scene is a structured unit of cinematic meaning.

The full Scene model must be defined in a later AFL specification.

Candidate future document:

```text
06-AI/AFL-000002_SCENE_MODEL_SPEC.md
```

---

## 12. Shot Concept

A Shot represents a smaller cinematic unit inside a Scene.

A Shot may contain:

- Shot purpose
- Subject focus
- Camera angle
- Camera movement
- Composition
- Motion
- Emotion
- Duration intent
- Visual details
- Continuity requirements
- Export intent

A Shot is the likely unit for many video generation outputs.

The full Shot model must be defined in a later AFL specification.

Candidate future document:

```text
06-AI/AFL-000003_SHOT_MODEL_SPEC.md
```

---

## 13. Character Presence Concept

Character Presence defines how a character exists inside a scene or shot.

It may include:

- Character identity
- Role in scene
- Visual continuity requirements
- Emotional state
- Action
- Relationship to other characters
- Position in frame
- Visibility level
- Dialogue or silence
- Reference requirements

Character Presence is not the same as a character database record.

It is the character's scene-specific or shot-specific participation.

The full Character Presence model must be defined in a later specification.

---

## 14. Emotion Concept

Emotion represents emotional state, direction or transformation.

AFL must support emotion at multiple levels:

- Film level
- Sequence level
- Scene level
- Shot level
- Character level
- Camera or composition level
- Sound or rhythm level

Emotion must be structured enough to guide generation and review.

Emotion must not be reduced to vague words such as "sad" or "beautiful" without context.

The full Emotion model must be defined in a later AFL specification.

Candidate future document:

```text
06-AI/AFL-000004_EMOTION_MODEL_SPEC.md
```

---

## 15. Camera Concept

Camera represents the intended visual capture behavior.

It may include:

- Angle
- Distance
- Lens feel
- Movement
- Framing
- Perspective
- Stability
- Focus behavior
- Subject relationship
- Cinematic motivation

Camera must be represented as cinematic intent, not provider-specific syntax.

The full Camera model must be defined in a later AFL specification.

Candidate future document:

```text
06-AI/AFL-000005_CAMERA_MODEL_SPEC.md
```

---

## 16. Composition Concept

Composition represents the arrangement of visual elements inside the frame.

It may include:

- Subject placement
- Foreground
- Background
- Depth
- Balance
- Negative space
- Symmetry or asymmetry
- Attention direction
- Visual hierarchy
- Symbolic placement

Composition must help Aurora preserve visual meaning across exports.

The full Composition model must be defined in a later AFL specification.

Candidate future document:

```text
06-AI/AFL-000006_COMPOSITION_MODEL_SPEC.md
```

---

## 17. Symbol Concept

Symbol represents a visual, narrative or emotional element with meaning beyond its literal presence.

A symbol may be:

- Object
- Color
- Weather element
- Light source
- Gesture
- Location detail
- Repeated visual motif
- Sound motif
- Camera behavior
- Environmental element

Symbols must be traceable across scenes and shots when continuity matters.

The full Symbol model must be defined in a later AFL specification.

Candidate future document:

```text
06-AI/AFL-000007_SYMBOL_MODEL_SPEC.md
```

---

## 18. Motion Concept

Motion represents movement inside cinematic structure.

Motion may include:

- Character movement
- Object movement
- Camera movement
- Environmental movement
- Emotional movement
- Rhythm movement
- Transition movement

Motion must be described by intention, not only by physical instruction.

The full Motion model must be defined in a later AFL specification.

Candidate future document:

```text
06-AI/AFL-000008_MOTION_MODEL_SPEC.md
```

---

## 19. Transition Concept

Transition defines how one cinematic unit relates to the next.

Transitions may occur between:

- Shots
- Scenes
- Sequences
- Emotional states
- Time periods
- Locations
- Symbolic states
- Sound states

A transition may be visual, emotional, rhythmic, narrative or symbolic.

The full Transition model must be defined in a later AFL specification.

Candidate future document:

```text
06-AI/AFL-000009_TRANSITION_MODEL_SPEC.md
```

---

## 20. Prompt Export Intent Concept

Prompt Export Intent defines how AFL should be converted into external prompt text or provider request structures.

Prompt Export Intent may include:

- Target provider
- Target model family
- Prompt style
- Required detail level
- Provider constraints
- Negative prompt requirements
- Safety constraints
- Duration target
- Aspect ratio target
- Motion emphasis
- Continuity emphasis
- Character reference usage
- Output format requirements

Prompt Export Intent must not replace AFL.

It is a bridge from AFL to provider-specific output.

The full Prompt Export Intent model must be defined in a later AFL specification.

Candidate future document:

```text
06-AI/AFL-000010_PROMPT_EXPORT_INTENT_SPEC.md
```

---

## 21. AFL And Provider Plugins

Provider plugins may consume AFL structures through approved interfaces.

Provider plugins may translate AFL into provider-specific output.

Provider plugins must not modify AFL core meaning directly.

Provider plugins must not introduce provider-specific fields into AFL core unless approved through specification and review.

Provider-specific extensions must be isolated.

AFL must remain provider-independent.

---

## 22. AFL And Data Ownership

AFL-owned data must be defined by approved data specifications before implementation.

AFL data must be:

- Versioned
- Inspectable
- Recoverable where technically possible
- Compatible with project persistence rules
- Separate from provider-specific export artifacts

Future AFL data specifications must define:

- Field names
- Types
- Required fields
- Optional fields
- Validation rules
- Migration rules
- Compatibility rules

This overview does not define final data fields.

---

## 23. AFL And Events

AFL-related operations may later emit events.

Possible future events:

- AFLSceneCreated
- AFLSceneUpdated
- AFLShotCreated
- AFLShotUpdated
- AFLEmotionChanged
- AFLExportIntentChanged
- AFLValidationFailed
- AFLPromptExportStarted
- AFLPromptExportFinished

This document does not define final event schemas.

Event schemas must be defined in later interface or data specifications.

---

## 24. AFL And Testing

AFL must be testable.

Future tests must verify:

- AFL structures preserve meaning.
- Prompt export does not modify AFL source.
- Provider-specific output remains isolated.
- Required fields are validated.
- Missing required cinematic intent is reported.
- Scene and shot relationships remain consistent.
- Compatibility rules are respected.
- AFL does not depend on online providers.

AFL implementation without applicable tests is incomplete.

---

## 25. AFL And Offline-First Behavior

AFL must work offline.

Users must be able to create, edit, save, inspect and validate AFL structures without Internet access.

Online AI providers may be used only during export, generation or provider-specific operations.

AFL itself must not require an online service.

---

## 26. AFL And Security

AFL must preserve user ownership.

AFL structures may contain creative work, story details, character definitions, prompts, references and private project information.

Provider plugins must not receive AFL data unless explicitly required for export or generation.

Future security specifications must define how plugins receive project data and what permissions are required.

---

## 27. AFL Document Family

The initial AFL document family should include:

```text
06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md
06-AI/AFL-000002_SCENE_MODEL_SPEC.md
06-AI/AFL-000003_SHOT_MODEL_SPEC.md
06-AI/AFL-000004_EMOTION_MODEL_SPEC.md
06-AI/AFL-000005_CAMERA_MODEL_SPEC.md
06-AI/AFL-000006_COMPOSITION_MODEL_SPEC.md
06-AI/AFL-000007_SYMBOL_MODEL_SPEC.md
06-AI/AFL-000008_MOTION_MODEL_SPEC.md
06-AI/AFL-000009_TRANSITION_MODEL_SPEC.md
06-AI/AFL-000010_PROMPT_EXPORT_INTENT_SPEC.md
```

This list may change through review.

Major changes may require an RFC or ADR.

---

## 28. AFL Design Rules

Future AFL specifications must follow these rules:

1. AFL represents cinematic meaning.
2. AFL is provider-independent.
3. AFL is not prompt text.
4. AFL must remain inspectable.
5. AFL must be versioned.
6. AFL must support offline work.
7. AFL must separate meaning from export.
8. AFL must support review.
9. AFL must support testing.
10. AFL must not create hidden provider dependencies.
11. AFL must not depend on GUI implementation.
12. AFL must not depend on specific AI model syntax.
13. AFL must preserve user ownership of creative work.
14. AFL must be structured enough for deterministic AI task execution.
15. AFL must allow future extension without rewriting Aurora Core.

---

## 29. Initial AFL Non-Goals

AFL does not aim to:

- Replace screenwriting formats entirely
- Replace professional editing software
- Replace all prompt writing
- Guarantee AI model output quality
- Force all providers into identical behavior
- Hide provider limitations
- Remove human creative control
- Become a universal cinema ontology
- Become a provider-specific prompt library
- Become a database schema by itself

AFL is a practical internal language for Aurora.

---

## 30. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This overview defines AFL purpose and boundaries only.

Implementation cannot begin until the following exist:

- Scene model specification
- Shot model specification
- Core AFL data model
- Prompt export intent specification
- Public interfaces
- Test specifications
- AI implementation tasks
- Review approval

---

## 31. Acceptance Criteria

This document is acceptable when:

1. AFL purpose is defined.
2. AFL is clearly separated from prompts.
3. AFL is clearly separated from provider-specific syntax.
4. AFL relationship to Aurora Architecture is defined.
5. AFL core concept families are listed.
6. Scene concept is introduced.
7. Shot concept is introduced.
8. Character Presence concept is introduced.
9. Emotion concept is introduced.
10. Camera concept is introduced.
11. Composition concept is introduced.
12. Symbol concept is introduced.
13. Motion concept is introduced.
14. Transition concept is introduced.
15. Prompt Export Intent concept is introduced.
16. Provider plugin boundaries are stated.
17. Data ownership expectations are stated.
18. Testing expectations are stated.
19. Offline-first expectations are stated.
20. Security expectations are stated.
21. Future AFL document family is listed.
22. Implementation readiness is explicitly marked Not Ready.

---

## 32. Change Control

Changes to this document must update:

- Version
- Change history
- Affected AFL documents
- Affected module specifications
- Affected interface specifications
- Affected data specifications
- Affected tasks

Breaking changes to AFL purpose, provider independence or relationship to prompts may require an ADR.

Major expansions of AFL scope may require an RFC.

---

## 33. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

---

## 34. Summary

Aurora Film Language is the internal language of cinematic meaning in Aurora.

AFL exists so Aurora does not become a fragile prompt generator.

AFL separates creative intent from provider-specific output.

Future AI providers may change.

Aurora's internal cinematic meaning must remain stable.

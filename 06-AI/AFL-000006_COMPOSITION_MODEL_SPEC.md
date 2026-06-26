# AFL Composition Model Specification

Document ID: AFL-000006  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 06-AI/AFL-000006_COMPOSITION_MODEL_SPEC.md  
Document Type: Aurora Film Language Specification  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, 01-Product/GLOSSARY.md, 01-Product/ROADMAP.md, 02-Architecture/ARCHITECTURE.md, 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md, 06-AI/AFL-000002_SCENE_MODEL_SPEC.md, 06-AI/AFL-000003_SHOT_MODEL_SPEC.md, 06-AI/AFL-000004_EMOTION_MODEL_SPEC.md, 06-AI/AFL-000005_CAMERA_MODEL_SPEC.md, 12-Templates/SPEC_TEMPLATE.md  

---

## 1. Purpose

This document defines the Aurora Film Language Composition Model.

Composition in Aurora is structured visual arrangement.

Composition is not a vague style word.

Composition is not provider-specific prompt syntax.

Composition defines how subjects, objects, environment, depth, space, attention, visual hierarchy and symbolic placement are organized inside a cinematic frame or sequence of frames.

The Composition Model exists so Aurora can preserve visual meaning before the work is exported to prompts, provider-specific requests, shot lists, storyboards or future timeline structures.

---

## 2. Authority

This specification is subordinate to the Aurora Constitution, Aurora Engineering Standard, Review Standard, Architecture document and prior AFL foundation specifications.

If this specification conflicts with the Aurora Constitution, the Constitution takes precedence.

If this specification conflicts with the AFL Overview, Scene Model, Shot Model, Emotion Model or Camera Model, the conflict must be reviewed before implementation begins.

This document defines the conceptual Composition model only.

Implementation requires later data, API, event and test specifications.

---

## 3. Scope

This specification defines:

- What AFL Composition is
- What AFL Composition is not
- Composition responsibility
- Composition ownership and inheritance expectations
- Subject placement
- Foreground, midground and background
- Depth intent
- Balance intent
- Negative space
- Visual hierarchy
- Attention path
- Symbolic placement
- Spatial tension
- Relationship to Scene, Shot, Emotion, Camera, Motion, Symbol and Prompt Export Intent
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
- GUI composition editor
- Image generation prompt syntax
- Video generation prompt syntax
- Physical camera simulation
- Automatic layout generation
- Computer vision analysis
- Provider-specific composition tags
- Render pipeline
- Plugin SDK behavior
- Persistence format
- Validation code
- Implementation code

Those topics require later specifications.

---

## 5. Definitions

| Term | Meaning |
|---|---|
| Composition | Structured arrangement of visual elements inside the frame. |
| Composition Intent | The intended visual arrangement and meaning of the frame. |
| Subject Placement | The position and visual role of the main subject. |
| Foreground | Elements closest to the viewer or visually in front of the subject. |
| Midground | Elements occupying the middle visual plane. |
| Background | Elements behind the subject that may carry context or meaning. |
| Depth Intent | The intended use of distance, layers and spatial separation. |
| Balance Intent | The intended visual stability or instability of the frame. |
| Negative Space | Empty or visually quiet space used as meaning, rhythm or attention control. |
| Visual Hierarchy | The order in which visual elements should attract attention. |
| Attention Path | The intended movement of viewer attention through the frame. |
| Symbolic Placement | The meaningful position of symbolic elements inside the composition. |
| Spatial Tension | Visual pressure created through placement, imbalance, distance or obstruction. |

---

## 6. Composition Responsibility

Composition is responsible for representing visual arrangement as meaning.

Composition may influence:

- Scene Visual Strategy
- Shot Purpose
- Subject Focus
- Camera Intent
- Emotion
- Symbolic Layer
- Motion Intent
- Transition Intent
- Prompt Export Intent
- Review and validation

Composition must not own provider-specific prompt syntax.

Composition must not directly know how a specific AI model interprets layout words.

Composition must not become uncontrolled descriptive text.

Composition must preserve visual meaning independently of output format.

---

## 7. Composition Is Not A Generic Style Word

Bad composition instruction:

```text
Beautiful composition.
```

Better composition instruction:

```text
The character is placed small in the lower-right of the frame while the empty station dominates the background, making the return feel impersonal.
```

Aurora may later export composition meaning into prompt text.

The prompt is output.

The structured Composition Intent is source meaning.

---

## 8. Composition Levels

AFL may support Composition Intent at multiple levels:

1. Film-level visual arrangement language
2. Sequence-level composition pattern
3. Scene-level composition strategy
4. Shot-level composition intent
5. Symbol-level placement
6. Character-level placement
7. Transition composition intent
8. Export-specific composition emphasis

Not every level is required for every project.

A future data specification must define exact field names and allowed structures.

---

## 9. Subject Placement

Subject Placement defines where the primary subject appears and what that placement means.

Subject Placement may include:

- Center placement
- Off-center placement
- Edge placement
- Lower-frame placement
- Upper-frame placement
- Foreground placement
- Background placement
- Obscured placement
- Isolated placement
- Crowded placement

Subject Placement should connect position to meaning when relevant.

---

## 10. Foreground, Midground and Background

Composition may define the use of visual layers.

Foreground may create intimacy, obstruction, secrecy or depth.

Midground may carry action or subject focus.

Background may carry context, threat, history, symbolism or scale.

Layering must be explicit when it affects meaning or export.

---

## 11. Depth Intent

Depth Intent defines how spatial depth contributes to meaning.

Depth may communicate:

- Isolation
- Distance
- Memory
- Scale
- Threat
- Intimacy
- Separation
- Discovery
- Hidden information

Depth Intent must not be confused with camera distance.

Camera defines viewpoint.

Composition defines arrangement inside that viewpoint.

---

## 12. Balance Intent

Balance Intent defines visual stability or instability.

Composition may be:

- Symmetrical
- Asymmetrical
- Balanced
- Unbalanced
- Center-weighted
- Edge-weighted
- Heavy on foreground
- Heavy on background
- Visually calm
- Visually tense

Balance must be linked to emotion or meaning when important.

---

## 13. Negative Space

Negative Space is empty or visually quiet space used intentionally.

Negative Space may communicate:

- Loneliness
- Threat
- Absence
- Waiting
- Emotional distance
- Powerlessness
- Silence
- Time passing

Negative Space must be preserved when meaning-critical.

Provider plugins must not fill negative space with decorative detail unless export rules allow it.

---

## 14. Visual Hierarchy

Visual Hierarchy defines what the viewer should notice first, second and later.

Hierarchy may involve:

- Subject size
- Light
- Contrast
- Color
- Focus
- Movement
- Placement
- Symbolic importance
- Foreground obstruction
- Background dominance

Visual Hierarchy is required when multiple important elements exist.

---

## 15. Attention Path

Attention Path defines how the viewer's eye should move.

Examples:

- From face to object
- From empty doorway to character
- From foreground symbol to distant figure
- From bright window to dark corner
- From moving subject to still background

Attention Path must be explicit when it affects reveal, suspense or symbolic meaning.

---

## 16. Symbolic Placement

Symbolic Placement defines where a symbol appears and why.

A symbol may be:

- Central
- Hidden
- Repeated
- Partially obscured
- In foreground
- In background
- Between characters
- Separating characters
- Aligned with a character
- Opposing a character

Symbolic Placement must not be accidental when the symbol carries defined meaning.

---

## 17. Spatial Tension

Spatial Tension is visual pressure created by arrangement.

It may involve:

- Distance between characters
- Barriers in frame
- Crowding
- Isolation
- Empty space
- Imbalance
- Visual compression
- Uncomfortable framing
- Obstruction
- Asymmetry

Spatial Tension should support Scene or Shot emotional intent.

---

## 18. Composition Inheritance

Composition may inherit from higher-level visual strategy:

```text
Film Visual Language
  ↓
Sequence Composition Pattern
  ↓
Scene Composition Strategy
  ↓
Shot Composition Intent
```

Inheritance must not create silent contradiction.

A lower-level override must be explicit and reviewable.

---

## 19. Composition Relationship To Camera

Camera defines viewpoint and behavior.

Composition defines arrangement inside the frame.

Camera distance, angle and movement may influence Composition, but they do not replace Composition.

Composition must remain independently reviewable when visual arrangement is meaning-critical.

---

## 20. Composition Relationship To Emotion

Composition may express or contrast emotion.

Examples:

- Empty space can express absence.
- Crowding can express pressure.
- Visual imbalance can express instability.
- Barriers can express separation.
- Small subject scale can express powerlessness.

Composition-emotion relationships must be explicit when they affect meaning.

---

## 21. Composition Relationship To Motion

Motion may change Composition over time.

Examples:

- A character enters empty space.
- Camera movement reveals symbolic background.
- A crowd closes around the subject.
- Light shifts attention from one plane to another.

A future Motion Model must define temporal movement in detail.

Composition must define the arrangement being changed or preserved.

---

## 22. Composition Relationship To Prompt Export Intent

Prompt Export Intent may use Composition structures to produce provider-specific prompt text.

Export may translate:

- Subject placement
- Foreground/background relationships
- Depth
- Negative space
- Visual hierarchy
- Symbolic placement
- Spatial tension

Prompt Export Intent must not replace Composition.

Provider-specific prompt wording is output, not source meaning.

---

## 23. Validation Expectations

Future validation should check:

1. Composition owner or level is clear.
2. Subject placement is defined when required.
3. Visual hierarchy is defined when multiple elements are important.
4. Symbolic placement is defined when symbols are meaning-critical.
5. Composition is compatible with Camera Intent.
6. Composition is compatible with Emotion Intent.
7. Negative space is preserved when meaning-critical.
8. Composition does not contain provider-specific syntax in core fields.
9. Composition can be saved and reviewed offline.

This specification does not define validation code.

---

## 24. Error Handling Expectations

Potential errors:

| Error Condition | Required Behavior |
|---|---|
| Missing required Composition Intent | Report incomplete composition structure. |
| Missing owner or level | Report unresolved composition ownership. |
| Composition contradicts Camera Intent | Report conflict requiring review. |
| Symbolic placement missing for meaning-critical symbol | Report incomplete symbolic arrangement. |
| Visual hierarchy unclear | Report ambiguity requiring review. |
| Provider-specific syntax found in Composition core | Report specification violation. |
| Composition is vague style text only | Report insufficient structure. |

Errors must not silently rewrite visual meaning.

---

## 25. Security Requirements

Composition data may contain private creative information, including story emphasis, symbolic meaning, visual design choices, hidden narrative signals and prompt export intent.

Provider plugins must receive only Composition data required for export or generation.

Composition data must not be sent to online providers unless the user initiates or approves an operation requiring it.

---

## 26. Offline-First Requirements

Composition creation, editing, saving, loading, validation and review must work offline whenever technically possible.

Composition structure must not require Internet access.

Online generation may use Composition during export, but the Composition model itself must remain local and usable.

---

## 27. Testing Requirements

Future Composition implementation must include tests for:

- Composition creation
- Owner validation
- Subject placement validation
- Foreground/midground/background validation
- Visual hierarchy validation
- Symbolic placement validation
- Camera compatibility checks
- Emotion compatibility checks
- Provider-specific syntax isolation
- Offline save/load behavior
- Backward compatibility for versioned Composition data

This specification does not create test files.

---

## 28. Example Conceptual Composition Intent

```text
Composition Owner:
Shot: Hand on the Door Handle

Subject Placement:
The hand is placed in the lower third.

Foreground:
No foreground obstruction.

Background:
Old scratched door texture dominates the frame.

Depth Intent:
Flat, compressed space to make the moment feel trapped.

Visual Hierarchy:
Viewer notices the hand first, then the worn door surface.

Symbolic Placement:
The locked door represents the past resisting entry.

Emotional Relationship:
The frame should feel still, heavy and restrained.
```

This example is not a schema.

---

## 29. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This specification defines the conceptual Composition model only.

Implementation cannot begin until data, API, event and test specifications exist and are reviewed.

---

## 30. Acceptance Criteria

This specification is acceptable when:

1. Composition purpose is defined.
2. Composition non-scope is explicit.
3. Composition responsibility is defined.
4. Composition is separated from vague style words.
5. Composition levels are defined.
6. Subject Placement is defined.
7. Foreground, midground and background are defined.
8. Depth Intent is defined.
9. Balance Intent is defined.
10. Negative Space is defined.
11. Visual Hierarchy is defined.
12. Attention Path is defined.
13. Symbolic Placement is defined.
14. Spatial Tension is defined.
15. Relationships to Camera, Emotion, Motion and Prompt Export Intent are defined.
16. Validation expectations are defined.
17. Error handling expectations are defined.
18. Security expectations are defined.
19. Offline-first expectations are defined.
20. Testing expectations are defined.
21. Implementation readiness is explicitly marked Not Ready.

---

## 31. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

---

## 32. Summary

The AFL Composition Model defines composition as structured visual arrangement.

Composition is not generic style text.

Composition preserves subject placement, depth, visual hierarchy, negative space and symbolic placement before export or generation.

Future implementation must build from approved data, API and test specifications.

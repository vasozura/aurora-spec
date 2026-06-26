# AFL Symbol Model Specification

Document ID: AFL-000007  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 06-AI/AFL-000007_SYMBOL_MODEL_SPEC.md  
Document Type: Aurora Film Language Specification  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, 01-Product/GLOSSARY.md, 01-Product/ROADMAP.md, 02-Architecture/ARCHITECTURE.md, 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md, 06-AI/AFL-000002_SCENE_MODEL_SPEC.md, 06-AI/AFL-000003_SHOT_MODEL_SPEC.md, 06-AI/AFL-000004_EMOTION_MODEL_SPEC.md, 06-AI/AFL-000005_CAMERA_MODEL_SPEC.md, 12-Templates/SPEC_TEMPLATE.md  

---

## 1. Purpose

This document defines the Aurora Film Language Symbol Model.

A Symbol is a visual, narrative, emotional or sonic element that carries meaning beyond its literal presence.

A Symbol may be an object, color, gesture, location detail, weather element, light source, sound motif, camera behavior, repeated composition, character action or environmental pattern.

Symbol is not decoration.

Symbol is not random prompt detail.

Symbol is structured meaning.

---

## 2. Authority

This specification is subordinate to the Aurora Constitution, AES, Review Standard, Architecture and prior AFL foundation documents.

If this specification conflicts with the Aurora Constitution, the Constitution takes precedence.

This document defines the conceptual Symbol model only.

Implementation requires later data, API, event and test specifications.

---

## 3. Scope

This specification defines:

- What AFL Symbol is
- What AFL Symbol is not
- Symbol responsibility
- Symbol identity expectations
- Symbol type
- Symbol meaning
- Symbol recurrence
- Symbol visibility
- Symbol relationship to Scene, Shot, Character Presence, Emotion, Composition, Camera, Motion, Transition and Prompt Export Intent
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
- GUI symbol editor
- Automatic symbolism detection
- Literary analysis engine
- Provider-specific prompt syntax
- Prompt export algorithm
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
| Symbol | A meaningful element that carries significance beyond literal presence. |
| Symbol Intent | The intended meaning and role of a symbol. |
| Symbol Type | The kind of symbol, such as object, color, sound, gesture or location detail. |
| Symbol Meaning | The interpretation or emotional/narrative role attached to the symbol. |
| Recurring Symbol | A symbol that appears across multiple scenes, shots or sequences. |
| Symbol Visibility | How obvious or hidden the symbol should be. |
| Symbol Anchor | A stable reference that identifies the symbol across the project. |
| Symbol Transformation | A change in symbol meaning, appearance or context over time. |
| Symbolic Placement | The meaningful placement of a symbol inside composition. |

---

## 6. Symbol Responsibility

Symbol is responsible for representing repeatable or meaningful elements.

Symbol may influence:

- Scene Purpose
- Scene Symbolic Layer
- Shot Purpose
- Character Presence
- Emotion
- Composition
- Camera
- Motion
- Transition
- Prompt Export Intent
- Review and validation

Symbol must not own provider-specific prompt syntax.

Symbol must not become uncontrolled decorative detail.

Symbol must preserve meaning independently of output format.

---

## 7. Symbol Is Not Decoration

Bad symbol instruction:

```text
Add a red umbrella for style.
```

Better symbol instruction:

```text
The red umbrella appears as the only warm object in cold rain and represents the memory the character refuses to abandon.
```

A symbol must have meaning, recurrence rule or intentional visual function.

If an object has no meaning beyond literal scene description, it may be a prop or detail, not a Symbol.

---

## 8. Symbol Types

Conceptual symbol types may include:

- Object symbol
- Color symbol
- Gesture symbol
- Location symbol
- Weather symbol
- Light symbol
- Sound symbol
- Camera symbol
- Composition symbol
- Motion symbol
- Character symbol
- Costume symbol
- Environmental symbol
- Text or sign symbol

This list is not final.

A future data specification may define controlled values.

---

## 9. Symbol Identity

Every reusable Symbol should have stable identity.

At conceptual level, a Symbol may require:

- Symbol ID
- Human-readable name
- Symbol type
- Meaning
- Project relationship
- Optional Scene or Sequence relationship
- Recurrence rule
- Version or revision information

Symbol identity must not depend on prompt text or provider output.

---

## 10. Symbol Meaning

Symbol Meaning defines what the symbol represents.

It may include:

- Emotional meaning
- Narrative meaning
- Character meaning
- Memory meaning
- Theme meaning
- Relationship meaning
- Time meaning
- Location meaning
- Transformation meaning

Symbol Meaning must be explicit when the symbol affects story, continuity, composition or export.

---

## 11. Symbol Visibility

Symbol Visibility defines how obvious the symbol should be.

Possible conceptual values:

- Hidden
- Subtle
- Noticeable
- Dominant
- Repeated
- Revealed later
- Misleading
- Ambiguous

Visibility is separate from importance.

A subtle symbol may be extremely important.

---

## 12. Symbol Recurrence

Symbol Recurrence defines whether and how a symbol repeats.

Recurrence may include:

- Single appearance
- Repeated appearance
- Escalating appearance
- Fading appearance
- Transformed appearance
- Hidden recurrence
- Final payoff
- False recurrence

Recurring symbols must be traceable across scenes or shots.

---

## 13. Symbol Transformation

Symbol Transformation defines how symbol meaning changes over time.

Examples:

- A key first represents hope, later imprisonment.
- Rain first represents cleansing, later isolation.
- A song first represents memory, later loss.
- A window first represents escape, later separation.

Transformation must be explicit when it affects continuity or interpretation.

---

## 14. Symbol Relationship To Scene

A Scene may contain a Symbolic Layer.

Scene-level symbols may define:

- Symbol presence
- Symbol meaning in the Scene
- Visibility
- Relationship to Scene Purpose
- Relationship to Emotional Arc
- Relationship to Character Presence
- Relationship to Transition Intent

Scene symbols must not be invented by provider plugins.

---

## 15. Symbol Relationship To Shot

A Shot may include or emphasize symbols.

Shot-level symbol use may define:

- Symbol focus
- Symbol placement
- Symbol visibility
- Symbol motion
- Symbol relationship to subject
- Symbol relationship to camera
- Symbol relationship to duration

Shot-level symbol use must remain consistent with Scene-level Symbolic Layer unless intentionally overridden.

---

## 16. Symbol Relationship To Emotion

Symbols may carry emotional meaning.

Examples:

- A broken clock may carry grief or stopped time.
- A warm window may carry unreachable safety.
- A repeated song may carry memory.
- Empty shoes may carry absence.

Symbol-emotion relationship must be explicit when meaning-critical.

---

## 17. Symbol Relationship To Composition

Symbolic Placement defines where the symbol appears and why.

A symbol may be central, hidden, repeated, foregrounded, backgrounded, between characters or visually aligned with a character.

Composition must preserve Symbolic Placement when it affects meaning.

---

## 18. Symbol Relationship To Camera And Motion

Camera may reveal, hide or emphasize a symbol.

Motion may transform how a symbol is perceived.

Examples:

- Camera slowly reveals a symbol.
- A symbol remains still while everything else moves.
- A character moves away from a symbol.
- A symbol enters frame at the emotional turning point.

These relationships must be explicit when meaning-critical.

---

## 19. Symbol Relationship To Transition

Symbols may connect shots, scenes or sequences.

Examples:

- Match cut from one symbol to another.
- Sound symbol carries into the next Scene.
- Object symbol appears in final shot as payoff.
- Color symbol changes across scenes.

Symbol-based transitions must be explicit when they guide structure.

---

## 20. Symbol Relationship To Prompt Export Intent

Prompt Export Intent may translate Symbol structures into provider-specific prompt text.

Export may translate:

- Symbol type
- Symbol meaning
- Symbol visibility
- Symbol placement
- Symbol recurrence
- Symbol transformation
- Symbol importance

Prompt Export Intent must not replace Symbol.

Provider-specific wording is output, not source meaning.

---

## 21. Validation Expectations

Future validation should check:

1. Symbol owner or scope is clear.
2. Symbol type is defined.
3. Symbol meaning is defined when symbol is marked meaning-critical.
4. Recurrence is defined for recurring symbols.
5. Symbol placement is defined when composition-critical.
6. Symbol visibility is defined when export-critical.
7. Symbol does not contain provider-specific syntax in core fields.
8. Symbol can be saved and reviewed offline.

This specification does not define validation code.

---

## 22. Error Handling Expectations

Potential errors:

| Error Condition | Required Behavior |
|---|---|
| Missing Symbol meaning | Report incomplete Symbol when meaning-critical. |
| Missing Symbol type | Report incomplete Symbol structure. |
| Recurring Symbol without recurrence rule | Report continuity risk. |
| Symbol appears inconsistently without transformation rule | Report ambiguity requiring review. |
| Provider-specific syntax found in Symbol core | Report specification violation. |
| Symbol is decorative text only | Report insufficient structure if marked Symbol. |

Errors must not silently rewrite symbolic meaning.

---

## 23. Security Requirements

Symbol data may reveal private story meaning, hidden themes, character secrets or future narrative payoffs.

Provider plugins must receive only Symbol data required for export or generation.

Symbol data must not be sent to online providers unless the user initiates or approves an operation requiring it.

---

## 24. Offline-First Requirements

Symbol creation, editing, saving, loading, validation and review must work offline whenever technically possible.

Symbol structure must not require Internet access.

---

## 25. Testing Requirements

Future Symbol implementation must include tests for:

- Symbol creation
- Symbol identity stability
- Symbol type validation
- Symbol meaning validation
- Symbol recurrence validation
- Symbol transformation validation
- Symbol placement validation
- Provider-specific syntax isolation
- Offline save/load behavior
- Backward compatibility for versioned Symbol data

This specification does not create test files.

---

## 26. Example Conceptual Symbol

```text
Symbol Name:
Old Streetlamp

Symbol Type:
Light symbol / location symbol

Meaning:
The streetlamp represents memory that survived while the character changed.

Visibility:
Subtle but repeated.

Recurrence:
Appears in the opening Scene and final Scene.

Transformation:
At first it feels nostalgic. In the final Scene it feels indifferent.

Composition Relationship:
Usually placed in background above the character.

Emotion Relationship:
Carries quiet resignation.
```

This example is not a schema.

---

## 27. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This specification defines the conceptual Symbol model only.

Implementation cannot begin until data, API, event and test specifications exist and are reviewed.

---

## 28. Acceptance Criteria

This specification is acceptable when:

1. Symbol purpose is defined.
2. Symbol non-scope is explicit.
3. Symbol responsibility is defined.
4. Symbol is separated from decoration.
5. Symbol types are defined.
6. Symbol identity is defined.
7. Symbol meaning is defined.
8. Symbol visibility is defined.
9. Symbol recurrence is defined.
10. Symbol transformation is defined.
11. Relationships to Scene, Shot, Emotion, Composition, Camera, Motion, Transition and Prompt Export Intent are defined.
12. Validation expectations are defined.
13. Error handling expectations are defined.
14. Security expectations are defined.
15. Offline-first expectations are defined.
16. Testing expectations are defined.
17. Implementation readiness is explicitly marked Not Ready.

---

## 29. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

---

## 30. Summary

The AFL Symbol Model defines symbols as structured meaning, not decoration.

Symbols may be objects, colors, gestures, sounds, locations, weather, light, camera behaviors or recurring visual motifs.

Future implementation must build from approved data, API and test specifications.

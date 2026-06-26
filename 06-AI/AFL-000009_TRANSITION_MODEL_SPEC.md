# AFL Transition Model Specification

Document ID: AFL-000009  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 06-AI/AFL-000009_TRANSITION_MODEL_SPEC.md  
Document Type: Aurora Film Language Specification  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, 01-Product/GLOSSARY.md, 01-Product/ROADMAP.md, 02-Architecture/ARCHITECTURE.md, 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md, 06-AI/AFL-000002_SCENE_MODEL_SPEC.md, 06-AI/AFL-000003_SHOT_MODEL_SPEC.md, 06-AI/AFL-000004_EMOTION_MODEL_SPEC.md, 06-AI/AFL-000005_CAMERA_MODEL_SPEC.md, 12-Templates/SPEC_TEMPLATE.md  

---

## 1. Purpose

This document defines the Aurora Film Language Transition Model.

A Transition defines the relationship between cinematic units.

A Transition may connect shots, scenes, sequences, emotional states, time periods, locations, symbols, sound states or visual ideas.

Transition is not only an edit effect.

Transition is structured cinematic relationship.

---

## 2. Authority

This specification is subordinate to the Aurora Constitution, AES, Review Standard, Architecture and prior AFL foundation specifications.

If this specification conflicts with the Aurora Constitution, the Constitution takes precedence.

This document defines the conceptual Transition model only.

Implementation requires later data, API, event and test specifications.

---

## 3. Scope

This specification defines:

- What AFL Transition is
- What AFL Transition is not
- Transition responsibility
- Transition types
- Incoming and outgoing transitions
- Visual transition
- Emotional transition
- Narrative transition
- Symbolic transition
- Motion transition
- Sound transition
- Time transition
- Location transition
- Continuity and contrast
- Relationship to Scene, Shot, Emotion, Symbol, Camera, Composition, Motion and Prompt Export Intent
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
- GUI timeline transition editor
- Video editing engine effects
- Render pipeline
- Exact cut/fade implementation
- Provider-specific prompt syntax
- Prompt export algorithm
- Plugin SDK behavior
- Persistence format
- Validation code
- Implementation code

Those topics require later specifications.

---

## 5. Definitions

| Term | Meaning |
|---|---|
| Transition | Structured relationship between two cinematic units. |
| Source Unit | The unit from which the transition begins. |
| Target Unit | The unit into which the transition leads. |
| Incoming Transition | How a unit is entered. |
| Outgoing Transition | How a unit is left. |
| Visual Transition | A visual relationship or change between units. |
| Emotional Transition | Emotional continuation, rupture, reversal or release between units. |
| Narrative Transition | Story relationship between units. |
| Symbolic Transition | Symbol-based connection or transformation. |
| Motion Transition | Movement-based connection or contrast. |
| Sound Transition | Sound bridge, rupture or change across units. |
| Temporal Transition | Time jump, compression, memory, flashback or time shift. |
| Spatial Transition | Location change or spatial relationship between units. |

---

## 6. Transition Responsibility

Transition is responsible for representing how cinematic units relate.

Transition may influence:

- Scene structure
- Shot ordering
- Timeline rhythm
- Emotional continuity
- Symbol recurrence
- Camera behavior
- Composition relationship
- Motion continuity
- Sound design
- Prompt Export Intent
- Review and validation

Transition must not own provider-specific prompt syntax.

Transition must not be reduced to editing effect names only.

Transition must preserve relationship meaning independently of output format.

---

## 7. Transition Is Not Only A Cut

Bad transition instruction:

```text
Cut to next scene.
```

Better transition instruction:

```text
Cut from the character's silence to an empty street, preserving the emotional absence rather than continuing the action.
```

The edit operation may be simple.

The transition meaning may be complex.

---

## 8. Transition Levels

AFL may support Transition Intent at multiple levels:

1. Shot-to-shot transition
2. Scene-to-scene transition
3. Sequence-to-sequence transition
4. Emotional transition
5. Symbolic transition
6. Sound transition
7. Time transition
8. Location transition
9. Export-specific transition emphasis

Not every level is required for every project.

---

## 9. Visual Transition

Visual Transition defines visual relationship between units.

It may include:

- Match cut
- Contrast cut
- Fade
- Dissolve
- Visual echo
- Shape match
- Color match
- Light change
- Object continuity
- Composition continuity
- Camera movement continuity
- Visual rupture

This specification does not define final edit operations.

It defines intent.

---

## 10. Emotional Transition

Emotional Transition defines how emotion moves between units.

It may include:

- Continuation
- Escalation
- Release
- Reversal
- Rupture
- Delay
- Echo
- Suppression
- False relief
- Emotional contradiction

Emotional Transition must be explicit when it affects interpretation.

---

## 11. Narrative Transition

Narrative Transition defines story relationship between units.

It may include:

- Cause and effect
- Time jump
- Consequence
- Memory
- Dream shift
- Parallel action
- Setup and payoff
- Revelation
- Ellipsis
- Change of perspective

Narrative Transition must not be guessed by provider plugins.

---

## 12. Symbolic Transition

Symbolic Transition uses symbols to connect or contrast units.

Examples:

- A lamp in one Scene becomes sunrise in the next.
- A song continues across locations.
- Rain transitions into shower water.
- A locked door transitions into a closed window.

Symbolic Transition must preserve symbolic meaning.

---

## 13. Motion Transition

Motion Transition uses movement to connect or contrast units.

Examples:

- Movement continues across a cut.
- A character's turn cuts to another character's turn.
- Camera push-in cuts to object close-up.
- Motion stops abruptly before silence.

Motion Transition must be compatible with Motion Intent and Camera Intent.

---

## 14. Sound Transition

Sound Transition defines sound relationship between units.

It may include:

- Sound bridge
- Sound cut
- Sound drop-out
- Music continuation
- Music interruption
- Ambient shift
- Voice carryover
- Silence bridge
- Repeated motif

This specification does not define audio implementation.

Sound Transition is cinematic intent.

---

## 15. Time Transition

Time Transition defines temporal relationship.

It may include:

- Immediate continuation
- Time jump
- Flashback
- Flashforward
- Memory shift
- Dream shift
- Time compression
- Time expansion
- Repeated moment
- Ambiguous time

Time Transition must be explicit when it affects story or continuity.

---

## 16. Location Transition

Location Transition defines spatial relationship.

It may include:

- Same location
- New location
- Parallel location
- Return to location
- Memory location
- Dream location
- Interior to exterior
- Exterior to interior
- Symbolic location shift

Location Transition must support narrative and visual continuity.

---

## 17. Continuity And Contrast

Transition may preserve continuity or create contrast.

Continuity may include:

- Emotional continuity
- Visual continuity
- Character continuity
- Motion continuity
- Sound continuity
- Symbol continuity
- Narrative continuity

Contrast may include:

- Emotional contrast
- Visual contrast
- Time contrast
- Sound contrast
- Motion contrast
- Symbol contrast

The intended relationship must be explicit.

---

## 18. Transition Relationship To Scene

Scene may define incoming and outgoing Transition Intent.

A Scene may require:

- Emotional entry
- Emotional exit
- Visual bridge
- Symbolic bridge
- Sound bridge
- Time relationship
- Location relationship

Scene transitions guide shot breakdown and export.

---

## 19. Transition Relationship To Shot

Shot transitions may define how adjacent shots relate.

They may include:

- Cut motivation
- Motion bridge
- Eye-line relationship
- Symbol continuation
- Camera continuity
- Emotional escalation
- Duration relationship

Shot transitions must support future timeline and editing workflows.

---

## 20. Transition Relationship To Emotion

Transition may carry emotional change.

Example:

```text
The Scene exits in unresolved grief and enters the next Scene with false calm.
```

Emotion transitions must be explicit when they affect interpretation.

---

## 21. Transition Relationship To Symbol

Symbols may bridge units.

Example:

```text
The old streetlamp is last seen in background, then the next Scene opens with a reflected light in a window.
```

Symbol transitions must be traceable when continuity matters.

---

## 22. Transition Relationship To Camera, Composition And Motion

Camera, Composition and Motion may support transition meaning.

Examples:

- Camera movement continues across a cut.
- Composition mirrors previous shot.
- Motion stops to create rupture.
- Negative space in one shot becomes physical absence in the next.

These relationships must be explicit when meaning-critical.

---

## 23. Transition Relationship To Prompt Export Intent

Prompt Export Intent may translate Transition structures into provider-specific prompt text or shot instructions.

Export may translate:

- Transition type
- Emotional relationship
- Visual relationship
- Motion relationship
- Sound relationship
- Symbol relationship
- Time relationship
- Location relationship

Prompt Export Intent must not replace Transition.

---

## 24. Validation Expectations

Future validation should check:

1. Source unit is defined when required.
2. Target unit is defined when required.
3. Transition type or relationship is clear.
4. Emotional transition is defined when emotion-critical.
5. Visual transition is defined when visual continuity matters.
6. Symbolic transition is defined when symbol continuity matters.
7. Motion transition is compatible with Motion Intent.
8. Sound transition is defined when sound continuity matters.
9. Transition does not contain provider-specific syntax in core fields.
10. Transition can be saved and reviewed offline.

This specification does not define validation code.

---

## 25. Error Handling Expectations

Potential errors:

| Error Condition | Required Behavior |
|---|---|
| Missing source or target unit | Report unresolved transition relationship. |
| Transition relationship unclear | Report ambiguity requiring review. |
| Emotional transition contradicts Scene emotion | Report conflict requiring review. |
| Symbolic transition references undefined Symbol | Report unresolved reference. |
| Motion transition conflicts with Motion Intent | Report conflict requiring review. |
| Provider-specific syntax found in Transition core | Report specification violation. |

Errors must not silently rewrite transition meaning.

---

## 26. Security Requirements

Transition data may reveal story structure, future payoffs, hidden symbolism, emotional design and private creative decisions.

Provider plugins must receive only Transition data required for export or generation.

Transition data must not be sent to online providers unless the user initiates or approves an operation requiring it.

---

## 27. Offline-First Requirements

Transition creation, editing, saving, loading, validation and review must work offline whenever technically possible.

Transition structure must not require Internet access.

---

## 28. Testing Requirements

Future Transition implementation must include tests for:

- Transition creation
- Source and target validation
- Emotional transition validation
- Visual transition validation
- Symbolic transition validation
- Motion transition validation
- Sound transition validation
- Time transition validation
- Provider-specific syntax isolation
- Offline save/load behavior
- Backward compatibility for versioned Transition data

This specification does not create test files.

---

## 29. Example Conceptual Transition

```text
Transition Owner:
Between Scene 3 and Scene 4

Source Unit:
Scene 3: The Bridge at Dawn

Target Unit:
Scene 4: Empty Apartment

Transition Type:
Emotional and visual bridge.

Emotional Transition:
Quiet resignation continues, but becomes more intimate.

Visual Transition:
Pale dawn light on bridge cuts to pale light through apartment window.

Sound Transition:
Distant city ambience continues under the cut.

Symbolic Transition:
The bridge as passage leads into the apartment as memory.
```

This example is not a schema.

---

## 30. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This specification defines the conceptual Transition model only.

Implementation cannot begin until data, API, event and test specifications exist and are reviewed.

---

## 31. Acceptance Criteria

This specification is acceptable when:

1. Transition purpose is defined.
2. Transition non-scope is explicit.
3. Transition responsibility is defined.
4. Transition is separated from simple edit effects.
5. Transition levels are defined.
6. Visual Transition is defined.
7. Emotional Transition is defined.
8. Narrative Transition is defined.
9. Symbolic Transition is defined.
10. Motion Transition is defined.
11. Sound Transition is defined.
12. Time Transition is defined.
13. Location Transition is defined.
14. Continuity and contrast are defined.
15. Relationships to Scene, Shot, Emotion, Symbol, Camera, Composition, Motion and Prompt Export Intent are defined.
16. Validation expectations are defined.
17. Error handling expectations are defined.
18. Security expectations are defined.
19. Offline-first expectations are defined.
20. Testing expectations are defined.
21. Implementation readiness is explicitly marked Not Ready.

---

## 32. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

---

## 33. Summary

The AFL Transition Model defines transitions as structured relationships between cinematic units.

Transition is not only a cut or effect.

Transition may carry emotional, visual, narrative, symbolic, motion, sound, time or location meaning.

Future implementation must build from approved data, API and test specifications.

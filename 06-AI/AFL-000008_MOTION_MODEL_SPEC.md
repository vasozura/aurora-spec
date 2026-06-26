# AFL Motion Model Specification

Document ID: AFL-000008  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 06-AI/AFL-000008_MOTION_MODEL_SPEC.md  
Document Type: Aurora Film Language Specification  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, 01-Product/GLOSSARY.md, 01-Product/ROADMAP.md, 02-Architecture/ARCHITECTURE.md, 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md, 06-AI/AFL-000002_SCENE_MODEL_SPEC.md, 06-AI/AFL-000003_SHOT_MODEL_SPEC.md, 06-AI/AFL-000004_EMOTION_MODEL_SPEC.md, 06-AI/AFL-000005_CAMERA_MODEL_SPEC.md, 12-Templates/SPEC_TEMPLATE.md  

---

## 1. Purpose

This document defines the Aurora Film Language Motion Model.

Motion in Aurora is structured cinematic movement.

Motion is not only physical movement.

Motion may represent character movement, object movement, camera movement, environmental movement, light movement, rhythm, emotional movement and transition movement.

Motion is not provider-specific prompt syntax.

Motion is cinematic intent.

---

## 2. Authority

This specification is subordinate to the Aurora Constitution, AES, Review Standard, Architecture and prior AFL foundation specifications.

If this specification conflicts with the Aurora Constitution, the Constitution takes precedence.

This document defines the conceptual Motion model only.

Implementation requires later data, API, event and test specifications.

---

## 3. Scope

This specification defines:

- What AFL Motion is
- What AFL Motion is not
- Motion responsibility
- Motion levels
- Character motion
- Object motion
- Camera motion
- Environmental motion
- Light motion
- Rhythm motion
- Emotional motion
- Motion direction
- Motion speed
- Motion continuity
- Motion relationship to Scene, Shot, Camera, Composition, Emotion, Symbol, Transition and Prompt Export Intent
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
- Animation engine
- Physics simulation
- Optical flow analysis
- Video stabilization algorithms
- Motion capture format
- Provider-specific motion prompt syntax
- Prompt export algorithm
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
| Motion | Structured representation of movement or movement intent. |
| Motion Intent | The intended movement and its meaning. |
| Character Motion | Movement performed by a character. |
| Object Motion | Movement of an object or prop. |
| Camera Motion | Movement of the camera viewpoint. |
| Environmental Motion | Movement of weather, crowd, water, smoke, light or background elements. |
| Emotional Motion | Emotional change expressed through movement or stillness. |
| Rhythm Motion | Repetition, cadence, acceleration, delay or pacing of movement. |
| Stillness | Intentional absence or near-absence of movement. |
| Motion Continuity | Consistency of movement across shots, scenes or transitions. |

---

## 6. Motion Responsibility

Motion is responsible for representing movement as meaning.

Motion may influence:

- Scene rhythm
- Shot purpose
- Character Presence
- Camera Intent
- Composition
- Emotion
- Symbol
- Transition
- Duration Intent
- Prompt Export Intent
- Review and validation

Motion must not own provider-specific prompt syntax.

Motion must not become uncontrolled descriptive text.

Motion must preserve meaning independently of output format.

---

## 7. Motion Is Not Just Movement

Bad motion instruction:

```text
Move slowly.
```

Better motion instruction:

```text
The character moves slowly because they are delaying the moment of entering the room.
```

Stillness may also be Motion Intent when it carries meaning.

---

## 8. Motion Levels

AFL may support Motion Intent at multiple levels:

1. Film-level movement language
2. Sequence-level movement rhythm
3. Scene-level motion strategy
4. Shot-level motion intent
5. Character motion
6. Object motion
7. Camera motion
8. Environmental motion
9. Transition motion
10. Export-specific motion emphasis

Not every level is required for every project.

---

## 9. Character Motion

Character Motion may include:

- Walking
- Turning
- Reaching
- Hesitating
- Freezing
- Retreating
- Approaching
- Falling
- Repeating action
- Small gesture
- Delayed movement
- Sudden movement

Character Motion should define meaning when relevant.

A gesture may carry more meaning than large movement.

---

## 10. Object Motion

Object Motion may include:

- Door opening
- Curtain moving
- Water dripping
- Paper falling
- Light flickering
- Vehicle passing
- Smoke drifting
- Object being carried
- Object being left behind

Object Motion may be symbolic or narrative.

---

## 11. Camera Motion

Camera Motion is one part of Motion but is also defined in the Camera Model.

This Motion specification references camera movement as movement behavior.

The Camera Model defines camera viewpoint and motivation in more detail.

Camera Motion must not silently conflict with Camera Intent.

---

## 12. Environmental Motion

Environmental Motion may include:

- Rain
- Snow
- Wind
- Smoke
- Dust
- Fire
- Water
- Crowd movement
- Traffic
- Shadows
- Reflections
- Light changes

Environmental Motion may define atmosphere, time, threat, memory or emotional pressure.

---

## 13. Light Motion

Light Motion may include:

- Flicker
- Dawn shift
- Passing headlights
- Moving shadows
- Neon pulse
- Firelight movement
- Reflected light movement

Light Motion may connect to emotion, symbol or transition.

---

## 14. Rhythm Motion

Rhythm Motion defines movement cadence.

It may include:

- Slow
- Delayed
- Repetitive
- Escalating
- Interrupted
- Sudden
- Still
- Pulsing
- Fading
- Mechanical
- Organic

Rhythm Motion may relate to editing rhythm and duration.

---

## 15. Emotional Motion

Emotional Motion represents emotional change through movement.

Examples:

- Stillness after shock
- Slow retreat after rejection
- Repeated hand movement from anxiety
- Sudden step forward from decision
- Motion fading as hope disappears

Emotional Motion must connect physical behavior to emotional meaning.

---

## 16. Motion Direction

Motion Direction may describe where movement goes.

Examples:

- Toward subject
- Away from subject
- Across frame
- Into depth
- Out of frame
- Upward
- Downward
- Circular
- Returning
- Collapsing inward
- Expanding outward

Direction must be explicit when it affects composition, continuity or meaning.

---

## 17. Motion Speed

Motion Speed may be conceptual rather than exact.

Possible conceptual values:

- Still
- Almost still
- Slow
- Moderate
- Fast
- Sudden
- Accelerating
- Decelerating
- Uneven
- Repetitive
- Interrupted

Exact timing belongs to later data or timeline specifications.

---

## 18. Motion Continuity

Motion Continuity defines consistency across shots or scenes.

It may include:

- Screen direction
- Character movement continuity
- Object movement continuity
- Camera movement continuity
- Rhythm continuity
- Motion contrast
- Motion bridge
- Interrupted motion

Motion Continuity must be explicit when it affects editing or export.

---

## 19. Motion Relationship To Scene

Scene-level Motion Intent may define:

- Overall movement energy
- Stillness
- Escalation
- Repetition
- Environmental activity
- Emotional movement
- Transition into or out of the Scene

Scene-level Motion guides Shot-level Motion.

---

## 20. Motion Relationship To Shot

Shot-level Motion Intent may define:

- Character action
- Object action
- Camera movement
- Environmental movement
- Gesture detail
- Movement speed
- Movement direction
- Movement meaning

Shot-level Motion must be specific enough to guide review and export.

---

## 21. Motion Relationship To Camera

Camera Motion must be compatible with Camera Intent.

If Camera Intent says static but Motion says push-in, the conflict must be reviewed.

Camera Motion may express emotion, reveal information or control rhythm.

---

## 22. Motion Relationship To Composition

Motion may change composition over time.

Examples:

- Subject enters negative space.
- Symbol moves from background to foreground.
- Character crosses a visual barrier.
- Crowd closes around subject.

Motion and Composition must be compatible when both are meaning-critical.

---

## 23. Motion Relationship To Emotion

Motion may express, hide or contradict emotion.

Examples:

- Stillness can express shock.
- Slow motion can express hesitation.
- Sudden motion can express rupture.
- Repetition can express obsession.

Motion-emotion relationship must be explicit when it affects meaning.

---

## 24. Motion Relationship To Symbol

A symbol may move, remain still or be revealed through movement.

Motion may transform symbolic meaning.

Example:

```text
The red umbrella is carried away by wind, turning memory into loss.
```

Symbol-motion relationships must be explicit when meaning-critical.

---

## 25. Motion Relationship To Transition

Motion may connect or separate cinematic units.

Examples:

- Movement continues across a cut.
- Motion stops before a transition.
- Camera movement hides a time jump.
- Environmental motion bridges two scenes.

Transition Motion must be defined in later Transition specifications.

---

## 26. Motion Relationship To Prompt Export Intent

Prompt Export Intent may translate Motion structures into provider-specific prompt text.

Export may translate:

- Motion type
- Subject movement
- Camera movement
- Environmental movement
- Speed
- Direction
- Rhythm
- Stillness
- Continuity requirement

Prompt Export Intent must not replace Motion.

---

## 27. Validation Expectations

Future validation should check:

1. Motion owner or level is clear.
2. Required Motion Intent exists when movement is meaning-critical.
3. Motion direction is defined when needed.
4. Motion speed is defined when needed.
5. Camera Motion is compatible with Camera Intent.
6. Motion is compatible with Composition when composition changes over time.
7. Motion is compatible with Emotion when emotional movement is defined.
8. Motion does not contain provider-specific syntax in core fields.
9. Motion can be saved and reviewed offline.

This specification does not define validation code.

---

## 28. Error Handling Expectations

Potential errors:

| Error Condition | Required Behavior |
|---|---|
| Missing required Motion Intent | Report incomplete motion structure. |
| Missing owner or level | Report unresolved motion ownership. |
| Camera Motion conflicts with Camera Intent | Report conflict requiring review. |
| Motion direction missing where continuity requires it | Report incomplete continuity. |
| Motion contradicts emotional intent without explanation | Report ambiguity requiring review. |
| Provider-specific syntax found in Motion core | Report specification violation. |

Errors must not silently rewrite motion meaning.

---

## 29. Security Requirements

Motion data may reveal private creative information, including story beats, emotional design, scene rhythm, symbolic transformation and generation intent.

Provider plugins must receive only Motion data required for export or generation.

Motion data must not be sent to online providers unless the user initiates or approves an operation requiring it.

---

## 30. Offline-First Requirements

Motion creation, editing, saving, loading, validation and review must work offline whenever technically possible.

Motion structure must not require Internet access.

---

## 31. Testing Requirements

Future Motion implementation must include tests for:

- Motion creation
- Owner validation
- Character Motion validation
- Object Motion validation
- Camera Motion compatibility
- Environmental Motion validation
- Speed and direction validation
- Motion continuity validation
- Provider-specific syntax isolation
- Offline save/load behavior
- Backward compatibility for versioned Motion data

This specification does not create test files.

---

## 32. Example Conceptual Motion Intent

```text
Motion Owner:
Shot: Hand on the Door Handle

Character Motion:
The fingers slowly tighten around the handle.

Camera Motion:
Static.

Environmental Motion:
No visible environmental motion.

Motion Speed:
Slow, delayed.

Emotional Motion:
The lack of movement should feel like fear being contained.

Continuity:
The hand must remain in the same position until the next Shot begins.
```

This example is not a schema.

---

## 33. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This specification defines the conceptual Motion model only.

Implementation cannot begin until data, API, event and test specifications exist and are reviewed.

---

## 34. Acceptance Criteria

This specification is acceptable when:

1. Motion purpose is defined.
2. Motion non-scope is explicit.
3. Motion responsibility is defined.
4. Motion is separated from generic movement words.
5. Motion levels are defined.
6. Character Motion is defined.
7. Object Motion is defined.
8. Camera Motion is defined.
9. Environmental Motion is defined.
10. Light Motion is defined.
11. Rhythm Motion is defined.
12. Emotional Motion is defined.
13. Motion Direction is defined.
14. Motion Speed is defined.
15. Motion Continuity is defined.
16. Relationships to Scene, Shot, Camera, Composition, Emotion, Symbol, Transition and Prompt Export Intent are defined.
17. Validation expectations are defined.
18. Error handling expectations are defined.
19. Security expectations are defined.
20. Offline-first expectations are defined.
21. Testing expectations are defined.
22. Implementation readiness is explicitly marked Not Ready.

---

## 35. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

---

## 36. Summary

The AFL Motion Model defines movement as structured cinematic intent.

Motion may include character, object, camera, environment, light, rhythm, emotion and transition.

Future implementation must build from approved data, API and test specifications.

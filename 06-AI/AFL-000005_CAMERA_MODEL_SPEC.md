# AFL Camera Model Specification

Document ID: AFL-000005  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 06-AI/AFL-000005_CAMERA_MODEL_SPEC.md  
Document Type: Aurora Film Language Specification  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, 01-Product/GLOSSARY.md, 01-Product/ROADMAP.md, 02-Architecture/ARCHITECTURE.md, 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md, 06-AI/AFL-000002_SCENE_MODEL_SPEC.md, 06-AI/AFL-000003_SHOT_MODEL_SPEC.md, 06-AI/AFL-000004_EMOTION_MODEL_SPEC.md, 12-Templates/SPEC_TEMPLATE.md  

---

## 1. Purpose

This document defines the Aurora Film Language Camera Model.

Camera in Aurora is structured cinematic intent.

Camera is not a vague style word.

Camera is not provider-specific prompt syntax.

Camera is not a physical camera simulation unless a later specification explicitly defines that behavior.

Camera represents the intended relationship between viewer, subject, space, movement, attention, emotion and meaning.

The Camera Model exists so Aurora can describe camera angle, distance, perspective, movement, stability, focus and motivation before those choices are exported to prompts, provider requests, shot lists, storyboards or future timeline structures.

---

## 2. Authority

This specification is subordinate to:

- 00-Governance/AURORA_CONSTITUTION.md
- 00-Governance/AURORA_ENGINEERING_STANDARD.md
- 00-Governance/REVIEW_STANDARD.md
- 02-Architecture/ARCHITECTURE.md
- 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md
- 06-AI/AFL-000002_SCENE_MODEL_SPEC.md
- 06-AI/AFL-000003_SHOT_MODEL_SPEC.md
- 06-AI/AFL-000004_EMOTION_MODEL_SPEC.md

If this specification conflicts with the Aurora Constitution, the Constitution takes precedence.

If this specification conflicts with the AFL Overview, Scene Model, Shot Model or Emotion Model, the conflict must be reviewed before implementation begins.

This document defines the conceptual Camera model only.

Implementation requires later data, API, event and test specifications.

---

## 3. Scope

This specification defines:

- What AFL Camera is
- What AFL Camera is not
- Camera responsibility
- Camera ownership and inheritance expectations
- Camera level usage
- Camera angle intent
- Camera distance intent
- Camera perspective intent
- Camera movement intent
- Camera stability intent
- Camera focus intent
- Camera subject relationship
- Camera motivation
- Camera relationship to Scene
- Camera relationship to Shot
- Camera relationship to Emotion
- Camera relationship to Composition
- Camera relationship to Motion
- Camera relationship to Prompt Export Intent
- Validation expectations
- Error handling expectations
- Offline-first expectations
- Security expectations
- Testing expectations
- Implementation readiness

This specification applies to:

- Aurora Film Language
- Future AFL Engine module
- Future Scene Manager module
- Future Shot Manager module
- Future Timeline Manager module
- Future Prompt Export Manager module
- Future provider export plugins
- Future data specifications
- Future interface specifications
- Future implementation tasks

---

## 4. Non-Scope

This specification does not define:

- Python classes
- JSON schema
- Database schema
- GUI camera editor
- Physical lens simulation
- Real-world camera calibration
- 3D camera rig implementation
- Video stabilization algorithms
- Full Composition model
- Full Motion model
- Provider-specific camera prompt syntax
- Prompt export algorithm
- Video generation API calls
- Render pipeline
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
| Camera | The structured AFL representation of viewer perspective, framing behavior and camera intent. |
| Camera Intent | The intended camera behavior and meaning for a Scene or Shot. |
| Camera Angle | The vertical or horizontal relationship between camera and subject. |
| Camera Distance | The perceived distance between viewer and subject. |
| Camera Perspective | The visual and emotional viewpoint created by camera placement and relationship. |
| Camera Movement | The intended movement of the camera during a Shot or Scene. |
| Camera Stability | The intended steadiness or instability of the camera. |
| Focus Intent | The intended behavior of visual focus and viewer attention. |
| Subject Relationship | The relationship between camera and primary subject. |
| Camera Motivation | The reason the camera behaves in a specific way. |
| Viewer Position | The implied place or role of the viewer created by the camera. |
| Camera Override | A lower-level Camera Intent that intentionally differs from inherited camera guidance. |

---

## 6. Camera Responsibility

The Camera Model is responsible for representing camera meaning in a structured way.

Camera may influence:

- Shot Purpose
- Subject Focus
- Framing Intent
- Composition Intent
- Motion Intent
- Emotional Intent
- Visual Detail Intent
- Duration Intent
- Transition Intent
- Prompt Export Intent
- Review and validation

Camera must not own provider-specific prompt syntax.

Camera must not directly know how a specific AI video model interprets camera language.

Camera must not become uncontrolled descriptive text.

Camera must preserve meaning independently of output format.

---

## 7. Camera Is Not A Generic Style Word

Camera must not be reduced to vague prompt decoration.

Bad camera instruction:

```text
Cinematic camera, professional shot.
```

Better camera instruction:

```text
Static wide camera keeps the character small against the empty station, making the return feel impersonal.
```

Aurora may later export camera meaning into prompt text.

The prompt is output.

The structured Camera Intent is source meaning.

---

## 8. Camera Levels

AFL may support Camera Intent at multiple levels.

Conceptual levels:

1. Film-level camera language
2. Sequence-level camera language
3. Scene-level camera strategy
4. Shot-level camera intent
5. Character-related camera intent
6. Transition camera intent
7. Export-specific camera emphasis

Not every level is required for every project.

A future data specification must define exact field names and allowed structures.

---

## 9. Film-Level Camera Language

Film-level camera language defines broad visual behavior across the work.

It may include:

- Overall camera restraint or intensity
- Dominant perspective style
- General movement philosophy
- Typical distance from characters
- Degree of subjectivity
- Degree of observational distance
- Recurring camera motif

Film-level camera language guides lower-level choices but must not override explicit Scene or Shot intent without review.

---

## 10. Scene-Level Camera Strategy

Scene-level Camera Strategy defines broad camera behavior for a Scene.

It may include:

- Overall camera distance pattern
- Movement pattern
- Stillness or instability
- Relationship to characters
- Relationship to location
- Emotional function
- Visual tension strategy
- Transition into or out of the Scene

Scene-level Camera Strategy guides Shot-level Camera Intent.

A Scene may be incomplete for shot breakdown if camera strategy is required but undefined.

---

## 11. Shot-Level Camera Intent

Shot-level Camera Intent defines the camera behavior for a specific Shot.

It may include:

- Camera angle
- Camera distance
- Camera movement
- Camera stability
- Focus behavior
- Subject relationship
- Perspective
- Viewer position
- Motivation
- Emotional effect
- Composition relationship
- Motion relationship
- Export emphasis

Shot-level Camera Intent must be specific enough to guide review and export.

Shot-level Camera Intent may inherit from Scene-level Camera Strategy.

Shot-level Camera Intent must not silently contradict Scene-level Camera Strategy.

---

## 12. Camera Angle Intent

Camera Angle Intent defines the camera's angular relationship to subject or space.

Conceptual angle categories may include:

- Eye-level
- Low angle
- High angle
- Overhead
- Ground-level
- Dutch angle
- Profile angle
- Three-quarter angle
- Over-the-shoulder
- Point-of-view
- Reverse angle

This list is not final.

A later data specification may define controlled values.

Angle must be linked to meaning when it affects interpretation.

Bad angle instruction:

```text
Low angle.
```

Better angle instruction:

```text
Low angle makes the closed door feel larger than the character.
```

---

## 13. Camera Distance Intent

Camera Distance Intent defines the perceived distance between viewer and subject.

Conceptual distance categories may include:

- Extreme wide
- Wide
- Full body
- Medium wide
- Medium
- Medium close
- Close-up
- Extreme close-up
- Insert detail
- Environmental distance

This list is not final.

A later data specification may define controlled values.

Distance must be connected to subject focus, emotion or composition when relevant.

---

## 14. Camera Perspective Intent

Camera Perspective Intent defines the viewer's relationship to the cinematic moment.

Perspective may be:

- Objective
- Subjective
- Observational
- Intimate
- Detached
- Voyeuristic
- Participatory
- Memory-like
- Dream-like
- Unreliable
- Witness-like

Perspective must be explicit when it affects meaning.

Perspective is not the same as camera angle.

A low angle may be objective, subjective or symbolic depending on intent.

---

## 15. Camera Movement Intent

Camera Movement Intent defines how the camera moves.

Conceptual movement categories may include:

- Static
- Push-in
- Pull-back
- Pan
- Tilt
- Tracking
- Dolly
- Crane-like movement
- Orbit
- Handheld drift
- Follow movement
- Reveal movement
- Reframe
- Locked-off stillness
- Sudden movement
- Slow movement
- Imperceptible movement

This list is not final.

Camera movement must include motivation when it affects meaning.

Bad movement instruction:

```text
Camera moves forward.
```

Better movement instruction:

```text
The camera slowly pushes in as the character realizes the room has not changed.
```

---

## 16. Camera Stability Intent

Camera Stability Intent defines the steadiness or instability of the camera.

Conceptual stability categories may include:

- Locked
- Stable
- Controlled
- Floating
- Slightly unstable
- Handheld
- Shaky
- Erratic
- Drifting
- Mechanically smooth

Stability must not be treated as only technical description.

Stability may communicate emotional state, memory, threat, intimacy or loss of control.

---

## 17. Focus Intent

Focus Intent defines how visual attention is controlled.

It may include:

- Primary focus target
- Secondary focus target
- Deep focus
- Shallow focus
- Focus shift
- Soft focus
- Sharp focus
- Delayed focus
- Uncertain focus
- Background focus
- Foreground focus

Focus Intent must be connected to viewer attention and meaning when relevant.

Provider limitations may affect export, but those limitations must not change the internal Camera Intent.

---

## 18. Subject Relationship

Subject Relationship defines how the camera relates to the subject.

It may include:

- Following the subject
- Observing the subject
- Confronting the subject
- Avoiding the subject
- Trapping the subject
- Isolating the subject
- Protecting the subject
- Invading the subject's space
- Sharing the subject's viewpoint
- Separating viewer from subject

Subject Relationship is part of cinematic meaning.

It must not be guessed by provider plugins.

---

## 19. Viewer Position

Viewer Position defines the implied role or location of the viewer.

Viewer Position may be:

- Outside observer
- Close witness
- Character viewpoint
- Hidden observer
- Memory participant
- Distant judge
- Physical participant
- Emotional participant

Viewer Position may influence angle, distance, perspective and composition.

Viewer Position must be explicit when it affects emotional or narrative meaning.

---

## 20. Camera Motivation

Camera Motivation defines why the camera behaves as specified.

Possible motivations:

- Reveal information
- Hide information
- Create intimacy
- Create distance
- Create threat
- Show power relationship
- Emphasize isolation
- Track realization
- Preserve ambiguity
- Build suspense
- Release tension
- Connect to symbol
- Reflect character state
- Contrast character state

Camera Motivation is required when camera behavior is non-obvious or meaning-critical.

Camera without motivation may still be valid for simple shots, but motivation improves review and export quality.

---

## 21. Camera Inheritance

Camera Intent may inherit from higher-level camera language.

Possible inheritance:

```text
Film Camera Language
  ↓
Sequence Camera Language
  ↓
Scene Camera Strategy
  ↓
Shot Camera Intent
```

Inheritance must not create silent contradiction.

A lower-level override must be explicit when it changes higher-level camera direction.

A future data specification must define how inheritance is represented.

---

## 22. Camera Override

Camera Override occurs when lower-level Camera Intent intentionally differs from inherited camera guidance.

Example:

```text
Scene Camera Strategy:
Mostly static and distant.

Shot Camera Intent:
Sudden close-up when the character hears the old song.
```

Overrides must explain why the difference exists.

Overrides must be reviewable.

Provider plugins must not invent overrides.

---

## 23. Camera Relationship To Scene

Scene-level Camera Strategy may define:

- Overall visual distance
- Movement philosophy
- Camera restraint or energy
- Relationship to emotional arc
- Relationship to location
- Relationship to symbols
- Transition camera behavior
- Shot breakdown guidance

Scene-level Camera Strategy should support Scene Purpose and Visual Strategy.

---

## 24. Camera Relationship To Shot

Shot-level Camera Intent may define:

- Camera angle
- Camera distance
- Camera movement
- Camera stability
- Focus behavior
- Subject relationship
- Viewer position
- Camera motivation
- Export emphasis

Shot-level Camera Intent should be specific enough to support generation or shot list export later.

---

## 25. Camera Relationship To Emotion

Camera may express, reinforce or contradict emotion.

Examples:

- Wide distance may express isolation.
- Close distance may express intimacy or pressure.
- Static camera may express restraint.
- Handheld camera may express instability.
- Slow push-in may express realization.
- High angle may express vulnerability.
- Low angle may express threat or weight.

Camera Emotion relationship must be explicit when it affects meaning.

Camera must not become a random style layer.

---

## 26. Camera Relationship To Composition

Camera and Composition are related but not identical.

Camera defines viewpoint and behavior.

Composition defines arrangement inside the frame.

Examples:

- Camera Distance affects Composition density.
- Camera Angle affects visual hierarchy.
- Camera Movement may change Composition over time.
- Focus Intent may guide Composition attention.

A later Composition Model must define composition rules in detail.

This Camera specification must not replace the Composition Model.

---

## 27. Camera Relationship To Motion

Camera Movement is one kind of Motion.

Motion may also include character, object, environment, light and rhythm.

Camera Movement must be distinguished from subject movement.

Example:

```text
Camera movement:
Static.

Subject movement:
Character slowly walks away from the table.
```

A later Motion Model must define motion rules in detail.

This Camera specification must not replace the Motion Model.

---

## 28. Camera Relationship To Transition

Camera may support transitions between shots or scenes.

Examples:

- Camera pulls back to end a Scene.
- Camera continues movement across a cut.
- Camera angle mirrors a previous shot.
- Camera stillness contrasts with the next Scene's instability.
- Camera movement hides a time jump.

Transition-related camera intent must be explicit when it affects continuity or meaning.

---

## 29. Camera Relationship To Prompt Export Intent

Prompt Export Intent may use Camera structures to produce provider-specific prompt text.

Export may translate:

- Camera angle
- Camera distance
- Camera movement
- Camera stability
- Focus intent
- Subject relationship
- Viewer position
- Camera motivation

Prompt Export Intent must not replace Camera.

Provider-specific prompt wording is output, not source meaning.

---

## 30. Camera Relationship To Provider Plugins

Provider plugins may consume Camera Intent through approved interfaces.

Provider plugins may translate Camera Intent into provider-specific output.

Provider plugins must not modify Camera core meaning directly.

Provider plugins must not introduce provider-specific fields into Camera core unless approved through specification and review.

Provider-specific camera extensions must be isolated.

Camera must remain provider-independent.

---

## 31. Camera Validation Expectations

Future validation should check:

1. Camera owner or level is clear.
2. Required Shot-level Camera Intent exists when needed.
3. Camera Intent is compatible with parent Scene camera strategy or has explicit override.
4. Camera angle is defined or explicitly inherited when required.
5. Camera distance is defined or explicitly inherited when required.
6. Camera movement is defined or explicitly not applicable when required.
7. Camera stability is defined or explicitly inherited when required.
8. Focus Intent is defined when focus is meaning-critical.
9. Subject Relationship is defined when it affects meaning.
10. Camera Motivation is defined when camera behavior is meaning-critical.
11. Camera does not contain provider-specific syntax in core fields.
12. Camera can be saved and reviewed offline.

This specification does not define validation code.

---

## 32. Camera Error Handling Expectations

Future implementation must handle Camera-related errors.

Potential errors:

| Error Condition | Required Behavior |
|---|---|
| Missing required Camera Intent | Report incomplete camera structure. |
| Missing camera owner or level | Report unresolved camera ownership. |
| Shot camera contradicts Scene camera without override | Report conflict requiring review. |
| Camera movement conflicts with Shot Motion Intent | Report conflict requiring review. |
| Camera distance conflicts with Subject Focus | Report ambiguity requiring review. |
| Provider-specific syntax found in Camera core | Report specification violation. |
| Camera instruction is vague style text only | Report insufficient structure. |
| Unsupported Camera data version | Require migration or compatibility handling. |

Errors must not silently rewrite camera meaning.

---

## 33. Camera Security Requirements

Camera data may contain private creative information.

Camera data may reveal:

- Story emphasis
- Character importance
- Hidden narrative meaning
- Emotional design
- Visual style decisions
- Prompt export intent
- Private creative references

Provider plugins must receive only Camera data required for export or generation.

Camera data must not be sent to online providers unless the user initiates or approves an operation requiring it.

Future security specifications must define plugin permissions.

---

## 34. Camera Offline-First Requirements

Camera creation, editing, saving, loading, validation and review must work offline whenever technically possible.

Camera structure must not require Internet access.

Camera structure must not require an online AI provider.

Online generation may use Camera Intent during export, but the Camera model itself must remain local and usable.

---

## 35. Camera Performance Expectations

Camera operations should be lightweight.

Expected lightweight operations:

- Create Camera Intent
- Edit Camera angle
- Edit Camera distance
- Edit Camera movement
- Edit Camera stability
- Edit Focus Intent
- Add Camera Motivation
- Link Camera to Scene
- Link Camera to Shot
- Validate required fields
- Save Camera data
- Load Camera data

Heavy operations, such as AI analysis of video or generated media, must not block basic Camera editing.

---

## 36. Camera Compatibility Expectations

Camera data must be versioned in future data specifications.

Compatibility expectations:

- Older Camera data should be migratable where technically possible.
- Unknown future fields should not corrupt current project data.
- Provider export artifacts must not become required to open Camera data.
- Camera meaning must remain separate from prompt output.

Breaking Camera data changes require an ADR.

---

## 37. Camera Relationships

Camera may relate to:

- Film
- Sequence
- Scene
- Shot
- Character Presence
- Emotion
- Composition
- Motion
- Transition
- Symbol
- Prompt Export Intent
- Provider Export Result
- Generated Media

Relationship rules must be defined in later data and interface specifications.

Camera must not directly mutate unrelated module data.

Cross-module changes must occur through approved interfaces.

---

## 38. Events

Future Camera operations may emit events.

Possible future events:

- CameraIntentCreated
- CameraIntentUpdated
- CameraAngleChanged
- CameraDistanceChanged
- CameraMovementChanged
- CameraStabilityChanged
- CameraFocusIntentChanged
- CameraMotivationChanged
- CameraOverrideCreated
- CameraValidationFailed
- CameraLinkedToScene
- CameraLinkedToShot

This specification does not define final event schemas.

Event schemas must be defined in later interface specifications.

---

## 39. Testing Requirements

Future Camera implementation must include tests.

Required future test areas:

- Camera Intent creation
- Camera owner validation
- Camera level validation
- Angle validation
- Distance validation
- Movement validation
- Stability validation
- Focus Intent validation
- Camera Motivation validation
- Camera inheritance behavior
- Camera override behavior
- Conflict detection between Scene and Shot camera intent
- Conflict detection with Motion Intent
- Provider-specific syntax isolation
- Offline save/load behavior
- Backward compatibility for versioned Camera data

This specification does not create test files.

Test specifications must be created before implementation.

---

## 40. AI Implementation Rules For Future Camera Tasks

Future AI implementation tasks for Camera must:

1. Reference this specification.
2. Reference the AFL Overview.
3. Reference the Scene Model Specification.
4. Reference the Shot Model Specification.
5. Reference the Emotion Model Specification.
6. Reference the future Camera data model.
7. Reference the future Camera API specification.
8. Reference applicable test specifications.
9. Define exact target files.
10. Define exact allowed files.
11. Forbid provider-specific logic unless explicitly required.
12. Forbid GUI behavior unless the task is a UI task.
13. Forbid database schema changes unless the task is a data task.
14. Require validation commands where applicable.

AI agents must not implement the Camera model directly from this conceptual specification alone.

---

## 41. Example Conceptual Camera Intent

The following is a conceptual example, not a schema.

```text
Camera Owner:
Shot: Hand on the Door Handle

Camera Angle:
Slightly low angle.

Camera Distance:
Close-up.

Camera Movement:
Static.

Camera Stability:
Locked.

Focus Intent:
Sharp focus on the hand and door handle. Background remains soft.

Subject Relationship:
The camera observes hesitation without entering the character's full face.

Viewer Position:
Close witness.

Camera Motivation:
The close static camera forces attention onto the smallest physical sign of fear.

Emotional Relationship:
Suppressed anxiety should be visible through stillness rather than performance.

Composition Relationship:
The hand stays low in frame while the old door surface dominates the image.
```

This example must not be treated as required data format.

---

## 42. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This specification defines the conceptual Camera model only.

Implementation cannot begin until the following exist:

- Camera data model specification
- Scene data model specification
- Shot data model specification
- Emotion model implementation-related specifications
- Composition model specification
- Motion model specification
- Prompt Export Intent specification
- Camera public API specification
- Camera event specification
- Camera test specification
- AI implementation tasks
- Review approval

---

## 43. Acceptance Criteria

This specification is acceptable when:

1. Camera purpose is defined.
2. Camera non-scope is explicit.
3. Camera responsibility is defined.
4. Camera is separated from vague style words.
5. Camera levels are defined.
6. Film-level camera language is introduced.
7. Scene-level camera strategy is introduced.
8. Shot-level camera intent is introduced.
9. Camera Angle Intent is defined.
10. Camera Distance Intent is defined.
11. Camera Perspective Intent is defined.
12. Camera Movement Intent is defined.
13. Camera Stability Intent is defined.
14. Focus Intent is defined.
15. Subject Relationship is defined.
16. Viewer Position is defined.
17. Camera Motivation is defined.
18. Camera Inheritance is defined.
19. Camera Override is defined.
20. Relationships to Scene and Shot are defined.
21. Relationship to Emotion is defined.
22. Relationship to Composition is defined.
23. Relationship to Motion is defined.
24. Relationship to Transition is defined.
25. Relationship to Prompt Export Intent is defined.
26. Provider plugin boundaries are defined.
27. Validation expectations are defined.
28. Error handling expectations are defined.
29. Security expectations are defined.
30. Offline-first expectations are defined.
31. Testing expectations are defined.
32. Implementation readiness is explicitly marked Not Ready.

---

## 44. Change Control

Changes to this specification must update:

- Version
- Change history
- Affected AFL documents
- Affected module specifications
- Affected interface specifications
- Affected data specifications
- Affected test specifications
- Affected implementation tasks

Breaking changes to Camera levels, Camera inheritance, provider independence or prompt separation may require an ADR.

Major changes to Camera concept scope may require an RFC.

---

## 45. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

---

## 46. Summary

The AFL Camera Model defines camera as structured cinematic intent.

Camera is not a generic style word.

Camera is not provider-specific syntax.

Camera may define angle, distance, perspective, movement, stability, focus, subject relationship and motivation.

Future implementation must build from approved data, API and test specifications, not from this conceptual document alone.

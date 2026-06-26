# AFL Scene Model Specification

Document ID: AFL-000002  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 06-AI/AFL-000002_SCENE_MODEL_SPEC.md  
Document Type: Aurora Film Language Specification  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, 01-Product/GLOSSARY.md, 01-Product/ROADMAP.md, 02-Architecture/ARCHITECTURE.md, 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md, 12-Templates/SPEC_TEMPLATE.md  

---

## 1. Purpose

This document defines the Aurora Film Language Scene Model.

A Scene is a structured cinematic unit inside Aurora Film Language.

A Scene represents meaningful dramatic, visual, emotional, symbolic and narrative intent before that intent is divided into shots, exported as prompts, sent to provider plugins or used in timeline workflows.

A Scene is not a prompt.

A Scene is not a provider-specific request.

A Scene is not a GUI object.

A Scene is a structured unit of cinematic meaning.

---

## 2. Authority

This specification is subordinate to:

- 00-Governance/AURORA_CONSTITUTION.md
- 00-Governance/AURORA_ENGINEERING_STANDARD.md
- 00-Governance/REVIEW_STANDARD.md
- 02-Architecture/ARCHITECTURE.md
- 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md

If this specification conflicts with the Aurora Constitution, the Constitution takes precedence.

If this specification conflicts with the AFL Overview, the conflict must be reviewed before implementation begins.

This document defines the conceptual Scene model only.

Implementation requires later data, API, event and test specifications.

---

## 3. Scope

This specification defines:

- What an AFL Scene is
- What an AFL Scene is not
- Scene responsibility
- Scene identity requirements
- Scene structural sections
- Scene relationships with shots, characters, emotions, symbols, camera, composition, motion, transition and prompt export
- Scene lifecycle states
- Scene validation expectations
- Scene error handling expectations
- Scene offline-first expectations
- Scene security expectations
- Scene implementation readiness

This specification applies to:

- Aurora Film Language
- Future Scene Manager module
- Future Shot Manager module
- Future AFL Engine module
- Future Prompt Export Manager module
- Future data specifications
- Future interface specifications
- Future implementation tasks

---

## 4. Non-Scope

This specification does not define:

- Python classes
- JSON schema
- Database schema
- GUI layout
- Timeline UI behavior
- Full Shot model
- Full Character model
- Full Emotion model
- Full Camera model
- Full Composition model
- Full Symbol model
- Full Motion model
- Full Transition model
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
| Scene | A meaningful dramatic, visual, emotional or narrative unit inside an Aurora project. |
| AFL Scene | The Aurora Film Language representation of a Scene. |
| Scene Intent | The reason the Scene exists and what it must communicate. |
| Scene Role | The function of the Scene inside the film, sequence or workflow. |
| Scene State | The lifecycle status of the Scene inside the project. |
| Scene Continuity | Requirements that preserve consistency before, during and after the Scene. |
| Shot List | The ordered or unordered collection of shots belonging to a Scene. |
| Character Presence | The scene-specific participation of a character. |
| Emotional Arc | The emotional movement or transformation represented by the Scene. |
| Symbolic Layer | The symbolic elements and meanings carried by the Scene. |
| Visual Strategy | The intended visual language of the Scene. |
| Export Intent | Structured guidance for converting the Scene into external outputs. |

---

## 6. Scene Responsibility

A Scene is responsible for representing the meaning of one cinematic unit.

A Scene may coordinate references to:

- Characters
- Location
- Time context
- Emotional arc
- Symbols
- Camera intent
- Composition intent
- Motion intent
- Sound intent
- Transition intent
- Shot structure
- Prompt export intent

A Scene must not own provider-specific prompt syntax.

A Scene must not directly know how a video model works.

A Scene must not contain plugin implementation details.

A Scene must not contain GUI state.

A Scene must preserve cinematic meaning independently of output format.

---

## 7. Scene Identity

Every Scene must have stable identity.

A future data specification must define exact field names and ID format.

At the conceptual level, a Scene requires:

- Scene ID
- Human-readable title
- Project relationship
- Optional sequence relationship
- Version or revision information
- Creation metadata
- Modification metadata

Scene identity must remain stable across editing, saving, loading and export.

Scene identity must not depend on provider output.

Scene identity must not be generated from prompt text.

---

## 8. Scene Required Conceptual Sections

An AFL Scene should contain the following conceptual sections:

1. Identity
2. Purpose
3. Narrative Context
4. Time and Location Context
5. Character Presence
6. Emotional Arc
7. Visual Strategy
8. Symbolic Layer
9. Sound Intent
10. Motion Intent
11. Transition Intent
12. Shot Structure
13. Continuity Requirements
14. Export Intent
15. Review and Validation State

These sections are conceptual requirements.

Exact fields must be defined in a later data specification.

---

## 9. Scene Purpose

Scene Purpose defines why the Scene exists.

Scene Purpose may describe:

- Narrative function
- Emotional function
- Visual function
- Symbolic function
- Character function
- Transition function
- Setup or payoff function

A Scene without purpose is incomplete.

Purpose must be understandable by a human reviewer.

Purpose must be structured enough to guide later shot creation and prompt export.

Bad Scene Purpose:

```text
Beautiful scene.
```

Better Scene Purpose:

```text
Show the protagonist realizing that the city no longer feels like home.
```

---

## 10. Scene Role

Scene Role defines how the Scene functions inside the larger film or sequence.

Possible role categories may include:

- Opening
- Setup
- Development
- Revelation
- Conflict
- Turning point
- Memory
- Transition
- Climax
- Resolution
- Epilogue
- Montage segment
- Atmospheric bridge
- Symbolic insert

This list is not final.

A later product or AFL specification may define controlled values.

Scene Role must not be guessed by provider plugins.

---

## 11. Narrative Context

Narrative Context describes what is happening at story level.

It may include:

- Situation
- Conflict
- Relationship state
- Character objective
- Obstacle
- New information
- Consequence
- Story dependency
- Prior scene reference
- Next scene expectation

Narrative Context should be separated from visual instructions.

This allows the same narrative meaning to be exported into multiple visual or prompt styles.

---

## 12. Time and Location Context

A Scene may define time and location context.

Time context may include:

- Story time
- Time of day
- Season
- Historical period
- Relative time
- Memory or dream state
- Temporal ambiguity

Location context may include:

- Physical location
- Fictional location
- Interior or exterior state
- Environmental condition
- Spatial relationship
- Symbolic meaning of location

Location must not be reduced only to a prompt phrase.

Location is part of cinematic meaning.

---

## 13. Character Presence

A Scene may contain one or more Character Presence entries.

Character Presence defines how each character participates in the Scene.

A Character Presence entry may include:

- Character identity reference
- Role in the Scene
- Emotional state
- Goal or intention
- Action
- Relationship to other characters
- Visibility level
- Position or spatial role
- Continuity requirements
- Reference asset requirements
- Dialogue or silence indicator

Character Presence is scene-specific.

Character identity itself should be defined in a future Character model or module.

A Scene must not duplicate full character database data unless explicitly required by a later specification.

---

## 14. Emotional Arc

A Scene may define an Emotional Arc.

The Emotional Arc describes emotional state and movement across the Scene.

It may include:

- Starting emotional state
- Ending emotional state
- Emotional shift
- Emotional intensity
- Dominant emotion
- Hidden emotion
- Character-specific emotion
- Audience-facing emotion
- Emotional contradiction
- Emotional pacing

Emotion must be defined as structured intent.

Emotion must not rely only on vague adjectives.

Bad emotional description:

```text
Sad.
```

Better emotional description:

```text
The Scene begins with controlled silence and ends with visible resignation.
```

The full Emotion model must be defined in a later AFL specification.

---

## 15. Visual Strategy

Visual Strategy defines how the Scene should communicate visually.

It may include:

- Overall visual tone
- Lighting direction
- Color intent
- Camera distance strategy
- Composition strategy
- Movement strategy
- Visual contrast
- Texture
- Environmental emphasis
- Subject emphasis
- Visual restraint or intensity

Visual Strategy is not provider syntax.

Visual Strategy guides future Shot, Camera, Composition and Prompt Export specifications.

---

## 16. Symbolic Layer

A Scene may contain symbolic elements.

A symbolic element may include:

- Symbol identity
- Literal object or visual element
- Intended meaning
- Recurrence rule
- Relationship to character or emotion
- Relationship to previous scenes
- Relationship to future scenes
- Visibility level
- Export importance

Symbols must be traceable when continuity matters.

A Symbol must not become accidental decoration if it has defined meaning.

The full Symbol model must be defined in a later AFL specification.

---

## 17. Sound Intent

Sound Intent defines expected sound meaning for the Scene.

It may include:

- Silence
- Ambient sound
- Music direction
- Rhythm
- Voice or dialogue intention
- Sound motif
- Emotional sound direction
- Transition sound
- Diegetic or non-diegetic sound role

This specification does not define audio implementation.

Sound Intent is part of cinematic meaning and may later affect export, editing or generation tasks.

---

## 18. Motion Intent

Motion Intent defines movement at Scene level.

It may include:

- Character movement
- Camera movement strategy
- Environmental movement
- Object movement
- Emotional movement
- Rhythm of movement
- Stillness or restraint
- Escalation or reduction of movement

Scene-level Motion Intent guides shot-level motion.

It must not replace the future Shot Motion model.

---

## 19. Transition Intent

Transition Intent defines how this Scene relates to adjacent scenes.

It may include:

- Incoming transition
- Outgoing transition
- Emotional bridge
- Visual bridge
- Symbolic bridge
- Sound bridge
- Time jump
- Location shift
- Contrast relationship
- Continuity relationship

Transition Intent must support review and future export.

The full Transition model must be defined in a later AFL specification.

---

## 20. Shot Structure

A Scene may contain or reference a Shot List.

At conceptual level, Scene Shot Structure may include:

- Shot count intent
- Ordered shots
- Optional unordered shot ideas
- Required shots
- Optional shots
- Shot purpose
- Shot continuity relationship
- Shot export priority

This specification does not define the full Shot model.

The full Shot model must be defined in:

```text
06-AI/AFL-000003_SHOT_MODEL_SPEC.md
```

A Scene may be valid before final shots are defined, but it is not ready for detailed video export until shot structure is sufficient.

---

## 21. Continuity Requirements

A Scene may define continuity requirements.

Continuity may apply to:

- Character appearance
- Character emotional state
- Location
- Props
- Symbols
- Lighting
- Time
- Weather
- Camera language
- Sound motifs
- Narrative facts
- Prior and next scenes

Continuity requirements must be explicit when they affect output.

Provider plugins must not invent continuity.

---

## 22. Export Intent

A Scene may include Prompt Export Intent or reference it.

Export Intent defines how Scene meaning may be converted into external outputs.

It may include:

- Target export type
- Target provider
- Detail level
- Style constraints
- Negative constraints
- Safety constraints
- Continuity emphasis
- Shot breakdown preference
- Prompt length preference
- Reference asset use
- Provider-specific limitations

Export Intent must not replace Scene meaning.

Export Intent is a bridge from Scene to output.

Provider-specific content belongs outside Scene core unless explicitly approved.

---

## 23. Scene State

A Scene may have lifecycle state.

Possible conceptual states:

- Draft
- Structured
- Ready for Review
- Approved
- Needs Revision
- Ready for Shot Breakdown
- Ready for Export
- Exported
- Deprecated
- Archived

This list is not final.

A later data specification must define exact allowed values.

Scene State must not be confused with document status.

Scene State describes the creative unit.

Document status describes specification lifecycle.

---

## 24. Scene Validation Expectations

A Scene should be validated before export.

Possible validation checks:

1. Scene has stable identity.
2. Scene has purpose.
3. Scene has narrative context or explicit atmospheric purpose.
4. Required characters are defined.
5. Emotional arc is defined or explicitly not applicable.
6. Visual strategy is defined.
7. Continuity requirements are not contradictory.
8. Shot structure is sufficient for the selected export mode.
9. Export Intent is compatible with the target provider.
10. Scene does not contain provider-specific syntax in core fields.
11. Required references are available.
12. Scene can be saved offline.

This specification does not define validation code.

---

## 25. Scene Error Handling Expectations

Future implementation must handle Scene-related errors.

Potential errors:

| Error Condition | Required Behavior |
|---|---|
| Missing Scene ID | Report validation failure and prevent export. |
| Missing Scene Purpose | Report incomplete Scene. |
| Missing required Character reference | Report unresolved reference. |
| Contradictory continuity requirement | Report conflict and require review. |
| Provider-specific syntax found in core fields | Report specification violation. |
| Export Intent incompatible with target provider | Report export preparation failure. |
| Missing required reference asset | Report missing dependency. |
| Scene data version unsupported | Require migration or compatibility handling. |

Errors must be meaningful.

Errors must not silently rewrite Scene meaning.

---

## 26. Scene Security Requirements

A Scene may contain private creative information.

Scene data may include:

- Story details
- Character details
- Prompt intent
- Private references
- Generated media relationships
- User creative decisions

Provider plugins must receive only the Scene data required for export or generation.

Scene data must not be sent to online providers unless the user initiates or approves an operation requiring it.

Future security specifications must define plugin permissions.

---

## 27. Scene Offline-First Requirements

Scene creation, editing, saving, loading, validation and review must work offline whenever technically possible.

A Scene must not require Internet access.

A Scene must not require an online provider.

Online generation may require an online provider, but Scene structure itself must remain local and usable.

---

## 28. Scene Performance Expectations

Scene operations should be lightweight.

Future implementation should avoid making basic Scene editing depend on heavy generation processes.

Expected lightweight operations:

- Create Scene
- Rename Scene
- Edit purpose
- Edit narrative context
- Edit emotional arc
- Edit visual strategy
- Validate required fields
- Save Scene
- Load Scene

Heavy operations, such as video generation or large asset analysis, must not block basic Scene editing.

---

## 29. Scene Compatibility Expectations

Scene data must be versioned in future data specifications.

Compatibility expectations:

- Older Scene data should be migratable where technically possible.
- Unknown future fields should not corrupt current project data.
- Provider export artifacts must not become required to open a Scene.
- Scene meaning must remain separate from generated media output.

Breaking Scene data changes require an ADR.

---

## 30. Scene Relationships

A Scene may relate to:

- Project
- Sequence
- Timeline
- Shot
- Character
- Asset
- Symbol
- Emotion
- Camera
- Composition
- Motion
- Transition
- Prompt Export Intent
- Provider Export Result

Relationship rules must be defined in later data and interface specifications.

A Scene must not directly mutate unrelated module data.

Cross-module changes must occur through approved interfaces.

---

## 31. Events

Future Scene operations may emit events.

Possible future events:

- SceneCreated
- SceneUpdated
- SceneRenamed
- SceneDeleted
- SceneArchived
- SceneValidated
- SceneValidationFailed
- SceneApproved
- SceneMarkedForRevision
- SceneReadyForShotBreakdown
- SceneReadyForExport
- SceneExportIntentChanged

This specification does not define final event schemas.

Event schemas must be defined in later interface specifications.

---

## 32. Testing Requirements

Future Scene implementation must include tests.

Required future test areas:

- Scene creation
- Scene identity stability
- Scene purpose validation
- Character Presence reference validation
- Emotional Arc presence or explicit exclusion
- Continuity conflict detection
- Provider-specific syntax isolation
- Offline save/load behavior
- Scene state transitions
- Export Intent compatibility checks
- Backward compatibility for versioned Scene data

This specification does not create test files.

Test specifications must be created before implementation.

---

## 33. AI Implementation Rules For Future Scene Tasks

Future AI implementation tasks for Scene must:

1. Reference this specification.
2. Reference the future Scene data model.
3. Reference the future Scene API specification.
4. Reference applicable test specifications.
5. Define exact target files.
6. Define exact allowed files.
7. Forbid provider-specific logic unless explicitly required.
8. Forbid GUI behavior unless the task is a UI task.
9. Forbid database schema changes unless the task is a data task.
10. Require validation commands where applicable.

AI agents must not implement the Scene model directly from this conceptual specification alone.

---

## 34. Example Conceptual Scene

The following is a conceptual example, not a schema.

```text
Scene Title:
The Bridge at Dawn

Scene Purpose:
Show the protagonist crossing from denial into acceptance.

Narrative Context:
The protagonist returns to the city after years away and realizes that the past cannot be recovered.

Emotional Arc:
Starts with guarded nostalgia and ends with quiet resignation.

Visual Strategy:
Cold dawn light, wide empty space, restrained camera, slow movement.

Symbolic Layer:
The bridge represents transition, distance and irreversible time.

Character Presence:
One protagonist, visible but isolated inside the frame.

Transition Intent:
The Scene should enter from darkness and leave into pale morning light.

Export Intent:
May later be broken into three slow video-generation shots.
```

This example must not be treated as required data format.

---

## 35. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This specification defines the conceptual Scene model only.

Implementation cannot begin until the following exist:

- Scene data model specification
- Shot model specification
- Character Presence specification or related model
- Emotion model specification
- Prompt Export Intent specification
- Scene public API specification
- Scene event specification
- Scene test specification
- AI implementation tasks
- Review approval

---

## 36. Acceptance Criteria

This specification is acceptable when:

1. Scene purpose is defined.
2. Scene non-scope is explicit.
3. Scene responsibility is defined.
4. Scene identity expectations are defined.
5. Required conceptual sections are listed.
6. Scene Purpose is defined.
7. Scene Role is defined.
8. Narrative Context is defined.
9. Time and Location Context are defined.
10. Character Presence is defined.
11. Emotional Arc is defined.
12. Visual Strategy is defined.
13. Symbolic Layer is defined.
14. Sound Intent is defined.
15. Motion Intent is defined.
16. Transition Intent is defined.
17. Shot Structure is defined.
18. Continuity Requirements are defined.
19. Export Intent is defined.
20. Scene State is defined conceptually.
21. Validation expectations are defined.
22. Error handling expectations are defined.
23. Security expectations are defined.
24. Offline-first expectations are defined.
25. Testing expectations are defined.
26. Implementation readiness is explicitly marked Not Ready.

---

## 37. Change Control

Changes to this specification must update:

- Version
- Change history
- Affected AFL documents
- Affected module specifications
- Affected interface specifications
- Affected data specifications
- Affected test specifications
- Affected implementation tasks

Breaking changes to Scene identity, Scene responsibility, provider independence or prompt separation may require an ADR.

Major changes to Scene concept scope may require an RFC.

---

## 38. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

---

## 39. Summary

The AFL Scene Model defines Scene as a structured unit of cinematic meaning.

A Scene is not a prompt.

A Scene is not provider syntax.

A Scene preserves creative intent before shot breakdown, prompt export or AI generation.

Future implementation must build from approved data, API and test specifications, not from this conceptual document alone.

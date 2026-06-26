# AFL Shot Model Specification

Document ID: AFL-000003  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 06-AI/AFL-000003_SHOT_MODEL_SPEC.md  
Document Type: Aurora Film Language Specification  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, 01-Product/GLOSSARY.md, 01-Product/ROADMAP.md, 02-Architecture/ARCHITECTURE.md, 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md, 06-AI/AFL-000002_SCENE_MODEL_SPEC.md, 12-Templates/SPEC_TEMPLATE.md  

---

## 1. Purpose

This document defines the Aurora Film Language Shot Model.

A Shot is a structured cinematic unit inside a Scene.

A Shot represents a focused unit of visual, emotional, camera, composition, motion, continuity and export intent.

A Shot is not a prompt.

A Shot is not provider-specific syntax.

A Shot is not a generated video file.

A Shot is not a GUI timeline clip.

A Shot is the structured intent for one cinematic unit that may later be exported, generated, reviewed, edited or placed on a timeline.

---

## 2. Authority

This specification is subordinate to:

- 00-Governance/AURORA_CONSTITUTION.md
- 00-Governance/AURORA_ENGINEERING_STANDARD.md
- 00-Governance/REVIEW_STANDARD.md
- 02-Architecture/ARCHITECTURE.md
- 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md
- 06-AI/AFL-000002_SCENE_MODEL_SPEC.md

If this specification conflicts with the Aurora Constitution, the Constitution takes precedence.

If this specification conflicts with the Scene Model, the conflict must be reviewed before implementation begins.

This document defines the conceptual Shot model only.

Implementation requires later data, API, event and test specifications.

---

## 3. Scope

This specification defines:

- What an AFL Shot is
- What an AFL Shot is not
- Shot responsibility
- Shot identity expectations
- Shot relationship to Scene
- Shot conceptual sections
- Shot purpose
- Subject focus
- Framing intent
- Camera intent
- Composition intent
- Motion intent
- Duration intent
- Visual detail intent
- Emotional intent
- Sound intent
- Continuity requirements
- Export intent
- Shot state
- Validation expectations
- Error handling expectations
- Offline-first expectations
- Security expectations
- Testing expectations
- Implementation readiness

This specification applies to:

- Aurora Film Language
- Future Shot Manager module
- Future Scene Manager module
- Future Timeline Manager module
- Future AFL Engine module
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
- GUI timeline clip behavior
- Video editing engine behavior
- Full Scene model
- Full Character model
- Full Emotion model
- Full Camera model
- Full Composition model
- Full Motion model
- Full Transition model
- Provider-specific prompt syntax
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
| Shot | A focused cinematic unit inside a Scene. |
| AFL Shot | The Aurora Film Language representation of a Shot. |
| Shot Intent | The reason the Shot exists and what it must communicate. |
| Subject Focus | The main visual or dramatic attention target of the Shot. |
| Framing Intent | The intended relationship between subject, frame, space and viewer attention. |
| Camera Intent | The intended camera angle, distance, behavior or perspective. |
| Composition Intent | The intended arrangement of visual elements inside the frame. |
| Motion Intent | The intended movement of camera, subject, object or environment inside the Shot. |
| Duration Intent | The intended temporal length or pacing meaning of the Shot. |
| Continuity Anchor | A detail that must remain consistent across shots or scenes. |
| Export Unit | A unit that may later be converted into provider-specific prompt or generation request. |

---

## 6. Shot Responsibility

A Shot is responsible for representing one focused cinematic unit within a Scene.

A Shot may coordinate references to:

- Parent Scene
- Character Presence
- Subject focus
- Camera intent
- Composition intent
- Motion intent
- Emotional intent
- Symbolic elements
- Sound intent
- Duration intent
- Continuity requirements
- Export intent
- Reference assets

A Shot must not own provider-specific prompt syntax.

A Shot must not know how a specific video model works.

A Shot must not contain plugin implementation details.

A Shot must not contain GUI state.

A Shot must preserve cinematic intent independently of output format.

---

## 7. Shot Identity

Every Shot must have stable identity.

A future data specification must define exact field names and ID format.

At conceptual level, a Shot requires:

- Shot ID
- Parent Scene relationship
- Human-readable title or label
- Optional shot number or ordering value
- Version or revision information
- Creation metadata
- Modification metadata

Shot identity must remain stable across editing, saving, loading and export.

Shot identity must not depend on generated video output.

Shot identity must not be generated from prompt text.

---

## 8. Parent Scene Relationship

A Shot belongs to a Scene.

A Shot must not exist as a fully independent film unit unless a later specification defines standalone shot libraries.

A Shot may inherit context from its parent Scene, including:

- Narrative context
- Location context
- Character context
- Emotional direction
- Visual strategy
- Symbolic layer
- Continuity requirements
- Export constraints

A Shot may override Scene-level intent only when explicitly allowed.

A Shot must not silently contradict its parent Scene.

Contradictions must be validated and reported.

---

## 9. Shot Required Conceptual Sections

An AFL Shot should contain the following conceptual sections:

1. Identity
2. Parent Scene Reference
3. Shot Purpose
4. Shot Role
5. Subject Focus
6. Character Presence Reference
7. Framing Intent
8. Camera Intent
9. Composition Intent
10. Motion Intent
11. Emotional Intent
12. Visual Detail Intent
13. Sound Intent
14. Duration Intent
15. Continuity Requirements
16. Reference Asset Requirements
17. Export Intent
18. Review and Validation State

These sections are conceptual requirements.

Exact fields must be defined in a later data specification.

---

## 10. Shot Purpose

Shot Purpose defines why the Shot exists.

Shot Purpose may describe:

- Narrative function
- Emotional function
- Visual function
- Symbolic function
- Character function
- Continuity function
- Transition function
- Detail emphasis
- Rhythm function

A Shot without purpose is incomplete unless it is explicitly marked as exploratory or optional.

Bad Shot Purpose:

```text
Cool shot.
```

Better Shot Purpose:

```text
Show the protagonist hesitating before entering the empty apartment.
```

---

## 11. Shot Role

Shot Role defines how the Shot functions inside its Scene.

Possible role categories may include:

- Establishing shot
- Wide shot
- Medium shot
- Close-up
- Insert
- Reaction shot
- Point-of-view shot
- Transition shot
- Detail shot
- Movement shot
- Symbolic shot
- Atmosphere shot
- Memory shot
- Dream shot
- Montage shot

This list is not final.

A later AFL or product specification may define controlled values.

Shot Role must not be guessed by provider plugins.

---

## 12. Subject Focus

Subject Focus defines the primary attention target of the Shot.

Subject Focus may be:

- Character
- Face
- Hands
- Object
- Location detail
- Symbol
- Movement
- Light
- Environmental change
- Empty space
- Camera relationship
- Emotional gesture

Subject Focus must be explicit when it affects generation or review.

A Shot may have primary and secondary focus.

A Shot with too many focus targets may be difficult to export and should be flagged by validation if future rules define limits.

---

## 13. Character Presence Reference

A Shot may reference Character Presence entries from the parent Scene.

Shot-level character information may include:

- Which Scene characters are visible
- Which character is primary
- Which character is secondary
- Character action in this Shot
- Character emotional state in this Shot
- Character gaze or attention
- Character frame position
- Character continuity requirements
- Character reference asset requirements

A Shot must not duplicate full character database data unless explicitly required by a later specification.

Shot-level Character Presence must remain consistent with Scene-level Character Presence unless an intentional change is documented.

---

## 14. Framing Intent

Framing Intent defines the intended relationship between the subject and the frame.

It may include:

- Shot size
- Subject placement
- Headroom
- Lead room
- Negative space
- Foreground use
- Background use
- Depth relationship
- Viewer attention
- Isolation or crowding
- Symmetry or imbalance

Framing Intent is cinematic meaning.

It must not be reduced only to provider prompt syntax.

---

## 15. Camera Intent

Camera Intent defines the intended camera behavior for the Shot.

It may include:

- Camera angle
- Camera distance
- Lens feel
- Perspective
- Camera height
- Camera stability
- Camera movement
- Focus behavior
- Subject relationship
- Motivation for camera choice

Camera Intent must express why the camera behaves in a certain way when relevant.

Bad Camera Intent:

```text
Cinematic camera.
```

Better Camera Intent:

```text
Low static camera makes the empty hallway feel heavier than the character.
```

The full Camera model must be defined in a later AFL specification.

---

## 16. Composition Intent

Composition Intent defines how visual elements are arranged inside the Shot.

It may include:

- Visual hierarchy
- Foreground elements
- Midground elements
- Background elements
- Depth
- Balance
- Contrast
- Subject isolation
- Symbol placement
- Attention path
- Spatial tension
- Visual emptiness or density

Composition Intent must be compatible with Scene-level Visual Strategy unless explicitly overridden.

The full Composition model must be defined in a later AFL specification.

---

## 17. Motion Intent

Motion Intent defines movement inside the Shot.

Motion may include:

- Character movement
- Camera movement
- Object movement
- Environmental movement
- Light movement
- Crowd movement
- Gesture movement
- Emotional movement
- Rhythm movement

Motion Intent should include cinematic motivation when needed.

Bad Motion Intent:

```text
Camera moves.
```

Better Motion Intent:

```text
Camera slowly pushes in as the character realizes the room is unchanged.
```

The full Motion model must be defined in a later AFL specification.

---

## 18. Emotional Intent

Emotional Intent defines what the Shot must communicate emotionally.

It may include:

- Dominant emotion
- Hidden emotion
- Emotional shift
- Emotional intensity
- Character-facing emotion
- Audience-facing emotion
- Emotional contradiction
- Emotional restraint
- Emotional release

Shot-level Emotional Intent may refine Scene-level Emotional Arc.

It must not silently contradict the Scene-level Emotional Arc.

The full Emotion model must be defined in a later AFL specification.

---

## 19. Visual Detail Intent

Visual Detail Intent defines important visual details that must be present, emphasized or avoided.

It may include:

- Prop details
- Costume details
- Weather details
- Texture details
- Light details
- Symbol details
- Environmental marks
- Time indicators
- Story clues
- Continuity anchors

Visual Detail Intent must distinguish between required and optional details in later data specifications.

Provider plugins must not treat all details as equally important unless export rules define that behavior.

---

## 20. Sound Intent

Sound Intent defines sound meaning at Shot level.

It may include:

- Silence
- Ambient sound
- Character sound
- Object sound
- Music cue
- Rhythm cue
- Sound bridge
- Emotional sound emphasis
- Diegetic or non-diegetic sound role

This specification does not define audio implementation.

Sound Intent may later guide editing, generation, export or review.

---

## 21. Duration Intent

Duration Intent defines the intended temporal meaning of the Shot.

It may include:

- Approximate duration
- Pacing category
- Hold duration
- Slow reveal
- Quick insert
- Long take intent
- Rhythm relationship to adjacent shots
- Export duration target

Duration Intent is not necessarily exact runtime.

A future data specification must define whether duration is approximate, fixed or provider-dependent.

Duration Intent must not be treated as a guaranteed provider output duration unless export specification defines that behavior.

---

## 22. Continuity Requirements

A Shot may define continuity requirements.

Continuity may apply to:

- Character appearance
- Character position
- Character emotion
- Props
- Symbols
- Location details
- Lighting
- Weather
- Camera direction
- Screen direction
- Time
- Sound
- Previous shot relationship
- Next shot relationship

Continuity requirements must be explicit when they affect output.

Provider plugins must not invent continuity.

---

## 23. Reference Asset Requirements

A Shot may require reference assets.

Reference assets may include:

- Character image reference
- Location reference
- Object reference
- Style reference
- Composition reference
- Motion reference
- Sound reference
- Color reference

A Shot must distinguish required references from optional references in later data specifications.

Missing required references must be reported before export.

---

## 24. Export Intent

A Shot may include or reference Prompt Export Intent.

Export Intent may include:

- Target export type
- Target provider
- Target model family
- Prompt detail level
- Negative constraints
- Safety constraints
- Duration target
- Aspect ratio target
- Motion emphasis
- Camera emphasis
- Character reference usage
- Continuity emphasis
- Output format expectations

Export Intent must not replace Shot meaning.

Export Intent is a bridge from Shot to output.

Provider-specific fields must remain outside Shot core unless explicitly approved.

---

## 25. Shot State

A Shot may have lifecycle state.

Possible conceptual states:

- Draft
- Structured
- Ready for Review
- Approved
- Needs Revision
- Ready for Export
- Exported
- Regeneration Needed
- Deprecated
- Archived

This list is not final.

A later data specification must define exact allowed values.

Shot State must not be confused with document status.

Shot State describes the creative unit.

Document status describes specification lifecycle.

---

## 26. Shot Ordering

A Shot may have ordering inside a Scene.

Ordering may be:

- Fixed
- Suggested
- Optional
- Alternative
- Parallel
- Montage-based
- Unordered idea

A future data specification must define exact ordering behavior.

Shot ordering must support review and future timeline integration.

Provider plugins must not reorder shots unless export rules explicitly allow it.

---

## 27. Shot Variants

A future Aurora workflow may allow Shot variants.

Possible variant use cases:

- Alternative camera angle
- Alternative emotional intensity
- Alternative duration
- Alternative composition
- Alternative provider export
- Regeneration candidate
- Director's choice comparison

This specification does not define final Shot variant behavior.

Variants must not corrupt the identity of the main Shot.

---

## 28. Shot Validation Expectations

A Shot should be validated before export.

Possible validation checks:

1. Shot has stable identity.
2. Shot has parent Scene reference.
3. Shot has purpose.
4. Subject Focus is defined or explicitly not applicable.
5. Camera Intent is defined or inherited.
6. Composition Intent is defined or inherited.
7. Motion Intent is defined or explicitly not applicable.
8. Emotional Intent is compatible with parent Scene.
9. Continuity requirements do not contradict parent Scene or adjacent shots.
10. Required reference assets are available.
11. Export Intent is compatible with target provider.
12. Provider-specific syntax is not stored in core fields.
13. Shot can be saved offline.

This specification does not define validation code.

---

## 29. Shot Error Handling Expectations

Future implementation must handle Shot-related errors.

Potential errors:

| Error Condition | Required Behavior |
|---|---|
| Missing Shot ID | Report validation failure and prevent export. |
| Missing parent Scene reference | Report unresolved relationship. |
| Missing Shot Purpose | Report incomplete Shot. |
| Missing Subject Focus | Report incomplete Shot unless explicitly not applicable. |
| Contradiction with Scene Emotional Arc | Report conflict and require review. |
| Contradictory continuity requirement | Report conflict and require review. |
| Provider-specific syntax found in core fields | Report specification violation. |
| Missing required reference asset | Report missing dependency. |
| Export Intent incompatible with target provider | Report export preparation failure. |
| Unsupported Shot data version | Require migration or compatibility handling. |

Errors must not silently rewrite Shot meaning.

---

## 30. Shot Security Requirements

A Shot may contain private creative information.

Shot data may include:

- Character actions
- Story details
- Visual details
- Emotional intent
- Prompt export intent
- Private references
- Generated media relationships
- User creative decisions

Provider plugins must receive only the Shot data required for export or generation.

Shot data must not be sent to online providers unless the user initiates or approves an operation requiring it.

Future security specifications must define plugin permissions.

---

## 31. Shot Offline-First Requirements

Shot creation, editing, saving, loading, validation and review must work offline whenever technically possible.

A Shot must not require Internet access.

A Shot must not require an online provider.

Online generation may require an online provider, but Shot structure itself must remain local and usable.

---

## 32. Shot Performance Expectations

Shot operations should be lightweight.

Expected lightweight operations:

- Create Shot
- Rename Shot
- Reorder Shot
- Edit purpose
- Edit Subject Focus
- Edit Camera Intent
- Edit Composition Intent
- Edit Motion Intent
- Edit Duration Intent
- Validate required fields
- Save Shot
- Load Shot

Heavy operations, such as video generation or large reference analysis, must not block basic Shot editing.

---

## 33. Shot Compatibility Expectations

Shot data must be versioned in future data specifications.

Compatibility expectations:

- Older Shot data should be migratable where technically possible.
- Unknown future fields should not corrupt current project data.
- Provider export artifacts must not become required to open a Shot.
- Shot meaning must remain separate from generated media output.

Breaking Shot data changes require an ADR.

---

## 34. Shot Relationships

A Shot may relate to:

- Scene
- Timeline
- Character Presence
- Asset
- Symbol
- Emotion
- Camera
- Composition
- Motion
- Transition
- Prompt Export Intent
- Provider Export Result
- Generated Media

Relationship rules must be defined in later data and interface specifications.

A Shot must not directly mutate unrelated module data.

Cross-module changes must occur through approved interfaces.

---

## 35. Events

Future Shot operations may emit events.

Possible future events:

- ShotCreated
- ShotUpdated
- ShotRenamed
- ShotDeleted
- ShotReordered
- ShotArchived
- ShotValidated
- ShotValidationFailed
- ShotApproved
- ShotMarkedForRevision
- ShotReadyForExport
- ShotExportIntentChanged
- ShotVariantCreated
- ShotVariantSelected

This specification does not define final event schemas.

Event schemas must be defined in later interface specifications.

---

## 36. Testing Requirements

Future Shot implementation must include tests.

Required future test areas:

- Shot creation
- Shot identity stability
- Parent Scene relationship validation
- Shot purpose validation
- Subject Focus validation
- Camera Intent inheritance or definition
- Composition Intent inheritance or definition
- Motion Intent validation
- Duration Intent validation
- Continuity conflict detection
- Reference asset requirement validation
- Provider-specific syntax isolation
- Offline save/load behavior
- Shot state transitions
- Shot ordering behavior
- Export Intent compatibility checks
- Backward compatibility for versioned Shot data

This specification does not create test files.

Test specifications must be created before implementation.

---

## 37. AI Implementation Rules For Future Shot Tasks

Future AI implementation tasks for Shot must:

1. Reference this specification.
2. Reference the Scene Model Specification.
3. Reference the future Shot data model.
4. Reference the future Shot API specification.
5. Reference applicable test specifications.
6. Define exact target files.
7. Define exact allowed files.
8. Forbid provider-specific logic unless explicitly required.
9. Forbid GUI behavior unless the task is a UI task.
10. Forbid database schema changes unless the task is a data task.
11. Require validation commands where applicable.

AI agents must not implement the Shot model directly from this conceptual specification alone.

---

## 38. Example Conceptual Shot

The following is a conceptual example, not a schema.

```text
Shot Title:
Hand on the Door Handle

Parent Scene:
The Bridge at Dawn

Shot Purpose:
Show the protagonist's hesitation before entering the old apartment.

Subject Focus:
The protagonist's hand resting on the door handle.

Camera Intent:
Static close-up, slightly low angle, restrained and intimate.

Composition Intent:
Hand in the lower third, old scratched door texture dominates the frame.

Motion Intent:
Almost no movement except a small tightening of the fingers.

Emotional Intent:
Controlled fear hidden behind stillness.

Duration Intent:
Hold longer than comfortable.

Continuity Requirements:
The same coat sleeve must match the previous shot.

Export Intent:
May become one slow video-generation shot.
```

This example must not be treated as required data format.

---

## 39. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This specification defines the conceptual Shot model only.

Implementation cannot begin until the following exist:

- Shot data model specification
- Scene data model specification
- Character Presence specification or related model
- Emotion model specification
- Camera model specification
- Composition model specification
- Motion model specification
- Prompt Export Intent specification
- Shot public API specification
- Shot event specification
- Shot test specification
- AI implementation tasks
- Review approval

---

## 40. Acceptance Criteria

This specification is acceptable when:

1. Shot purpose is defined.
2. Shot non-scope is explicit.
3. Shot responsibility is defined.
4. Shot identity expectations are defined.
5. Parent Scene relationship is defined.
6. Required conceptual sections are listed.
7. Shot Purpose is defined.
8. Shot Role is defined.
9. Subject Focus is defined.
10. Character Presence Reference is defined.
11. Framing Intent is defined.
12. Camera Intent is defined.
13. Composition Intent is defined.
14. Motion Intent is defined.
15. Emotional Intent is defined.
16. Visual Detail Intent is defined.
17. Sound Intent is defined.
18. Duration Intent is defined.
19. Continuity Requirements are defined.
20. Reference Asset Requirements are defined.
21. Export Intent is defined.
22. Shot State is defined conceptually.
23. Shot Ordering is defined conceptually.
24. Shot Variants are introduced.
25. Validation expectations are defined.
26. Error handling expectations are defined.
27. Security expectations are defined.
28. Offline-first expectations are defined.
29. Testing expectations are defined.
30. Implementation readiness is explicitly marked Not Ready.

---

## 41. Change Control

Changes to this specification must update:

- Version
- Change history
- Affected AFL documents
- Affected module specifications
- Affected interface specifications
- Affected data specifications
- Affected test specifications
- Affected implementation tasks

Breaking changes to Shot identity, parent Scene relationship, provider independence or prompt separation may require an ADR.

Major changes to Shot concept scope may require an RFC.

---

## 42. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

---

## 43. Summary

The AFL Shot Model defines Shot as a focused cinematic unit inside a Scene.

A Shot is not a prompt.

A Shot is not provider syntax.

A Shot preserves camera, composition, motion, emotion, continuity and export intent before AI generation or timeline placement.

Future implementation must build from approved data, API and test specifications, not from this conceptual document alone.

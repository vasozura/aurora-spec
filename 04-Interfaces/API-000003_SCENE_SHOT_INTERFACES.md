# Scene and Shot Interfaces

Document ID: API-000003  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 04-Interfaces/API-000003_SCENE_SHOT_INTERFACES.md  
Document Type: Interface Specification  
Depends On: API-000001_CORE_INTERFACE_PRINCIPLES.md, MOD-000003_SCENE_MANAGER_SPEC.md, MOD-000004_SHOT_MANAGER_SPEC.md, AFL-000002_SCENE_MODEL_SPEC.md, AFL-000003_SHOT_MODEL_SPEC.md  

---

## 1. Purpose

This document defines conceptual interfaces for Scene Manager and Shot Manager.

These interfaces preserve ownership boundaries between Scene and Shot while allowing coordinated workflows.

This document does not define code signatures.

---

## 2. Scope

This specification covers:

- Scene Manager commands, queries and events
- Shot Manager commands, queries and events
- Scene-Shot relationship rules
- Validation expectations
- Error expectations
- Offline-first expectations
- Security expectations

---

## 3. Scene Manager Commands

Conceptual commands:

| Command | Purpose |
|---|---|
| CreateScene | Create a new Scene in a project. |
| UpdateScene | Update Scene-owned conceptual data. |
| RenameScene | Rename a Scene. |
| ArchiveScene | Archive a Scene without destroying history where possible. |
| DeleteScene | Delete a Scene according to approved deletion rules. |
| ValidateScene | Validate Scene completeness and consistency. |
| MarkSceneReadyForShotBreakdown | Mark Scene ready for Shot work after validation. |
| MarkSceneReadyForExport | Mark Scene ready for export after validation. |

Scene commands must not directly create generated media.

Scene commands must not execute provider-specific export.

---

## 4. Scene Manager Queries

Conceptual queries:

| Query | Purpose |
|---|---|
| GetScene | Return a Scene by ID. |
| ListScenes | Return Scenes in a project. |
| GetSceneState | Return Scene lifecycle state. |
| GetSceneValidationReport | Return latest Scene validation report. |
| GetSceneShotReferences | Return Shot references belonging to Scene. |

Queries must be read-only.

---

## 5. Scene Manager Events

Conceptual events:

- SceneCreated
- SceneUpdated
- SceneRenamed
- SceneArchived
- SceneDeleted
- SceneValidated
- SceneValidationFailed
- SceneReadyForShotBreakdown
- SceneReadyForExport

---

## 6. Shot Manager Commands

Conceptual commands:

| Command | Purpose |
|---|---|
| CreateShot | Create a Shot inside a parent Scene. |
| UpdateShot | Update Shot-owned conceptual data. |
| RenameShot | Rename a Shot. |
| ReorderShot | Change Shot ordering inside Scene. |
| ArchiveShot | Archive a Shot. |
| DeleteShot | Delete a Shot according to approved deletion rules. |
| ValidateShot | Validate Shot completeness and consistency. |
| MarkShotReadyForExport | Mark Shot ready for export after validation. |
| CreateShotVariant | Create a Shot variant if supported by future data rules. |
| SelectShotVariant | Select a Shot variant if supported by future data rules. |

Shot commands must not modify parent Scene meaning directly.

---

## 7. Shot Manager Queries

Conceptual queries:

| Query | Purpose |
|---|---|
| GetShot | Return a Shot by ID. |
| ListShotsForScene | Return Shots for a parent Scene. |
| GetShotState | Return Shot lifecycle state. |
| GetShotValidationReport | Return latest Shot validation report. |
| GetShotVariants | Return variant references if supported. |

Queries must be read-only.

---

## 8. Shot Manager Events

Conceptual events:

- ShotCreated
- ShotUpdated
- ShotRenamed
- ShotReordered
- ShotArchived
- ShotDeleted
- ShotValidated
- ShotValidationFailed
- ShotReadyForExport
- ShotVariantCreated
- ShotVariantSelected

---

## 9. Scene-Shot Relationship Rules

A Shot must belong to a parent Scene unless a later specification allows standalone shot libraries.

A Shot may inherit context from Scene.

A Shot must not silently contradict parent Scene.

Scene deletion or archiving must define behavior for child Shots in later data specifications.

Shot ordering must be controlled by Shot Manager or approved timeline coordination.

---

## 10. Validation Expectations

Scene validation must check required Scene conceptual sections.

Shot validation must check required Shot conceptual sections.

AFL Engine may coordinate deeper consistency checks, but Scene Manager and Shot Manager must expose validation interfaces.

---

## 11. Error Expectations

Possible errors:

| Error | Meaning |
|---|---|
| SceneNotFound | Requested Scene does not exist. |
| ShotNotFound | Requested Shot does not exist. |
| InvalidParentScene | Shot references invalid parent Scene. |
| SceneValidationFailed | Scene incomplete or inconsistent. |
| ShotValidationFailed | Shot incomplete or inconsistent. |
| SceneShotConflict | Shot contradicts parent Scene without explicit override. |
| InvalidShotOrder | Requested Shot ordering is invalid. |

Errors must not silently rewrite creative meaning.

---

## 12. Offline-First Requirements

Scene and Shot creation, editing, validation and querying must work offline.

Provider export is outside this interface.

---

## 13. Security Requirements

Scene and Shot data may contain private creative material.

External provider access must be routed through Prompt Export Manager and Plugin Manager.

---

## 14. Testing Requirements

Future tests must verify:

- Scene command validation
- Scene query read-only behavior
- Scene event emission
- Shot command validation
- Shot query read-only behavior
- Shot event emission
- Parent Scene relationship enforcement
- Scene-Shot conflict handling
- Offline behavior

---

## 15. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This document defines conceptual interface contracts only.

Implementation requires concrete data contracts, function signatures, error types and test specifications.

---

## 16. Acceptance Criteria

This document is acceptable when:

1. Scene commands are listed.
2. Scene queries are listed.
3. Scene events are listed.
4. Shot commands are listed.
5. Shot queries are listed.
6. Shot events are listed.
7. Scene-Shot relationship rules are stated.
8. Error expectations are stated.
9. Offline-first requirements are stated.
10. Security requirements are stated.
11. Implementation readiness is explicitly marked Not Ready.

---

## 17. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

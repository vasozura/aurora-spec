# Project and Workspace Interfaces

Document ID: API-000002  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 04-Interfaces/API-000002_PROJECT_WORKSPACE_INTERFACES.md  
Document Type: Interface Specification  
Depends On: API-000001_CORE_INTERFACE_PRINCIPLES.md, MOD-000001_PROJECT_MANAGER_SPEC.md, MOD-000002_WORKSPACE_SPEC.md  

---

## 1. Purpose

This document defines conceptual interfaces for Project Manager and Workspace.

These interfaces describe commands, queries and events at a specification level.

This document does not define code signatures.

---

## 2. Scope

This specification covers:

- Project Manager commands
- Project Manager queries
- Project Manager events
- Workspace commands
- Workspace queries
- Workspace events
- Error expectations
- Security expectations
- Offline-first expectations

---

## 3. Project Manager Commands

Conceptual commands:

| Command | Purpose |
|---|---|
| CreateProject | Create a new Aurora project. |
| OpenProject | Open an existing Aurora project. |
| SaveProject | Save the active project. |
| CloseProject | Close the active project after validation. |
| ValidateProject | Validate project structure and compatibility. |
| RecoverProject | Attempt controlled project recovery when state is incomplete or damaged. |

Commands must not create Scenes, Shots, Assets or Plugins directly.

Project Manager coordinates project lifecycle only.

---

## 4. Project Manager Queries

Conceptual queries:

| Query | Purpose |
|---|---|
| GetProjectMetadata | Return project identity and metadata. |
| GetProjectState | Return current project lifecycle state. |
| GetProjectCompatibility | Return compatibility and version status. |
| GetProjectValidationReport | Return latest validation report. |

Queries must be read-only.

---

## 5. Project Manager Events

Conceptual events:

- ProjectCreated
- ProjectOpened
- ProjectSaved
- ProjectClosed
- ProjectValidationFailed
- ProjectRecoveryRequired
- ProjectRecovered

Events must not include full project data unless later specifications explicitly allow it.

---

## 6. Workspace Commands

Conceptual commands:

| Command | Purpose |
|---|---|
| ActivateWorkspace | Activate workspace for an opened project. |
| SetWorkspaceMode | Change active workspace mode. |
| SetActiveScene | Set active Scene reference. |
| SetActiveShot | Set active Shot reference. |
| SetActiveTimeline | Set active Timeline reference. |
| ClearWorkspaceSelection | Clear current selection context. |

Workspace commands must not modify Scene or Shot meaning directly.

---

## 7. Workspace Queries

Conceptual queries:

| Query | Purpose |
|---|---|
| GetActiveProject | Return active project reference. |
| GetWorkspaceState | Return workspace state. |
| GetActiveSelection | Return current selection context. |
| GetActiveScene | Return active Scene reference. |
| GetActiveShot | Return active Shot reference. |
| GetWorkspaceMode | Return current workspace mode. |

Queries must be read-only.

---

## 8. Workspace Events

Conceptual events:

- WorkspaceActivated
- WorkspaceModeChanged
- WorkspaceSelectionChanged
- ActiveSceneChanged
- ActiveShotChanged
- ActiveTimelineChanged

Events must contain references, not full owned data from other modules.

---

## 9. Error Expectations

Errors must be explicit.

Possible errors:

| Error | Meaning |
|---|---|
| ProjectNotFound | Requested project does not exist or cannot be opened. |
| ProjectAlreadyOpen | Operation conflicts with already opened project. |
| ProjectValidationFailed | Project structure or compatibility check failed. |
| WorkspaceUnavailable | Workspace cannot activate without valid project. |
| InvalidSelectionReference | Workspace selection references missing or invalid item. |

---

## 10. Offline-First Requirements

Project and Workspace operations must work offline for local projects.

Opening, saving, validating and workspace selection must not require online services.

---

## 11. Security Requirements

Project metadata and workspace state must not be sent to external providers.

External provider workflows must be routed through export or plugin boundaries.

---

## 12. Testing Requirements

Future tests must verify:

- Project command validation
- Project query read-only behavior
- Workspace command validation
- Workspace query read-only behavior
- Event emission
- Invalid reference handling
- Offline behavior

---

## 13. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This document defines conceptual interface contracts only.

Implementation requires concrete data contracts, function signatures, error types and test specifications.

---

## 14. Acceptance Criteria

This document is acceptable when:

1. Project commands are listed.
2. Project queries are listed.
3. Project events are listed.
4. Workspace commands are listed.
5. Workspace queries are listed.
6. Workspace events are listed.
7. Error expectations are stated.
8. Offline-first requirements are stated.
9. Security requirements are stated.
10. Implementation readiness is explicitly marked Not Ready.

---

## 15. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

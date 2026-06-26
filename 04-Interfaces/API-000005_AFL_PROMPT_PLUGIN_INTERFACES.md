# AFL, Prompt Export and Plugin Interfaces

Document ID: API-000005  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 04-Interfaces/API-000005_AFL_PROMPT_PLUGIN_INTERFACES.md  
Document Type: Interface Specification  
Depends On: API-000001_CORE_INTERFACE_PRINCIPLES.md, MOD-000008_AFL_ENGINE_SPEC.md, MOD-000009_PROMPT_EXPORT_MANAGER_SPEC.md, MOD-000010_PLUGIN_MANAGER_SPEC.md, AFL-000001 through AFL-000010  

---

## 1. Purpose

This document defines conceptual interfaces for AFL Engine, Prompt Export Manager and Plugin Manager.

These interfaces preserve the separation between AFL source meaning, export artifacts and provider-specific plugin behavior.

This document does not define code signatures.

---

## 2. Scope

This specification covers:

- AFL Engine commands, queries and events
- Prompt Export Manager commands, queries and events
- Plugin Manager commands, queries and events
- AFL-to-export boundary rules
- Plugin boundary rules
- Error expectations
- Offline-first expectations
- Security expectations

---

## 3. AFL Engine Commands

Conceptual commands:

| Command | Purpose |
|---|---|
| ValidateAFLStructure | Validate one AFL structure. |
| ValidateAFLProject | Validate AFL consistency across a project. |
| AnalyzeAFLConflicts | Identify contradictions between AFL structures. |
| MarkAFLReadyForExport | Mark validated AFL structure ready for export. |

AFL Engine commands must not execute provider generation.

AFL Engine must not rewrite creative meaning silently.

---

## 4. AFL Engine Queries

Conceptual queries:

| Query | Purpose |
|---|---|
| GetAFLValidationReport | Return validation results. |
| GetAFLConflictReport | Return consistency conflicts. |
| GetAFLReadinessState | Return export readiness state. |
| GetAFLStructureSummary | Return human-readable AFL structure summary. |

Queries must be read-only.

---

## 5. AFL Engine Events

Conceptual events:

- AFLValidationStarted
- AFLValidationFinished
- AFLValidationFailed
- AFLConflictDetected
- AFLStructureReadyForExport

---

## 6. Prompt Export Manager Commands

Conceptual commands:

| Command | Purpose |
|---|---|
| PreparePromptExport | Prepare an export job from AFL and Prompt Export Intent. |
| ValidatePromptExportIntent | Validate export readiness and constraints. |
| CreateExportArtifact | Create prompt text or other export artifact. |
| CancelExportJob | Cancel pending export preparation where applicable. |
| MarkExportArtifactReviewed | Mark artifact reviewed by user or workflow. |

Prompt Export Manager must not modify AFL source meaning.

---

## 7. Prompt Export Manager Queries

Conceptual queries:

| Query | Purpose |
|---|---|
| GetExportJob | Return export job metadata. |
| ListExportArtifacts | Return export artifacts for an owner reference. |
| GetExportArtifact | Return a specific export artifact. |
| GetExportValidationReport | Return export validation result. |

Queries must be read-only.

---

## 8. Prompt Export Manager Events

Conceptual events:

- PromptExportStarted
- PromptExportFinished
- PromptExportFailed
- ExportArtifactCreated
- ExportValidationFailed
- ExportArtifactReviewed

---

## 9. Plugin Manager Commands

Conceptual commands:

| Command | Purpose |
|---|---|
| DiscoverPlugins | Discover plugins through approved mechanisms. |
| ValidatePlugin | Validate metadata and compatibility. |
| EnablePlugin | Enable an approved plugin. |
| DisablePlugin | Disable a plugin. |
| RequestPluginCapability | Request a declared plugin capability. |
| ExecutePluginOperation | Execute an approved plugin operation through controlled boundary. |

Plugin Manager must not grant unrestricted project access.

---

## 10. Plugin Manager Queries

Conceptual queries:

| Query | Purpose |
|---|---|
| ListPlugins | Return available plugins. |
| GetPluginMetadata | Return metadata for one plugin. |
| GetPluginCapabilities | Return declared plugin capabilities. |
| GetPluginPermissionRequirements | Return required permissions. |
| GetPluginCompatibilityStatus | Return compatibility status. |

Queries must be read-only.

---

## 11. Plugin Manager Events

Conceptual events:

- PluginDiscovered
- PluginValidated
- PluginValidationFailed
- PluginEnabled
- PluginDisabled
- PluginPermissionRequired
- PluginOperationStarted
- PluginOperationFinished
- PluginOperationFailed

---

## 12. AFL-to-Export Boundary Rules

AFL is source meaning.

Prompt export artifacts are outputs.

Export may read AFL through approved interfaces.

Export must not modify AFL core structures.

Provider-specific syntax must remain in export artifacts or plugin logic.

AFL structures must remain provider-independent.

---

## 13. Plugin Boundary Rules

Plugins may receive only the minimum necessary data.

Plugins must declare capabilities.

Plugins must declare permission requirements.

Plugins must not directly mutate Aurora Core data.

Plugins must not access full project data unless a later security specification explicitly allows it.

Online provider plugins must not execute without user-initiated or approved operation.

---

## 14. Error Expectations

Possible errors:

| Error | Meaning |
|---|---|
| AFLValidationFailed | AFL structure is incomplete or contradictory. |
| AFLConflictDetected | Multiple AFL structures conflict. |
| ExportIntentInvalid | Prompt Export Intent is incomplete or invalid. |
| ExportTargetUnsupported | Requested export target is unsupported. |
| RequiredReferenceMissing | Required reference asset is missing. |
| PluginNotFound | Requested plugin is unavailable. |
| PluginPermissionDenied | Plugin lacks required permission. |
| PluginCompatibilityFailed | Plugin cannot run in current environment. |
| PluginOperationFailed | Controlled plugin execution failed. |

Errors must not silently alter AFL meaning.

---

## 15. Offline-First Requirements

AFL validation and local export preparation must work offline where technically possible.

Online plugin execution may require Internet access, but that requirement must be explicit.

---

## 16. Security Requirements

AFL, export and plugin workflows may expose private creative work.

Plugin access must be controlled.

Provider-bound data must be minimized.

Sensitive data transfer must be explicit and reviewable.

---

## 17. Testing Requirements

Future tests must verify:

- AFL validation behavior
- AFL conflict detection
- Export preparation behavior
- Export artifact separation
- Plugin discovery validation
- Plugin permission handling
- Plugin operation boundary enforcement
- Provider-specific syntax isolation
- Offline behavior
- Error behavior

---

## 18. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This document defines conceptual interface contracts only.

Implementation requires concrete data contracts, function signatures, plugin permission model, error types and test specifications.

---

## 19. Acceptance Criteria

This document is acceptable when:

1. AFL Engine commands are listed.
2. AFL Engine queries are listed.
3. AFL Engine events are listed.
4. Prompt Export Manager commands are listed.
5. Prompt Export Manager queries are listed.
6. Prompt Export Manager events are listed.
7. Plugin Manager commands are listed.
8. Plugin Manager queries are listed.
9. Plugin Manager events are listed.
10. AFL-to-export boundary rules are stated.
11. Plugin boundary rules are stated.
12. Error expectations are stated.
13. Offline-first requirements are stated.
14. Security requirements are stated.
15. Implementation readiness is explicitly marked Not Ready.

---

## 20. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

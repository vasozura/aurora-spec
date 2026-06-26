# Core Data Contracts

Document ID: DATA-000001  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 05-Data/DATA-000001_CORE_DATA_CONTRACTS.md  
Document Type: Data Contract Specification  
Depends On: AURORA_CONSTITUTION.md, AURORA_ENGINEERING_STANDARD.md, ARCHITECTURE.md, API-000001 through API-000005, MOD-000001 through MOD-000010, AFL-000001 through AFL-000010  

---

## 1. Purpose

This document defines conceptual core data contracts for Aurora Studio.

A data contract describes what categories of data exist, which module owns them, how identity should be treated, and what rules must exist before implementation.

This document does not define final JSON schema, database schema or Python classes.

---

## 2. Authority

This specification is subordinate to the Aurora Constitution, Aurora Engineering Standard, Review Standard and Architecture document.

If this document conflicts with ownership rules in module or interface specifications, implementation must stop until the conflict is reviewed.

---

## 3. Scope

This document defines:

- Core identity rules
- Versioning expectations
- Ownership categories
- Project data contract
- Workspace data contract
- Scene data contract
- Shot data contract
- Asset data contract
- Character data contract
- AFL validation data contract
- Prompt export artifact contract
- Plugin metadata contract
- Error and validation report contract
- Compatibility expectations
- Implementation readiness

---

## 4. Non-Scope

This document does not define:

- Final field names
- Final types
- JSON schema
- SQL schema
- ORM models
- File format
- Serialization format
- Migration code
- Validation code
- Implementation code

Those require later specifications.

---

## 5. Core Identity Rules

Every durable project entity must have stable identity.

Stable identity must not depend on:

- Prompt text
- Generated media output
- Provider response
- GUI position
- File display order
- Temporary runtime state

Future data specifications must define exact ID formats.

---

## 6. Versioning Rules

Durable data must be versioned where compatibility matters.

Versioning must support:

- Compatibility checks
- Migration decisions
- Clear error reporting
- Safe refusal when unsupported
- Future extension without silent corruption

Breaking data changes require ADR review.

---

## 7. Ownership Categories

Conceptual ownership categories:

| Data Category | Owning Module |
|---|---|
| Project identity and metadata | Project Manager |
| Active workspace context | Workspace |
| Scene meaning | Scene Manager |
| Shot meaning | Shot Manager |
| Timeline placement references | Timeline Manager |
| Asset metadata and availability | Asset Manager |
| Character identity and references | Character Manager |
| AFL validation state | AFL Engine |
| Export job metadata and artifacts | Prompt Export Manager |
| Plugin metadata and capability declarations | Plugin Manager |

A module must not directly mutate another module's owned data.

---

## 8. Project Data Contract

Project data conceptually includes:

- Project ID
- Project title
- Project version
- Created timestamp
- Modified timestamp
- Compatibility status
- Project settings reference
- Module data references
- Validation state reference

Project data must be recoverable where technically possible.

Project data must not contain provider secrets unless a later security specification explicitly allows it.

---

## 9. Workspace Data Contract

Workspace data conceptually includes:

- Active project reference
- Active workspace mode
- Active selection reference
- Active Scene reference
- Active Shot reference
- Active Timeline reference
- UI-independent workspace state

Workspace data is active context, not core creative meaning.

---

## 10. Scene Data Contract

Scene data conceptually includes:

- Scene ID
- Project reference
- Title
- Purpose
- Scene state
- Narrative context
- Time and location context
- Character Presence references
- Emotional Arc reference
- Visual Strategy reference
- Symbolic Layer reference
- Shot references
- Continuity requirements
- Export Intent reference
- Validation state

Final Scene fields must be defined in a later Scene data model specification.

---

## 11. Shot Data Contract

Shot data conceptually includes:

- Shot ID
- Parent Scene reference
- Title or label
- Ordering reference
- Shot state
- Shot Purpose
- Subject Focus
- Character Presence references
- Camera Intent reference
- Composition Intent reference
- Motion Intent reference
- Emotional Intent reference
- Visual Detail Intent
- Duration Intent
- Continuity requirements
- Reference asset requirements
- Export Intent reference
- Validation state

Final Shot fields must be defined in a later Shot data model specification.

---

## 12. Asset Data Contract

Asset data conceptually includes:

- Asset ID
- Asset type
- Asset display name
- Asset location reference
- Availability status
- Metadata
- Owner relationship references
- Created timestamp
- Modified timestamp

Asset location may be local or external only if later specifications approve.

External access rules require security review.

---

## 13. Character Data Contract

Character data conceptually includes:

- Character ID
- Display name
- Character identity metadata
- Reference asset links
- Continuity requirements
- Optional descriptive notes
- Validation state

Character data must be separated from scene-specific Character Presence.

---

## 14. AFL Validation Data Contract

AFL validation data conceptually includes:

- Validation report ID
- Target entity reference
- Validation status
- Errors
- Warnings
- Missing requirements
- Conflict references
- Created timestamp

Validation data must be reviewable.

Validation must not silently modify source meaning.

---

## 15. Prompt Export Artifact Contract

Export artifact data conceptually includes:

- Export artifact ID
- Source owner reference
- Export target
- Provider target where applicable
- Generated artifact type
- Artifact content or reference
- Created timestamp
- Review state
- Safety status
- Validation report reference

Export artifacts are not source meaning.

They may be regenerated.

---

## 16. Plugin Metadata Contract

Plugin metadata conceptually includes:

- Plugin ID
- Plugin name
- Version
- Capability declarations
- Permission declarations
- Compatibility status
- Enabled or disabled state
- Provider target where applicable

Plugins must not be trusted by default.

Permission rules require later security and SDK specifications.

---

## 17. Error Contract

Errors conceptually include:

- Error code
- Human-readable message
- Operation
- Target reference
- Severity
- Recoverability
- Whether data changed
- Suggested user action where applicable

Errors must be meaningful and reviewable.

---

## 18. Validation Report Contract

Validation reports conceptually include:

- Report ID
- Target reference
- Status
- Errors
- Warnings
- Informational notes
- Validation rules applied
- Created timestamp

Validation reports must not hide failed rules.

---

## 19. Compatibility Expectations

Future data implementation must support:

- Version checks
- Compatibility reports
- Safe loading behavior
- Migration decisions
- Clear refusal when unsupported
- No silent destructive conversion

---

## 20. Security Expectations

Data contracts must preserve user ownership.

Private creative data must not be sent externally unless the user initiates or approves the operation.

Provider plugins must receive minimum necessary data.

---

## 21. Offline-First Expectations

Core data must remain usable offline.

Project open, edit, save and validation must not require online services.

Provider execution may require online access, but provider execution is not core data behavior.

---

## 22. Testing Requirements

Future data implementation must test:

- Stable identity
- Ownership boundaries
- Version compatibility
- Validation report structure
- Error structure
- Offline save/load behavior
- Safe refusal on unsupported versions
- Separation of source meaning and export artifacts

---

## 23. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This document defines conceptual data contracts only.

Implementation requires concrete schemas, field definitions, migrations, serializers, validators and tests.

---

## 24. Acceptance Criteria

This document is acceptable when:

1. Core identity rules are defined.
2. Versioning rules are defined.
3. Ownership categories are defined.
4. Project data contract is introduced.
5. Workspace data contract is introduced.
6. Scene data contract is introduced.
7. Shot data contract is introduced.
8. Asset data contract is introduced.
9. Character data contract is introduced.
10. AFL validation data contract is introduced.
11. Prompt export artifact contract is introduced.
12. Plugin metadata contract is introduced.
13. Error contract is introduced.
14. Validation report contract is introduced.
15. Compatibility expectations are stated.
16. Security expectations are stated.
17. Offline-first expectations are stated.
18. Testing requirements are stated.
19. Implementation readiness is explicitly marked Not Ready.

---

## 25. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

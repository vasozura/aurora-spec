# Asset and Character Interfaces

Document ID: API-000004  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 04-Interfaces/API-000004_ASSET_CHARACTER_INTERFACES.md  
Document Type: Interface Specification  
Depends On: API-000001_CORE_INTERFACE_PRINCIPLES.md, MOD-000006_ASSET_MANAGER_SPEC.md, MOD-000007_CHARACTER_MANAGER_SPEC.md  

---

## 1. Purpose

This document defines conceptual interfaces for Asset Manager and Character Manager.

These interfaces preserve ownership boundaries for assets, character identity and reference relationships.

This document does not define code signatures.

---

## 2. Scope

This specification covers:

- Asset Manager commands, queries and events
- Character Manager commands, queries and events
- Asset-Character relationship rules
- Reference asset availability expectations
- Error expectations
- Offline-first expectations
- Security expectations

---

## 3. Asset Manager Commands

Conceptual commands:

| Command | Purpose |
|---|---|
| ImportAsset | Register an asset reference in the project. |
| UpdateAssetMetadata | Update asset-owned metadata. |
| RemoveAsset | Remove an asset reference according to approved rules. |
| ValidateAsset | Validate asset availability and metadata. |
| LinkAssetToOwner | Link asset to Scene, Shot, Character or Symbol by approved reference. |
| UnlinkAssetFromOwner | Remove approved relationship reference. |
| MarkAssetMissing | Mark asset as unavailable when reference cannot be resolved. |

Asset commands must not rewrite Scene, Shot or Character meaning directly.

---

## 4. Asset Manager Queries

Conceptual queries:

| Query | Purpose |
|---|---|
| GetAsset | Return asset metadata by ID. |
| ListAssets | Return project asset references. |
| ListAssetsByType | Return assets filtered by type. |
| GetAssetAvailability | Return availability status. |
| GetAssetsForOwner | Return assets linked to an owner reference. |

Queries must be read-only.

---

## 5. Asset Manager Events

Conceptual events:

- AssetImported
- AssetUpdated
- AssetRemoved
- AssetLinked
- AssetUnlinked
- AssetMissing
- AssetValidated
- AssetValidationFailed

---

## 6. Character Manager Commands

Conceptual commands:

| Command | Purpose |
|---|---|
| CreateCharacter | Create a character identity record. |
| UpdateCharacter | Update character-owned identity data. |
| RenameCharacter | Rename or relabel a character. |
| ArchiveCharacter | Archive a character. |
| DeleteCharacter | Delete according to approved deletion rules. |
| AddCharacterReferenceAsset | Link a reference asset to a character. |
| RemoveCharacterReferenceAsset | Remove character reference asset link. |
| ValidateCharacter | Validate character identity and required references. |

Character commands must not own Scene-specific Character Presence.

---

## 7. Character Manager Queries

Conceptual queries:

| Query | Purpose |
|---|---|
| GetCharacter | Return character identity by ID. |
| ListCharacters | Return characters in a project. |
| GetCharacterReferences | Return reference assets for a character. |
| GetCharacterContinuityRules | Return character continuity expectations. |
| GetCharacterValidationReport | Return latest validation report. |

Queries must be read-only.

---

## 8. Character Manager Events

Conceptual events:

- CharacterCreated
- CharacterUpdated
- CharacterRenamed
- CharacterArchived
- CharacterDeleted
- CharacterReferenceAdded
- CharacterReferenceRemoved
- CharacterReferenceMissing
- CharacterValidated
- CharacterValidationFailed

---

## 9. Asset-Character Relationship Rules

Character Manager may reference assets owned by Asset Manager.

Asset Manager owns asset metadata and availability.

Character Manager owns character identity and continuity rules.

Scene-specific Character Presence belongs to Scene or Shot context, not Character Manager.

Reference assets must be validated before export when required.

---

## 10. Error Expectations

Possible errors:

| Error | Meaning |
|---|---|
| AssetNotFound | Requested asset does not exist. |
| AssetUnavailable | Asset reference cannot be resolved. |
| InvalidAssetOwner | Requested asset link owner is invalid. |
| CharacterNotFound | Requested character does not exist. |
| CharacterValidationFailed | Character identity or reference requirements are incomplete. |
| CharacterReferenceMissing | Required character reference asset is missing. |

Errors must not silently remove references or rewrite character identity.

---

## 11. Offline-First Requirements

Local asset reference management and character management must work offline where technically possible.

Online provider reference upload is outside this interface.

---

## 12. Security Requirements

Assets and character references may contain private user material.

Provider access must be routed through Prompt Export Manager and Plugin Manager.

The system must avoid sending reference assets externally without user-initiated or approved operation.

---

## 13. Testing Requirements

Future tests must verify:

- Asset import validation
- Asset metadata updates
- Asset availability checks
- Asset relationship linking
- Character creation and update validation
- Character reference validation
- Missing asset handling
- Query read-only behavior
- Event emission
- Offline behavior

---

## 14. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This document defines conceptual interface contracts only.

Implementation requires concrete data contracts, function signatures, error types and test specifications.

---

## 15. Acceptance Criteria

This document is acceptable when:

1. Asset commands are listed.
2. Asset queries are listed.
3. Asset events are listed.
4. Character commands are listed.
5. Character queries are listed.
6. Character events are listed.
7. Asset-Character relationship rules are stated.
8. Error expectations are stated.
9. Offline-first requirements are stated.
10. Security requirements are stated.
11. Implementation readiness is explicitly marked Not Ready.

---

## 16. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

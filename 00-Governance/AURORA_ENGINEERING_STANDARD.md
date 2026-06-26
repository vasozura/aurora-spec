# Aurora Engineering Standard

Document ID: GOV-000002  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 00-Governance/AURORA_ENGINEERING_STANDARD.md  
Document Type: Engineering Standard  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 02-Architecture/ARCHITECTURE.md  

---

## 1. Purpose

This document defines the engineering standard used to create, review, version and implement Aurora Studio specifications.

Aurora Engineering Standard, abbreviated as AES, exists to make Aurora development deterministic, reviewable and executable by both human contributors and AI implementation agents.

AES defines how specifications are written, how tasks are structured, how AI agents are instructed, how reviews are performed and how implementation is allowed to begin.

---

## 2. Authority

AES is subordinate to the Aurora Constitution.

If AES conflicts with the Aurora Constitution, the Constitution takes precedence.

AES has authority over:

- Specification structure
- Task structure
- AI implementation rules
- Review process
- Document lifecycle
- Module lifecycle
- Change control
- Release preparation

Implementation must follow AES unless an approved Architecture Decision Record explicitly defines an exception.

---

## 3. Core Principle

Aurora is not developed from vague prompts.

Aurora is developed from version-controlled specifications.

The specification repository is treated as the source code of the product definition.

Implementation code must be generated or written only after the required specification and review phases are complete.

---

## 4. Repository Model

Aurora development is divided into three related repositories or workspaces:

1. `aurora-spec`
2. `aurora-studio`
3. `aurora-assets`

`aurora-spec` defines product truth.

`aurora-studio` contains implementation code.

`aurora-assets` may contain sample media, design references, test assets and non-code supporting material.

During Sprint-0, only `aurora-spec` is in scope.

---

## 5. Required Repository Structure

The `aurora-spec` repository must use the following top-level structure:

```text
aurora-spec/
├── README.md
├── 00-Governance/
├── 01-Product/
├── 02-Architecture/
├── 03-Modules/
├── 04-Interfaces/
├── 05-Data/
├── 06-AI/
├── 07-SDK/
├── 08-Tasks/
├── 09-Tests/
├── 10-ADR/
├── 11-RFC/
├── 12-Templates/
└── 99-Archive/
```

This structure is stable.

Changes to the top-level structure require an approved ADR.

---

## 6. Document Identity Standard

Every controlled document must have a unique document ID.

ID families:

- `GOV-000001` for governance documents
- `PROD-000001` for product documents
- `ARCH-000001` for architecture documents
- `MOD-000001` for module specifications
- `API-000001` for public interface specifications
- `DATA-000001` for data specifications
- `AI-000001` for AI behavior specifications
- `SDK-000001` for SDK specifications
- `TASK-000001` for implementation or documentation tasks
- `TEST-000001` for test specifications
- `ADR-000001` for Architecture Decision Records
- `RFC-000001` for Requests for Comments
- `AFL-000001` for Aurora Film Language specifications

IDs must never be reused.

IDs must not be renamed after approval.

If a document is replaced, the old ID remains in history and the new document receives a new ID.

---

## 7. Versioning Standard

Documents use semantic versioning:

```text
MAJOR.MINOR.PATCH
```

Version meaning:

- `MAJOR` changes indicate breaking conceptual or structural changes.
- `MINOR` changes indicate compatible additions or clarifications.
- `PATCH` changes indicate corrections, formatting fixes or non-behavioral edits.

Initial draft documents start at:

```text
0.1.0
```

Approved baseline documents may become:

```text
1.0.0
```

---

## 8. Document Status Standard

Allowed document statuses:

- `Draft`
- `Review`
- `Approved`
- `Deprecated`
- `Superseded`
- `Archived`

Meaning:

`Draft` means the document is actively being created.

`Review` means the document is ready for review but not yet approved.

`Approved` means the document may be used for implementation.

`Deprecated` means the document should not be used for new work.

`Superseded` means another document has replaced it.

`Archived` means the document is retained only for historical reference.

Implementation must not begin from a `Draft` document unless the task explicitly allows it.

---

## 9. Required Metadata Header

Every controlled Markdown document must begin with a metadata block.

Required fields:

```text
Document ID:
Version:
Status:
Owner:
Repository:
Path:
Document Type:
Depends On:
```

Task documents must begin with:

```text
Task ID:
Version:
Status:
Priority:
Sprint:
Document Type:
Target Repository:
Target File:
Depends On:
Required Input:
```

Metadata must be plain text.

YAML front matter is not required in Sprint-0.

---

## 10. Specification Document Standard

Every specification document must include:

1. Purpose
2. Authority or dependency
3. Scope
4. Non-scope
5. Definitions
6. Requirements
7. Constraints
8. Acceptance criteria
9. Change control
10. Summary

Specifications must be written for deterministic execution.

A specification must not contain hidden assumptions.

A specification must not require the AI implementation agent to guess.

---

## 11. Task Document Standard

Every task must include:

1. Objective
2. Strict scope
3. Preconditions
4. Required action
5. Forbidden actions
6. Validation
7. Expected report
8. Markdown content or implementation instructions, when applicable

Tasks must be small.

Tasks must be reviewable.

Tasks must be reversible.

Tasks must not combine unrelated work.

Tasks must not allow uncontrolled continuation.

---

## 12. AI Implementation Agent Role

An AI implementation agent working on Aurora is an implementation engineer.

The AI agent is not the architect unless explicitly assigned that role.

The AI agent must:

- Execute only the assigned task
- Read required input files
- Respect target files
- Stop on missing prerequisites
- Report ambiguity
- Avoid guessing
- Avoid adding hidden behavior
- Avoid changing public interfaces
- Avoid creating files outside scope
- Produce a short implementation report

The AI agent must not:

- Invent architecture
- Add dependencies without permission
- Continue to the next task
- Rewrite existing documents without instruction
- Rename IDs
- Merge tasks
- Add implementation code to specification tasks

---

## 13. Module Lifecycle

Every Aurora module must pass through eight phases before implementation begins.

The phases are:

1. Vision
2. Specification
3. Architecture
4. Data Model
5. Public API
6. Tests
7. AI Tasks
8. Review

### Phase 1: Vision

Defines why the module exists.

### Phase 2: Specification

Defines what the module does.

### Phase 3: Architecture

Defines how the module fits into Aurora architecture.

### Phase 4: Data Model

Defines what data the module owns, reads and writes.

### Phase 5: Public API

Defines what the module exposes to other modules.

### Phase 6: Tests

Defines how the module is validated.

### Phase 7: AI Tasks

Defines small implementation tasks for AI coding agents.

### Phase 8: Review

Confirms that the module is ready for implementation.

A module is not ready for implementation until all eight phases are complete or an approved exception exists.

---

## 14. Review Standard

Every controlled document must be reviewable.

A review must check:

- Correct path
- Correct document ID
- Correct version
- Correct status
- Correct dependencies
- Consistency with Constitution
- Consistency with Architecture
- Scope clarity
- Non-scope clarity
- Acceptance criteria
- AI executability
- Absence of uncontrolled assumptions

A document that cannot be reviewed clearly is not ready.

---

## 15. Change Control

Changes must be traceable.

Every significant change must include:

- Reason for change
- Affected documents
- Affected modules
- Compatibility impact
- Review decision

Breaking architectural changes require an ADR.

Large conceptual proposals should begin as an RFC.

---

## 16. ADR Standard

An Architecture Decision Record must be used when a decision:

- Changes architecture
- Changes dependency direction
- Changes public APIs
- Adds major technology dependencies
- Changes storage model
- Changes plugin boundaries
- Changes security boundaries
- Creates a long-term constraint

ADR documents must be stored in:

```text
10-ADR/
```

---

## 17. RFC Standard

A Request for Comments must be used when an idea requires discussion before approval.

RFC documents must be stored in:

```text
11-RFC/
```

An RFC may later become:

- A specification
- An ADR
- A rejected proposal
- An archived idea

---

## 18. Testing Standard

Testing must be planned before implementation.

Test specifications must define:

- What is being tested
- Expected behavior
- Input conditions
- Output conditions
- Failure cases
- Regression cases
- Acceptance criteria

Test specifications must be stored in:

```text
09-Tests/
```

---

## 19. AI Task Size Standard

AI tasks should be small enough to complete, review and revert independently.

Preferred task size:

- One document
- One module phase
- One interface
- One data model
- One test group
- One implementation unit

Large tasks must be split.

A task that asks an AI agent to "build Aurora" is invalid.

---

## 20. Forbidden Development Pattern

The following pattern is forbidden:

```text
Idea → AI prompt → Code → Fix errors → Invent architecture later
```

Aurora uses this pattern instead:

```text
Idea → Specification → Architecture → Data → API → Tests → AI Tasks → Review → Code
```

---

## 21. Implementation Readiness

A feature or module is ready for implementation only when:

1. Its specification is complete.
2. Its architectural placement is clear.
3. Its data ownership is defined.
4. Its public interfaces are defined.
5. Its tests are defined.
6. Its AI tasks are written.
7. Its review is complete.
8. No constitutional conflict exists.

---

## 22. Sprint-0 Standard

Sprint-0 is documentation-only.

Sprint-0 must not create Aurora Studio implementation code.

Sprint-0 may create:

- Governance documents
- Architecture documents
- Templates
- Task documents
- Review standards
- AI implementation protocol
- Glossary
- Roadmap
- Initial AFL documents

Sprint-0 must establish the rules before implementation begins.

---

## 23. Commit Standard

Each completed task should result in a small commit.

Commit messages should use this pattern:

```text
TASK-000004: create Aurora Engineering Standard
```

A commit should not contain unrelated work.

---

## 24. Completion Report Standard

Every AI task must end with a short report containing:

1. Files created or updated
2. Preconditions verified
3. Validation performed
4. Confirmation of scope compliance
5. Deviations, if any
6. Readiness for commit

The report must be factual.

The report must not claim work that was not performed.

---

## 25. Summary

Aurora Engineering Standard exists to prevent uncontrolled AI-generated development.

AES makes Aurora development structured, deterministic, reviewable and maintainable.

Every future specification, task, review and implementation must follow this standard unless an approved exception exists.

The goal is not speed alone.

The goal is controlled progress.

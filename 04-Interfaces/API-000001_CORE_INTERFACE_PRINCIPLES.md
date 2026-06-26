# Core Interface Principles

Document ID: API-000001  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 04-Interfaces/API-000001_CORE_INTERFACE_PRINCIPLES.md  
Document Type: Interface Specification  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, 02-Architecture/ARCHITECTURE.md, 03-Modules/MOD-000001_PROJECT_MANAGER_SPEC.md through 03-Modules/MOD-000010_PLUGIN_MANAGER_SPEC.md  

---

## 1. Purpose

This document defines the core interface principles for Aurora Studio.

Interfaces define how modules communicate without violating ownership boundaries.

Interfaces are not implementation code.

Interfaces are not database schemas.

Interfaces are not GUI contracts.

Interfaces are controlled agreements between modules.

---

## 2. Authority

This specification is subordinate to the Aurora Constitution, Aurora Engineering Standard, Review Standard and Architecture document.

If this document conflicts with the Aurora Constitution, the Constitution takes precedence.

If this document conflicts with module specifications, implementation must stop until the conflict is reviewed.

---

## 3. Scope

This document defines:

- Interface purpose
- Interface boundaries
- Command principles
- Query principles
- Event principles
- Error principles
- Ownership rules
- Cross-module communication rules
- Offline-first expectations
- Security expectations
- Testing expectations
- Implementation readiness

---

## 4. Non-Scope

This document does not define:

- Final programming language interfaces
- Python abstract classes
- REST APIs
- GraphQL schema
- Database schema
- GUI event handlers
- Plugin SDK code
- Provider API calls
- Serialization format
- Implementation code

---

## 5. Interface Types

Aurora interfaces may use three conceptual interaction types:

1. Commands
2. Queries
3. Events

A Command asks a module to perform an action.

A Query asks a module to return information.

An Event announces that something happened.

Commands may change state.

Queries must not change state.

Events must not require the sender to know who will consume them.

---

## 6. Command Principles

Commands must:

- Have one clear purpose
- Target one owning module
- Validate required input
- Return meaningful success or failure
- Avoid hidden side effects
- Respect data ownership boundaries
- Preserve offline-first behavior where possible
- Avoid provider-specific dependencies unless routed through approved plugin boundaries

Commands must not:

- Modify data owned by unrelated modules directly
- Trigger uncontrolled provider calls
- Hide validation failures
- Rewrite user creative meaning silently

---

## 7. Query Principles

Queries must:

- Be read-only
- Have explicit input
- Return stable conceptual data
- Avoid hidden mutation
- Avoid provider calls
- Respect access boundaries
- Return meaningful errors when data is missing

Queries must not:

- Modify project state
- Create missing data silently
- Execute generation workflows
- Change active workspace state unless explicitly defined as a command

---

## 8. Event Principles

Events must:

- Represent something that already happened
- Use past-tense names where possible
- Include enough context for subscribers to react safely
- Avoid carrying unnecessary private data
- Avoid provider-specific payloads unless emitted by approved plugin/export boundaries
- Be versioned when event schema is later defined

Events must not:

- Be used as commands
- Require synchronous handling by unrelated modules
- Contain full project data unless explicitly approved
- Leak sensitive user creative data unnecessarily

---

## 9. Ownership Rules

Each module owns its own data.

A module may expose commands and queries for controlled access.

A module must not directly mutate another module's owned data.

Cross-module changes must happen through approved commands or coordinated application services.

If ownership is unclear, implementation must stop and require specification review.

---

## 10. Error Rules

Interface errors must be explicit.

Errors must identify:

- What operation failed
- Why it failed
- Whether user action is required
- Whether data was changed
- Whether retry is safe

Errors must not silently rewrite creative meaning.

Errors must not corrupt project data.

---

## 11. Offline-First Rules

Interfaces must support offline operation wherever technically possible.

Commands and queries for local project work must not require online services.

Online provider calls must use approved plugin or export interfaces.

If an operation requires Internet access, that must be explicit.

---

## 12. Security Rules

Interfaces must use minimum necessary data.

Modules must not expose full project data when a smaller contract is enough.

Provider plugins must receive only data required for selected export or generation.

Sensitive data movement must be explicit and reviewable.

---

## 13. Testing Requirements

Future implementation must test:

- Command success behavior
- Command validation failure behavior
- Query read-only behavior
- Event emission behavior
- Ownership boundary enforcement
- Error behavior
- Offline behavior
- Security boundary behavior

This document does not create tests.

---

## 14. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This document defines interface principles only.

Implementation requires concrete interface specifications, data contracts and test specifications.

---

## 15. Acceptance Criteria

This document is acceptable when:

1. Commands are defined conceptually.
2. Queries are defined conceptually.
3. Events are defined conceptually.
4. Ownership boundaries are stated.
5. Error rules are stated.
6. Offline-first rules are stated.
7. Security rules are stated.
8. Testing requirements are stated.
9. Implementation readiness is explicitly marked Not Ready.

---

## 16. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

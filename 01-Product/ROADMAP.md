# Aurora Roadmap

Document ID: PROD-000002  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 01-Product/ROADMAP.md  
Document Type: Product Roadmap  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, 01-Product/GLOSSARY.md, 02-Architecture/ARCHITECTURE.md  

---

## 1. Purpose

This document defines the early development roadmap for Aurora.

The roadmap describes the intended sequence of work from Sprint-0 governance foundations to Aurora Film Language, module specifications, interface specifications, data models, AI implementation tasks and the future Aurora Studio implementation skeleton.

This roadmap is not an implementation plan for code.

This roadmap defines order, dependency and readiness.

---

## 2. Authority

This roadmap is subordinate to:

- 00-Governance/AURORA_CONSTITUTION.md
- 00-Governance/AURORA_ENGINEERING_STANDARD.md
- 00-Governance/REVIEW_STANDARD.md
- 02-Architecture/ARCHITECTURE.md

If this roadmap conflicts with the Constitution, the Constitution takes precedence.

If this roadmap conflicts with AES, AES takes precedence.

---

## 3. Roadmap Principle

Aurora must be developed in the following order:

```text
Governance
  ↓
Architecture
  ↓
Templates
  ↓
Glossary
  ↓
Product Roadmap
  ↓
Aurora Film Language
  ↓
Module Specifications
  ↓
Interface Specifications
  ↓
Data Specifications
  ↓
Test Specifications
  ↓
AI Implementation Tasks
  ↓
Implementation Skeleton
  ↓
Feature Implementation
```

Implementation must not begin before the required specifications exist.

The roadmap prevents premature coding.

---

## 4. Current Strategic Direction

Aurora development is divided into three major workstreams:

1. `aurora-spec`
2. `aurora-studio`
3. `aurora-assets`

### 4.1 `aurora-spec`

Defines product truth, architecture, standards, specifications, tasks, ADRs and RFCs.

This is the current active workstream.

### 4.2 `aurora-studio`

Will contain the future application implementation.

This must not begin until the required specification baseline is ready.

### 4.3 `aurora-assets`

Will contain sample assets, references, media fixtures and testing resources when needed.

This is not required during early Sprint-0.

---

## 5. Sprint-0: Specification Foundation

Sprint-0 is documentation-only.

Sprint-0 establishes the engineering system before implementation begins.

Sprint-0 must not create Aurora Studio code.

Sprint-0 must not create Python packages.

Sprint-0 must not create GUI files.

Sprint-0 must not create database schemas.

Sprint-0 must not create plugins.

### Sprint-0 Goals

Sprint-0 must create:

- Governance foundation
- Architecture foundation
- AI implementation protocol
- Review system
- Templates
- Glossary
- Roadmap
- Initial AFL planning foundation

### Sprint-0 Required Documents

Sprint-0 should include the following controlled documents:

```text
00-Governance/AURORA_CONSTITUTION.md
00-Governance/AURORA_ENGINEERING_STANDARD.md
00-Governance/REVIEW_STANDARD.md
00-Governance/AI_IMPLEMENTATION_PROTOCOL.md
01-Product/GLOSSARY.md
01-Product/ROADMAP.md
02-Architecture/ARCHITECTURE.md
12-Templates/TASK_TEMPLATE.md
12-Templates/ADR_TEMPLATE.md
12-Templates/RFC_TEMPLATE.md
12-Templates/SPEC_TEMPLATE.md
```

### Sprint-0 Completion Criteria

Sprint-0 is complete when:

1. Governance documents exist.
2. Architecture foundation exists.
3. Templates exist.
4. Glossary exists.
5. Roadmap exists.
6. AI task protocol exists.
7. Review standard exists.
8. Future tasks can be created from templates.
9. AI agents can be controlled by task documents.
10. No implementation code has been created.

---

## 6. Sprint-1: Aurora Film Language Foundation

Sprint-1 defines the conceptual foundation of Aurora Film Language.

AFL is the internal language of Aurora.

Prompt text is an export format, not the internal source of truth.

### Sprint-1 Goals

Sprint-1 must define:

- AFL purpose
- AFL scope
- AFL non-scope
- Core cinematic concepts
- Scene structure
- Shot structure
- Character references
- Emotion model
- Symbol model
- Camera model
- Composition model
- Motion model
- Transition model
- Prompt export relationship

### Sprint-1 Candidate Documents

```text
06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md
06-AI/AFL-000002_SCENE_MODEL_SPEC.md
06-AI/AFL-000003_SHOT_MODEL_SPEC.md
06-AI/AFL-000004_EMOTION_MODEL_SPEC.md
06-AI/AFL-000005_CAMERA_MODEL_SPEC.md
06-AI/AFL-000006_COMPOSITION_MODEL_SPEC.md
06-AI/AFL-000007_SYMBOL_MODEL_SPEC.md
06-AI/AFL-000008_MOTION_MODEL_SPEC.md
06-AI/AFL-000009_TRANSITION_MODEL_SPEC.md
06-AI/AFL-000010_PROMPT_EXPORT_INTENT_SPEC.md
```

### Sprint-1 Completion Criteria

Sprint-1 is complete when:

1. AFL overview exists.
2. Core AFL concepts are defined.
3. AFL is clearly separated from prompts.
4. Scene and shot concepts are specified.
5. Emotion, camera, composition, symbol and motion are specified.
6. Prompt export is defined as output.
7. AFL documents are reviewable.
8. Future module specifications can depend on AFL.

---

## 7. Sprint-2: Core Module Specifications

Sprint-2 defines the first major Aurora modules.

This sprint is still specification-only.

No implementation code is allowed unless a later approved task explicitly starts implementation.

### Sprint-2 Goals

Sprint-2 must define module responsibilities and boundaries.

Initial module candidates:

```text
MOD-000001 Project Manager
MOD-000002 Workspace
MOD-000003 Scene Manager
MOD-000004 Shot Manager
MOD-000005 Timeline Manager
MOD-000006 Asset Manager
MOD-000007 Character Manager
MOD-000008 AFL Engine
MOD-000009 Prompt Export Manager
MOD-000010 Plugin Manager
```

### Required Module Phases

Each module must follow the eight-phase lifecycle:

1. Vision
2. Specification
3. Architecture
4. Data Model
5. Public API
6. Tests
7. AI Tasks
8. Review

### Sprint-2 Completion Criteria

Sprint-2 is complete when:

1. Initial module list is approved.
2. Each selected module has clear responsibility.
3. Module boundaries are defined.
4. Module dependencies are documented.
5. No module violates architecture layers.
6. No module depends directly on a provider-specific AI system.
7. Follow-up interface and data specifications are identified.

---

## 8. Sprint-3: Interfaces and Data Models

Sprint-3 defines public interfaces and data ownership.

This sprint converts module boundaries into contracts.

### Sprint-3 Goals

Sprint-3 must define:

- Public APIs
- Events
- Commands
- Queries
- Data ownership
- Data schemas
- Persistence expectations
- Project structure expectations
- Compatibility rules

### Candidate Interface Documents

```text
04-Interfaces/API-000001_PROJECT_API_SPEC.md
04-Interfaces/API-000002_SCENE_API_SPEC.md
04-Interfaces/API-000003_TIMELINE_API_SPEC.md
04-Interfaces/API-000004_ASSET_API_SPEC.md
04-Interfaces/API-000005_PLUGIN_API_SPEC.md
04-Interfaces/API-000006_PROMPT_EXPORT_API_SPEC.md
```

### Candidate Data Documents

```text
05-Data/DATA-000001_PROJECT_STRUCTURE_SPEC.md
05-Data/DATA-000002_SCENE_DATA_MODEL_SPEC.md
05-Data/DATA-000003_SHOT_DATA_MODEL_SPEC.md
05-Data/DATA-000004_ASSET_DATA_MODEL_SPEC.md
05-Data/DATA-000005_AFL_DATA_MODEL_SPEC.md
05-Data/DATA-000006_PLUGIN_METADATA_SPEC.md
```

### Sprint-3 Completion Criteria

Sprint-3 is complete when:

1. Public interfaces are defined.
2. Data ownership is explicit.
3. Events are defined or planned.
4. Project data structure is specified.
5. Compatibility risks are identified.
6. Breaking decisions have ADRs.
7. Future implementation tasks can reference stable contracts.

---

## 9. Sprint-4: Test Specifications and AI Task Breakdown

Sprint-4 prepares implementation.

This sprint defines tests and implementation tasks, but still does not require code.

### Sprint-4 Goals

Sprint-4 must define:

- Test specifications
- Acceptance tests
- Regression test strategy
- AI task breakdown
- Implementation sequencing
- Validation commands
- Review gates

### Candidate Test Documents

```text
09-Tests/TEST-000001_PROJECT_MANAGER_TEST_SPEC.md
09-Tests/TEST-000002_SCENE_MANAGER_TEST_SPEC.md
09-Tests/TEST-000003_AFL_ENGINE_TEST_SPEC.md
09-Tests/TEST-000004_PROMPT_EXPORT_TEST_SPEC.md
09-Tests/TEST-000005_PLUGIN_MANAGER_TEST_SPEC.md
```

### Candidate AI Task Groups

```text
08-Tasks/Sprint-1/
08-Tasks/Sprint-2/
08-Tasks/Sprint-3/
08-Tasks/Implementation-0/
```

### Sprint-4 Completion Criteria

Sprint-4 is complete when:

1. Required test specifications exist.
2. AI implementation tasks are small and scoped.
3. Validation commands are defined where applicable.
4. Implementation order is clear.
5. No AI task requires guessing.
6. Review gates are defined.
7. Implementation may begin safely.

---

## 10. Sprint-5: Aurora Studio Implementation Skeleton

Sprint-5 is the earliest point where code may begin.

The first implementation sprint must create only the application skeleton.

No business logic should be implemented in the first code task.

### Sprint-5 Goals

Sprint-5 may create:

- Repository structure
- Python project configuration
- Package structure
- Basic test configuration
- Linting configuration
- Formatting configuration
- Type-checking configuration
- Pre-commit configuration

### Sprint-5 Must Not Create

Sprint-5 must not create:

- Full GUI
- Business logic
- Plugin implementations
- AI provider integration
- Database schema unless explicitly specified
- Prompt generation behavior
- AFL execution behavior

### Sprint-5 Completion Criteria

Sprint-5 is complete when:

1. `aurora-studio` skeleton exists.
2. Development tools are configured.
3. Empty tests run successfully.
4. No business logic exists.
5. No architecture is invented in code.
6. Repository is ready for small implementation tasks.

---

## 11. Sprint-6: First Implementation Units

Sprint-6 may begin implementing small, approved units.

Candidate first implementation units:

```text
Project file structure validation
Project metadata model
Basic project create/open/save flow
Internal event type definitions
Initial AFL data classes
Basic prompt export placeholder from approved AFL structures
```

Every implementation unit must reference:

- Approved specification
- Approved data model
- Approved interface
- Required tests
- AI task document

### Sprint-6 Completion Criteria

Sprint-6 is complete when:

1. First implementation unit is complete.
2. Tests pass.
3. Scope is preserved.
4. Review confirms no architecture drift.
5. Future implementation can continue incrementally.

---

## 12. Major Milestones

### Milestone M0: Governance Baseline

Expected outcome:

```text
Aurora can control AI-assisted development.
```

Includes:

- Constitution
- AES
- Review Standard
- AI Implementation Protocol
- Templates

### Milestone M1: Product Language Baseline

Expected outcome:

```text
Aurora has a shared vocabulary and AFL foundation.
```

Includes:

- Glossary
- AFL overview
- Core cinematic concepts

### Milestone M2: Module Baseline

Expected outcome:

```text
Aurora has defined module boundaries.
```

Includes:

- Project Manager spec
- Scene Manager spec
- Asset Manager spec
- Timeline Manager spec
- Plugin Manager spec

### Milestone M3: Contract Baseline

Expected outcome:

```text
Aurora modules can communicate through approved interfaces.
```

Includes:

- APIs
- Events
- Data models

### Milestone M4: Implementation Readiness

Expected outcome:

```text
AI coding agents can begin implementation safely.
```

Includes:

- Test specifications
- AI task breakdown
- Review gates

### Milestone M5: Application Skeleton

Expected outcome:

```text
Aurora Studio exists as an empty but valid application workspace.
```

Includes:

- Project skeleton
- Tooling
- Empty tests
- No business logic

---

## 13. Explicit Non-Goals

This roadmap does not define:

- Exact release dates
- Staffing plan
- Funding plan
- Marketing plan
- UI design
- Full feature list
- Implementation code
- Database schema
- Plugin SDK details
- Provider integrations

Those require separate documents.

---

## 14. Risk Areas

Known risks:

1. Premature implementation
2. AI scope expansion
3. Architecture drift
4. Undefined AFL concepts
5. Provider lock-in
6. Plugin boundary confusion
7. Data model instability
8. Overly large tasks
9. Weak review discipline
10. Treating prompts as internal source of truth

Each risk must be controlled through specification, review and task discipline.

---

## 15. Roadmap Change Rules

This roadmap may change only through review.

Changes must update:

- Version
- Change history
- Affected milestones
- Affected sprints
- Affected dependencies

Major roadmap changes may require an RFC.

Architecture-impacting roadmap changes may require an ADR.

---

## 16. Acceptance Criteria

This roadmap is acceptable when:

1. Sprint order is clear.
2. Sprint-0 remains documentation-only.
3. AFL is placed before implementation.
4. Module specifications are placed before code.
5. Interface and data specifications are placed before code.
6. Tests are planned before implementation.
7. AI task breakdown happens before implementation.
8. Implementation skeleton does not begin prematurely.
9. Milestones are clear.
10. Risks are identified.
11. The roadmap is consistent with the Aurora Constitution.
12. The roadmap is consistent with AES.
13. The roadmap is consistent with the Architecture document.

---

## 17. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-26 | Initial draft | Aurora Labs |

---

## 18. Summary

Aurora must be built in controlled stages.

The first product is not code.

The first product is a specification system that makes correct code possible.

This roadmap protects Aurora from premature implementation and uncontrolled AI development.

The next major product milestone after Sprint-0 is Aurora Film Language.

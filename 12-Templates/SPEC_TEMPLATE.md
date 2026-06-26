---
id: TEMPLATE-0001
title: Module Specification Template
version: 0.1.0
status: Draft
owner: Aurora Labs
created: 2026-06-26
updated: 2026-06-26
depends_on: [GOV-0001, GOV-0003]
---

# Module Specification Template

## Purpose

This template defines the required structure for all Aurora Studio module specification documents.
Every module specification must follow this template exactly.
A module with an incomplete specification is not implementation-ready.

## Scope

All module specifications written for `aurora-spec/03-Modules/`.

## Non-Goals

- This template does not contain implementation guidance.
- This template does not define test cases (see TEMPLATE for test specs).

## Ownership

Owner: Aurora Labs
Change authority: Architecture review required for template changes.

## Change Rules

- Template changes apply to new specifications only unless explicitly back-applied.
- Template version must be referenced in each module specification.

---

## Template

Copy everything below this line into the new module specification file.

---

```markdown
---
id: MOD-XXXX
title: [Module Name]
version: 0.1.0
status: Draft
owner: Aurora Labs
created: YYYY-MM-DD
updated: YYYY-MM-DD
depends_on: []
---

# [Module Name]

---

## Phase 1 — Vision

### Why This Module Exists

[Describe the problem this module solves and why Aurora needs it.]

### Success Criteria

[What does success look like for this module?]

---

## Phase 2 — Specification

### What This Module Does

[Describe the module's responsibilities.]

### What This Module Does NOT Do

[Explicitly state out-of-scope behaviour.]

### Inputs

[What does this module receive?]

### Outputs

[What does this module produce?]

### Invariants

[Rules that must always be true while this module operates.]

---

## Phase 3 — Architecture

### How This Module Works

[Internal structure, components, state machines, algorithms.]

### Layer

[Which architecture layer does this module belong to? Reference ARCH-0001.]

### Dependencies

[Which other modules does this module depend on? List MOD IDs.]

### Internal Components

[List and describe internal components. Do not expose them as public API.]

---

## Phase 4 — Data Model

### Data Owned by This Module

[List DATA- IDs. Each data model must have a separate document in 05-Data/.]

### Data Consumed from Other Modules

[List DATA- IDs and the source module.]

---

## Phase 5 — Public API

### Exposed Interfaces

[List API- IDs. Each API must have a separate document in 04-Interfaces/.]

### Events Emitted

[List events this module emits.]

### Events Consumed

[List events this module listens to.]

---

## Phase 6 — Tests

### Test Specifications

[List TEST- IDs. Each test spec must have a separate document in 09-Tests/.]

### Acceptance Criteria

[What must pass before this module is considered complete?]

---

## Phase 7 — AI Tasks

### Implementation Tasks

[List TASK- IDs. Each task must have a document in 08-Tasks/.]

### Task Sequence

[In what order must tasks be executed?]

---

## Phase 8 — Review

### Review Status

Status: [Draft | In Review | Approved | Rejected]

### Reviewer

[Name or role of reviewer]

### Review Notes

[Outstanding questions or required changes]

### Approval Date

[YYYY-MM-DD or blank if not yet approved]
```

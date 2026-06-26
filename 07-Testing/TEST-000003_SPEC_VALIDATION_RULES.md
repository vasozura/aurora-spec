# Specification Validation Rules

Document ID: TEST-000003  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 07-Testing/TEST-000003_SPEC_VALIDATION_RULES.md  
Document Type: Validation Rules Specification  
Depends On: TEST-000001_AURORA_TEST_STRATEGY.md, TEST-000002_DOCUMENT_REVIEW_CHECKLIST.md  

---

## 1. Purpose

This document defines validation rules for Aurora specification documents.

The goal is to detect incomplete, contradictory or implementation-dangerous specifications before code begins.

These rules may be applied manually first and automated later.

---

## 2. Scope

These rules apply to:

- Governance specifications
- Architecture specifications
- AFL specifications
- Module specifications
- Interface specifications
- Data contract specifications
- Test specifications
- AI implementation task files

---

## 3. Required Metadata Rules

A specification is invalid if it lacks:

- Document ID
- Version
- Status
- Owner
- Repository
- Path
- Document Type
- Dependencies
- Change History

A task file is invalid if it lacks:

- Task ID
- Version
- Status
- Priority
- Target Repository
- Target Files
- Depends On
- Required Input

---

## 4. Required Section Rules

Most specifications must include:

- Purpose
- Authority
- Scope
- Non-Scope
- Definitions where needed
- Responsibilities or rules
- Error expectations where behavior is described
- Security expectations
- Offline-first expectations
- Testing requirements
- Implementation readiness
- Acceptance criteria
- Change history

If a section is intentionally omitted, the reason must be clear.

---

## 5. Scope Consistency Rules

A specification is invalid if:

- Scope authorizes work that non-scope forbids.
- Scope references files outside the stated target area without explanation.
- Scope includes implementation while readiness is Not Ready.
- Scope expands module responsibility beyond architecture.
- Scope gives one module ownership over another module's data.

---

## 6. Dependency Rules

A specification is invalid if:

- It depends on missing prerequisite documents.
- It contradicts a higher-authority document.
- It creates circular dependency without review.
- It references future documents as if they already authorize implementation.
- It relies on provider-specific behavior inside core architecture.

---

## 7. AFL Validation Rules

AFL specifications are invalid if they:

- Treat prompt text as source truth.
- Place provider-specific syntax in AFL core.
- Collapse Scene or Shot meaning into generic prompt words.
- Remove offline-first expectations.
- Allow plugins to mutate AFL core directly.
- Fail to state implementation readiness.
- Fail to protect user creative meaning.

---

## 8. Module Validation Rules

Module specifications are invalid if they:

- Do not define ownership.
- Do not define non-scope.
- Modify other modules directly.
- Depend on GUI implementation.
- Depend on provider-specific integrations.
- Skip public interface deferral.
- Mark implementation ready without data, API and test specifications.

---

## 9. Interface Validation Rules

Interface specifications are invalid if they:

- Allow queries to mutate state.
- Use events as commands.
- Allow commands to mutate unrelated module data directly.
- Hide online provider calls.
- Omit error behavior.
- Omit security boundaries.
- Omit offline-first behavior.

---

## 10. Data Contract Validation Rules

Data contract specifications are invalid if they:

- Do not define ownership.
- Do not define stable identity expectations.
- Treat export artifacts as source meaning.
- Allow provider outputs to become required for opening core project data.
- Omit versioning expectations.
- Omit compatibility behavior.
- Omit security expectations.

---

## 11. AI Task Validation Rules

AI task files are invalid if they:

- Do not define target files.
- Do not define allowed scope.
- Do not define forbidden actions.
- Do not define preconditions.
- Do not define validation steps.
- Do not define expected report.
- Allow continuation into the next task.
- Ask for broad implementation without file boundaries.
- Permit guessing missing requirements.

---

## 12. Implementation Readiness Rules

A document marked `Not Ready` must not authorize implementation.

A document may be marked `Ready for Implementation` only if it references:

- Data contracts or schema
- Public interfaces
- Test requirements
- Implementation task
- Review approval

If readiness and content disagree, the document is invalid.

---

## 13. Error Severity

Validation findings may be classified as:

| Severity | Meaning |
|---|---|
| Info | Does not block use. |
| Warning | Needs attention but may not block use. |
| Error | Blocks implementation. |
| Critical | Violates governance, ownership or safety boundaries. |

Critical findings must be resolved before proceeding.

---

## 14. Validation Report Template

```text
Validation Report:
Document:
Version:
Date:

Status:
Passed / Failed / Blocked

Findings:
- Severity:
  Rule:
  Location:
  Description:
  Required Fix:

Implementation Allowed:
Yes / No
```

---

## 15. Future Automation

Future automation may validate:

- Required metadata
- Required sections
- Target path consistency
- Duplicate IDs
- Missing dependencies
- Implementation readiness
- Forbidden phrase patterns
- Provider-specific syntax leakage
- Task file scope violations

Automation must not replace human review for creative or architectural judgment.

---

## 16. Acceptance Criteria

This document is acceptable when:

1. Required metadata rules are defined.
2. Required section rules are defined.
3. Scope consistency rules are defined.
4. Dependency rules are defined.
5. AFL validation rules are defined.
6. Module validation rules are defined.
7. Interface validation rules are defined.
8. Data contract validation rules are defined.
9. AI task validation rules are defined.
10. Implementation readiness rules are defined.
11. Error severity is defined.
12. Validation report template is included.
13. Future automation boundaries are stated.

---

## 17. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This document defines validation rules only.

Executable validation tooling requires a later implementation task.

---

## 18. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

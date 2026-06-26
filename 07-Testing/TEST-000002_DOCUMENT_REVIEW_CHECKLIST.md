# Document Review Checklist

Document ID: TEST-000002  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 07-Testing/TEST-000002_DOCUMENT_REVIEW_CHECKLIST.md  
Document Type: Review Checklist  
Depends On: TEST-000001_AURORA_TEST_STRATEGY.md, 00-Governance/REVIEW_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md  

---

## 1. Purpose

This document defines a repeatable checklist for reviewing Aurora specification documents before they are accepted.

The checklist exists to prevent vague documents from becoming implementation authority.

A document that fails review should not be used to generate code.

---

## 2. Scope

This checklist applies to:

- Governance documents
- Architecture documents
- Product documents
- AFL specifications
- Module specifications
- Interface specifications
- Data contract specifications
- Test specifications
- AI implementation task files

---

## 3. Metadata Checklist

A document must include:

- Document ID or Task ID
- Version
- Status
- Owner
- Repository
- Path or Target File
- Document Type
- Dependencies or Required Input
- Change History

If metadata is missing, the document is incomplete.

---

## 4. Authority Checklist

A document must state:

- Which documents it is subordinate to
- What happens if conflicts exist
- Whether it authorizes implementation
- Whether it requires future specifications

If authority is unclear, implementation must not start.

---

## 5. Scope Checklist

A document must define:

- What it covers
- What it does not cover
- Which files or modules it affects
- Which concepts it owns
- Which concepts it references but does not own

Scope must be narrow enough to review.

---

## 6. Non-Scope Checklist

A document must explicitly reject work that belongs elsewhere.

Non-scope should identify:

- Code not authorized
- Schema not authorized
- GUI not authorized
- Provider integration not authorized
- Plugin work not authorized
- Tests not authorized when not in scope
- Data migrations not authorized when not in scope

If non-scope is missing, AI agents may overreach.

---

## 7. Ownership Checklist

A document must clarify:

- Which module or concept owns the subject
- Which other modules are referenced
- Whether cross-module mutation is allowed
- Whether data ownership is final or conceptual
- Whether provider-specific behavior is excluded

Ownership ambiguity blocks implementation.

---

## 8. Provider Independence Checklist

A document must not place provider-specific syntax inside core AFL, module or data contracts unless explicitly approved.

Check for hidden dependency on:

- WAN
- Veo
- Kling
- Runway
- OpenAI
- Local model-specific syntax
- Provider parameter names
- Provider prompt hacks

Provider-specific behavior belongs in export/plugin layers.

---

## 9. Offline-First Checklist

A document must state whether the described behavior works offline.

Core project, AFL, module, interface and data behavior should be offline-first.

Online operations must be explicit.

If online dependency is hidden, the document fails review.

---

## 10. Security Checklist

A document must consider:

- User creative data
- Project privacy
- Reference assets
- Provider-bound data
- Plugin permissions
- Minimum necessary data sharing
- External service boundaries

If external data movement is possible but not addressed, the document fails review.

---

## 11. Testability Checklist

A document must be testable.

Check whether the document has:

- Clear acceptance criteria
- Validation expectations
- Error expectations
- Ownership boundaries
- Observable behavior
- Explicit implementation readiness

Untestable requirements must be rewritten.

---

## 12. AI Task Checklist

For AI implementation task files, verify:

- Active task ID is clear
- Target files are explicit
- Allowed files are explicit
- Forbidden actions are explicit
- Preconditions are explicit
- Required action is explicit
- Validation is explicit
- Expected report is explicit
- Stop condition is explicit
- No continuation into next task is allowed

AI task files must not rely on vague instructions.

---

## 13. Implementation Readiness Checklist

Every specification must state one of:

```text
Not Ready
Ready for Design
Ready for Implementation
Deprecated
```

If readiness is `Ready for Implementation`, the document must reference:

- Data specification
- Interface specification
- Test specification
- Implementation task
- Review approval

Most current foundation documents should be `Not Ready`.

---

## 14. Review Outcome

Review result must be one of:

| Result | Meaning |
|---|---|
| Accepted | Document is usable for its stated purpose. |
| Accepted With Notes | Document is usable but requires follow-up. |
| Needs Revision | Document must be corrected before use. |
| Rejected | Document conflicts with governance or architecture. |
| Blocked | Required input is missing. |

---

## 15. Reviewer Notes Template

```text
Review Result:
Reviewer:
Date:
Document:
Version:

Passed Checks:
- ...

Failed Checks:
- ...

Required Changes:
- ...

Risk Notes:
- ...

Implementation Readiness Confirmed:
Yes / No

Approved For Next Task:
Yes / No
```

---

## 16. Acceptance Criteria

This checklist is acceptable when:

1. Metadata review is defined.
2. Authority review is defined.
3. Scope review is defined.
4. Non-scope review is defined.
5. Ownership review is defined.
6. Provider independence review is defined.
7. Offline-first review is defined.
8. Security review is defined.
9. Testability review is defined.
10. AI task review is defined.
11. Implementation readiness review is defined.
12. Review outcomes are defined.
13. Reviewer notes template is included.

---

## 17. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This checklist is a manual review instrument.

Automation may be introduced later.

---

## 18. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

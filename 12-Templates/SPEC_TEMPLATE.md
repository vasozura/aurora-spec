# Aurora Specification Template

Document ID: TEMPLATE-000004  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 12-Templates/SPEC_TEMPLATE.md  
Document Type: Specification Template  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 02-Architecture/ARCHITECTURE.md  

---

## 1. Purpose

This template defines the standard structure for Aurora specification documents.

A specification document defines product behavior, module responsibility, interface behavior, data ownership, workflow rules or system requirements before implementation begins.

Specifications are the primary source of truth for implementation.

AI implementation agents must follow approved specifications and must not invent missing behavior.

---

## 2. When To Use This Template

Use this template for:

- Product specifications
- Module specifications
- Interface specifications
- Data specifications
- AI behavior specifications
- SDK specifications
- Workflow specifications
- Testing specifications when a more specific test template is not available
- Any controlled document that defines required behavior

Do not use this template for:

- ADRs
- RFCs
- Simple implementation tasks
- Informal notes
- README files
- Scratch documents

---

## 3. File Naming Rule

Specification files must use a clear ID-based filename.

Recommended patterns:

```text
MOD-000001_PROJECT_MANAGER_SPEC.md
API-000001_PROJECT_API_SPEC.md
DATA-000001_PROJECT_DATA_MODEL_SPEC.md
AI-000001_AI_AGENT_BEHAVIOR_SPEC.md
SDK-000001_PLUGIN_SDK_SPEC.md
AFL-000001_AURORA_FILM_LANGUAGE_CORE_SPEC.md
```

Specification files must be stored in the correct repository folder:

```text
01-Product/
02-Architecture/
03-Modules/
04-Interfaces/
05-Data/
06-AI/
07-SDK/
09-Tests/
```

The selected folder must match the document type and responsibility.

---

## 4. Specification Status Values

Allowed specification statuses:

- `Draft`
- `Review`
- `Approved`
- `Deprecated`
- `Superseded`
- `Archived`

Meaning:

`Draft` means the specification is being written.

`Review` means the specification is ready for review.

`Approved` means the specification may be used for implementation.

`Deprecated` means the specification should not be used for new implementation.

`Superseded` means another specification replaced this document.

`Archived` means the document is retained only for historical reference.

Implementation should not begin from a `Draft` specification unless the task explicitly allows it.

---

## 5. Required Specification Template

```markdown
# <Specification Title>

Document ID: <DOC-ID>  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: <path/to/specification.md>  
Document Type: <Product Specification | Module Specification | Interface Specification | Data Specification | AI Specification | SDK Specification | Workflow Specification | Test Specification>  
Depends On: <related document IDs or paths>  
Supersedes: <DOC-ID or None>  
Superseded By: <DOC-ID or None>  

---

## 1. Purpose

<Explain why this specification exists.>

The purpose must be clear enough that a contributor or AI implementation agent understands what area of Aurora this document controls.

---

## 2. Authority

This specification is subordinate to:

- 00-Governance/AURORA_CONSTITUTION.md
- 00-Governance/AURORA_ENGINEERING_STANDARD.md
- 02-Architecture/ARCHITECTURE.md

If this specification conflicts with a higher-authority document, the higher-authority document takes precedence.

---

## 3. Scope

This specification defines:

- <in-scope item 1>
- <in-scope item 2>
- <in-scope item 3>

This specification applies to:

- <module, layer, workflow, interface, data area or product area>

---

## 4. Non-Scope

This specification does not define:

- <out-of-scope item 1>
- <out-of-scope item 2>
- <out-of-scope item 3>

Non-scope is mandatory.

Anything not explicitly in scope must not be implemented from this specification.

---

## 5. Definitions

| Term | Meaning |
|---|---|
| <Term> | <Definition> |

Definitions must be precise.

Do not use vague terms when the term affects implementation.

---

## 6. Users, Actors or System Participants

This specification involves the following actors:

| Actor | Description | Responsibility |
|---|---|---|
| <Actor> | <Description> | <Responsibility> |

Use this section only when actors are relevant.

If no actors are relevant, state:

\`\`\`text
No external actors are defined by this specification.
\`\`\`

---

## 7. Requirements

### 7.1 Functional Requirements

The system must:

1. <Functional requirement>
2. <Functional requirement>
3. <Functional requirement>

### 7.2 Non-Functional Requirements

The system must satisfy:

1. <Performance, reliability, security, offline, compatibility or usability requirement>
2. <Requirement>
3. <Requirement>

### 7.3 Negative Requirements

The system must not:

1. <Forbidden behavior>
2. <Forbidden behavior>
3. <Forbidden behavior>

Negative requirements are required when implementation agents might otherwise over-expand behavior.

---

## 8. Behavioral Rules

The following behavior is required:

1. <Behavioral rule>
2. <Behavioral rule>
3. <Behavioral rule>

Rules must be deterministic.

If behavior depends on a condition, define the condition explicitly.

---

## 9. Data Ownership

This specification owns the following data:

- <data item>

This specification reads the following data owned by other modules:

- <data item and owner>

This specification writes the following data owned by other modules:

- <data item and required interface>

If no data is owned, state:

\`\`\`text
This specification does not define data ownership.
\`\`\`

Data ownership must not be ambiguous.

---

## 10. Interfaces

This specification exposes the following public interfaces:

- <interface name or future API-ID>

This specification consumes the following public interfaces:

- <interface name or future API-ID>

If no public interface is defined, state:

\`\`\`text
This specification does not define a public interface.
\`\`\`

Public interfaces must not be changed silently after approval.

---

## 11. Events

This specification may emit the following events:

- <EventName>

This specification may consume the following events:

- <EventName>

If no events are involved, state:

\`\`\`text
This specification does not define events.
\`\`\`

Event schemas must be defined in interface or data specifications when implementation begins.

---

## 12. Workflow

Describe the expected workflow.

\`\`\`text
Step 1: <description>
Step 2: <description>
Step 3: <description>
\`\`\`

If this specification does not define a workflow, state:

\`\`\`text
This specification does not define a workflow.
\`\`\`

---

## 13. Error Handling

The system must handle the following errors:

| Error Condition | Required Behavior | User/System Message |
|---|---|---|
| <Condition> | <Behavior> | <Message or message rule> |

Errors must not be hidden.

Recoverable errors must be reported in a meaningful way.

---

## 14. Security Requirements

Security requirements:

- <security requirement>

Permission requirements:

- <permission requirement>

Data protection requirements:

- <data protection requirement>

If no specific security requirement is defined, state:

\`\`\`text
No additional security requirements are defined beyond the Aurora Constitution and Architecture.
\`\`\`

---

## 15. Offline-First Requirements

Offline behavior:

- <offline behavior>

Online behavior, if applicable:

- <online behavior>

If online capability is required, justify it explicitly.

Aurora must remain offline-first unless an approved exception exists.

---

## 16. Performance Requirements

Performance expectations:

- <performance expectation>

Responsiveness expectations:

- <responsiveness expectation>

If no specific performance requirement is defined, state:

\`\`\`text
No additional performance requirements are defined beyond the Aurora Constitution and Architecture.
\`\`\`

---

## 17. Compatibility Requirements

Compatibility requirements:

- Project compatibility: <None | Required | Breaking>
- Public API compatibility: <None | Required | Breaking>
- Plugin compatibility: <None | Required | Breaking>
- Cross-platform compatibility: <Windows | Linux | Both | Not Applicable>

Breaking compatibility requires an ADR.

---

## 18. Dependencies

This specification depends on:

- <document ID or file path>

This specification is required by:

- <document ID or file path, if known>

Dependencies must be explicit.

Hidden dependencies are forbidden.

---

## 19. Testing Requirements

The following tests are required:

- Unit tests: <Required | Not Applicable>
- Integration tests: <Required | Not Applicable>
- Acceptance tests: <Required | Not Applicable>
- Regression tests: <Required | Not Applicable>

Test cases or future test specifications:

- <TEST-ID or future placeholder>

A feature is incomplete without applicable tests.

---

## 20. Acceptance Criteria

This specification is acceptable when:

1. Purpose is clear.
2. Scope is explicit.
3. Non-scope is explicit.
4. Requirements are deterministic.
5. Data ownership is defined.
6. Public interfaces are defined or explicitly excluded.
7. Events are defined or explicitly excluded.
8. Error handling is defined.
9. Security impact is addressed.
10. Offline-first behavior is addressed.
11. Performance impact is addressed.
12. Compatibility impact is addressed.
13. Testing requirements are defined.
14. The specification does not violate the Aurora Constitution.
15. The specification is consistent with AES and Architecture.

---

## 21. Implementation Readiness

Implementation readiness:

\`\`\`text
<Not Ready | Ready After Review | Ready>
\`\`\`

Reason:

<Explain why implementation may or may not begin.>

Required follow-up tasks:

- <TASK-ID or future placeholder>

---

## 22. Review Checklist

Before approval, verify:

1. The document ID is unique.
2. The path is correct.
3. The document type is correct.
4. Dependencies are listed.
5. Scope is clear.
6. Non-scope prevents expansion.
7. Requirements are testable.
8. Interfaces are explicit.
9. Data ownership is explicit.
10. Security requirements are addressed.
11. Offline-first requirements are addressed.
12. Testing requirements are addressed.
13. No implementation details are invented unnecessarily.
14. AI agents can execute future tasks from this specification without guessing.

---

## 23. Change Control

Changes to this specification must update:

- Version
- Change history
- Affected documents, if any
- Related tasks, if any

Breaking changes require an ADR.

---

## 24. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | <YYYY-MM-DD> | Initial draft | Aurora Labs |

---

## 25. Summary

<Briefly summarize what this specification controls and why it matters.>
```

---

## 6. Specification Quality Rules

A good Aurora specification must be:

- Deterministic
- Scoped
- Testable
- Reviewable
- Linked to dependencies
- Clear about non-scope
- Clear about data ownership
- Clear about public interfaces
- Clear about offline behavior
- Clear about compatibility impact

A specification must not:

- Hide assumptions
- Mix unrelated modules
- Invent implementation details unnecessarily
- Replace an ADR when an ADR is required
- Replace a task when a task is required
- Allow AI agents to guess
- Allow uncontrolled continuation

---

## 7. Specification Lifecycle

A typical specification lifecycle is:

```text
Draft
  ↓
Review
  ↓
Approved
  ↓
AI Tasks
  ↓
Implementation
  ↓
Tests
  ↓
Review
```

Implementation should begin only after approval unless explicitly allowed.

---

## 8. AI Implementation Rule

AI implementation agents must treat approved specifications as contracts.

If a specification is incomplete, the AI agent must stop and report the missing requirement.

The AI agent must not:

- Invent missing behavior
- Add hidden features
- Rewrite scope
- Create architecture
- Change public APIs
- Modify unrelated files
- Continue beyond the assigned task

---

## 9. Summary

This template exists to make Aurora specifications consistent, executable and reviewable.

Aurora must be built from structured specifications, not from scattered prompts.

The specification is the product definition.

Code follows the specification.

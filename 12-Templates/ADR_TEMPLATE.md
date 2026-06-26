# Aurora ADR Template

Document ID: TEMPLATE-000002  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 12-Templates/ADR_TEMPLATE.md  
Document Type: ADR Template  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 02-Architecture/ARCHITECTURE.md  

---

## 1. Purpose

This template defines the standard structure for Aurora Architecture Decision Records.

An Architecture Decision Record, abbreviated as ADR, documents a significant architectural decision that affects Aurora Studio.

ADR documents exist to prevent undocumented architecture drift.

Every significant architectural decision must be traceable, reviewable and reversible where technically possible.

---

## 2. When To Use An ADR

Use an ADR when a decision:

- Changes architecture
- Changes dependency direction
- Changes public APIs
- Adds a major technology dependency
- Changes storage model
- Changes plugin boundaries
- Changes security boundaries
- Changes data ownership
- Changes module responsibility
- Creates a long-term technical constraint
- Introduces a cross-platform limitation
- Creates a breaking change
- Supersedes a previous ADR

Do not use an ADR for small wording changes, formatting corrections or minor non-architectural edits.

---

## 3. File Naming Rule

ADR files must use this pattern:

```text
ADR-000000_SHORT_DECISION_NAME.md
```

Example:

```text
ADR-000001_USE_PYSIDE6_FOR_DESKTOP_UI.md
```

ADR files must be stored in:

```text
10-ADR/
```

ADR IDs must never be reused.

---

## 4. ADR Status Values

Allowed ADR statuses:

- `Proposed`
- `Accepted`
- `Rejected`
- `Superseded`
- `Deprecated`

Meaning:

`Proposed` means the decision is under review.

`Accepted` means the decision is approved and authoritative.

`Rejected` means the decision was considered but not adopted.

`Superseded` means another ADR replaced this decision.

`Deprecated` means the decision should not be used for new work but may still explain legacy behavior.

---

## 5. Required ADR Template

```markdown
# ADR-000000: <Decision Title>

Document ID: ADR-000000  
Version: 0.1.0  
Status: Proposed  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 10-ADR/ADR-000000_<SHORT_DECISION_NAME>.md  
Document Type: Architecture Decision Record  
Depends On: <related Constitution, AES, Architecture, Module, API, DATA or TASK documents>  
Supersedes: <ADR-ID or None>  
Superseded By: <ADR-ID or None>  

---

## 1. Decision Summary

<Write a short summary of the decision in one to three paragraphs.>

The summary must clearly state what is being decided.

---

## 2. Status

Current status:

\`\`\`text
Proposed
\`\`\`

Allowed status values:

- Proposed
- Accepted
- Rejected
- Superseded
- Deprecated

---

## 3. Context

<Explain the problem, constraint, requirement or opportunity that requires an architectural decision.>

Include:

- Why the decision is needed
- What problem it solves
- What constraints apply
- What documents or modules are affected
- What happens if no decision is made

---

## 4. Decision

<Describe the selected decision clearly.>

The decision must be specific enough that implementation agents can follow it without guessing.

---

## 5. Scope

This ADR applies to:

- <module, layer, interface or system area>

This ADR does not apply to:

- <excluded area>

---

## 6. Options Considered

### Option A: <Option Name>

Description:

<Describe the option.>

Advantages:

- <advantage>

Disadvantages:

- <disadvantage>

Reason for rejection or acceptance:

<Explain.>

---

### Option B: <Option Name>

Description:

<Describe the option.>

Advantages:

- <advantage>

Disadvantages:

- <disadvantage>

Reason for rejection or acceptance:

<Explain.>

---

## 7. Consequences

Positive consequences:

- <positive consequence>

Negative consequences:

- <negative consequence>

Neutral consequences:

- <neutral consequence>

---

## 8. Compatibility Impact

This decision affects compatibility as follows:

- Public API impact: <None | Minor | Breaking>
- Data format impact: <None | Minor | Breaking>
- Plugin compatibility impact: <None | Minor | Breaking>
- Project compatibility impact: <None | Minor | Breaking>
- Cross-platform impact: <None | Minor | Significant>

If any impact is breaking, migration requirements must be defined.

---

## 9. Security Impact

Security impact:

\`\`\`text
<None | Low | Medium | High>
\`\`\`

Explanation:

<Explain security implications, permissions, isolation requirements or risk boundaries.>

---

## 10. Performance Impact

Performance impact:

\`\`\`text
<None | Low | Medium | High>
\`\`\`

Explanation:

<Explain expected effect on startup time, runtime responsiveness, memory usage, storage, export speed or plugin execution.>

---

## 11. Offline-First Impact

Offline-first impact:

\`\`\`text
<None | Compatible | Requires Online Capability | Not Applicable>
\`\`\`

Explanation:

<Explain whether the decision affects offline operation.>

Aurora must remain offline-first unless the exception is explicitly justified.

---

## 12. Affected Documents

This ADR affects:

- <document path or ID>

Documents requiring update:

- <document path or ID>

---

## 13. Affected Modules

This ADR affects:

- <MOD-ID or module name>

Modules requiring update:

- <MOD-ID or module name>

---

## 14. Implementation Requirements

Implementation must:

- <requirement>

Implementation must not:

- <forbidden action>

Implementation tasks required:

- <TASK-ID or future task placeholder>

---

## 15. Testing Requirements

Testing must verify:

- <test requirement>

Required test specifications:

- <TEST-ID or future test placeholder>

---

## 16. Migration Requirements

Migration is required:

\`\`\`text
<Yes | No>
\`\`\`

If yes, define:

- Data migration steps
- API migration steps
- Plugin migration steps
- User project migration steps
- Rollback strategy

---

## 17. Review Checklist

Before this ADR can be accepted, verify:

1. The decision is clearly stated.
2. The context is complete.
3. Options were considered.
4. Consequences are documented.
5. Compatibility impact is documented.
6. Security impact is documented.
7. Performance impact is documented.
8. Offline-first impact is documented.
9. Affected documents are listed.
10. Affected modules are listed.
11. Implementation requirements are clear.
12. Testing requirements are clear.
13. The decision does not violate the Aurora Constitution.
14. The decision is consistent with the Aurora Engineering Standard.
15. The decision is consistent with the current Architecture document or explicitly updates it.

---

## 18. Approval

Reviewer:

\`\`\`text
<Reviewer name or role>
\`\`\`

Decision:

\`\`\`text
<Accepted | Rejected | Needs Revision>
\`\`\`

Review date:

\`\`\`text
<YYYY-MM-DD>
\`\`\`

Review notes:

<Write review notes.>

---

## 19. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | <YYYY-MM-DD> | Initial draft | Aurora Labs |
```

---

## 6. ADR Quality Rules

An ADR must be:

- Specific
- Short enough to review
- Complete enough to implement
- Linked to affected documents
- Explicit about consequences
- Explicit about compatibility
- Explicit about migration when needed

An ADR must not:

- Hide tradeoffs
- Approve vague architecture
- Combine unrelated decisions
- Modify implementation directly
- Replace module specifications
- Replace task specifications
- Ignore Constitution conflicts

---

## 7. ADR Review Rule

An ADR is not authoritative until its status is `Accepted`.

Implementation tasks may reference a `Proposed` ADR only if the task explicitly states that implementation is exploratory or provisional.

Production implementation must use accepted architectural decisions.

---

## 8. Superseding Rule

If an ADR replaces a previous ADR:

1. The new ADR must list the previous ADR under `Supersedes`.
2. The previous ADR must be updated to `Superseded`.
3. The previous ADR must list the new ADR under `Superseded By`.
4. Affected specifications must be reviewed.

No ADR may be silently overwritten.

---

## 9. Summary

This template ensures that Aurora architectural decisions remain explicit and reviewable.

Architecture must not live only in chat history, code comments or AI memory.

If a decision shapes Aurora for the future, it belongs in an ADR.

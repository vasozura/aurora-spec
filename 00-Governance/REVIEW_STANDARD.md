# Aurora Review Standard

Document ID: GOV-000003  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 00-Governance/REVIEW_STANDARD.md  
Document Type: Review Standard  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 02-Architecture/ARCHITECTURE.md, 12-Templates/TASK_TEMPLATE.md, 12-Templates/ADR_TEMPLATE.md, 12-Templates/RFC_TEMPLATE.md, 12-Templates/SPEC_TEMPLATE.md  

---

## 1. Purpose

This document defines the review standard for Aurora specifications, tasks, templates, ADRs, RFCs and AI-generated implementation outputs.

The purpose of review is to prevent uncontrolled scope expansion, hidden assumptions, undocumented architecture, weak task definitions, inconsistent IDs, invalid dependencies and implementation drift.

Aurora review is not a formality.

Review is a required engineering control.

---

## 2. Authority

This Review Standard is subordinate to:

- 00-Governance/AURORA_CONSTITUTION.md
- 00-Governance/AURORA_ENGINEERING_STANDARD.md
- 02-Architecture/ARCHITECTURE.md

If this document conflicts with the Constitution, the Constitution takes precedence.

If this document conflicts with AES, AES takes precedence unless this document is updated through approved review.

---

## 3. Review Principle

Every controlled change must be reviewable.

If a change cannot be reviewed clearly, it is not ready.

Review must verify:

- Correct scope
- Correct path
- Correct ID
- Correct dependencies
- Consistency with higher-authority documents
- Absence of uncontrolled implementation
- Absence of hidden assumptions
- AI executability
- Acceptance criteria
- Commit readiness

---

## 4. Review Targets

The Review Standard applies to:

- Governance documents
- Product specifications
- Architecture documents
- Module specifications
- Interface specifications
- Data specifications
- AI behavior specifications
- SDK specifications
- Task documents
- Test specifications
- ADRs
- RFCs
- Templates
- AI-generated implementation reports
- Future implementation code

During Sprint-0, this standard applies only to documentation and specification work.

---

## 5. Review Decision Values

Allowed review decisions:

- `Approved`
- `Approved With Minor Corrections`
- `Needs Revision`
- `Rejected`
- `Blocked`
- `Superseded`

Meaning:

`Approved` means the document or change is ready for use or commit.

`Approved With Minor Corrections` means the change is acceptable after small non-structural fixes.

`Needs Revision` means the change is not ready and must be corrected.

`Rejected` means the change should not proceed.

`Blocked` means review cannot continue because required information or dependencies are missing.

`Superseded` means another document or change replaced this one.

---

## 6. Review Severity Levels

Issues found during review must be classified as:

- `Critical`
- `Major`
- `Minor`
- `Editorial`

Meaning:

`Critical` means the change violates Constitution, AES, architecture, scope, dependency rules, public API stability, security boundaries or implementation readiness.

`Major` means the change is incomplete, ambiguous, missing required sections or likely to cause AI implementation errors.

`Minor` means the change is mostly correct but requires clarification, formatting correction or small consistency fixes.

`Editorial` means spelling, grammar, formatting or wording cleanup that does not affect meaning.

A document with Critical issues must not be approved.

A document with Major issues should not be approved unless explicitly accepted with documented risk.

---

## 7. Universal Review Checklist

Every reviewed item must pass the following checks:

1. The file is in the correct path.
2. The document or task ID is present.
3. The ID format is correct.
4. The version is present.
5. The status is present.
6. The owner is present.
7. The document type is present.
8. Dependencies are listed.
9. Scope is explicit.
10. Non-scope is explicit where applicable.
11. Acceptance criteria are present.
12. The document does not conflict with the Constitution.
13. The document does not conflict with AES.
14. The document does not conflict with Architecture.
15. The document does not introduce hidden dependencies.
16. The document does not silently change public APIs.
17. The document does not silently change module responsibility.
18. The document does not include uncontrolled continuation.
19. The document is clear enough for an AI agent to execute without guessing.
20. The document is ready for a small, traceable commit.

---

## 8. Task Review Checklist

A task is acceptable when:

1. It has a unique Task ID.
2. It has a clear objective.
3. It has strict scope.
4. It lists target files.
5. It lists required input files.
6. It defines preconditions.
7. It defines required action.
8. It defines forbidden actions.
9. It defines validation steps.
10. It defines expected report format.
11. It does not allow continuation to the next task.
12. It does not combine unrelated work.
13. It does not allow the AI to invent architecture.
14. It does not allow the AI to modify files outside the allowed scope.
15. It is small enough to review and revert.

A task must be rejected if it asks the AI agent to:

- Build the whole product
- Continue until done
- Invent missing requirements
- Decide architecture during implementation
- Modify public APIs without ADR
- Add dependencies without approval
- Change unrelated files

---

## 9. Specification Review Checklist

A specification is acceptable when:

1. Purpose is clear.
2. Authority is defined.
3. Scope is explicit.
4. Non-scope is explicit.
5. Definitions are precise.
6. Functional requirements are deterministic.
7. Non-functional requirements are stated.
8. Negative requirements are stated where needed.
9. Behavioral rules are testable.
10. Data ownership is defined or explicitly excluded.
11. Public interfaces are defined or explicitly excluded.
12. Events are defined or explicitly excluded.
13. Error handling is defined.
14. Security requirements are addressed.
15. Offline-first requirements are addressed.
16. Performance requirements are addressed.
17. Compatibility impact is addressed.
18. Dependencies are explicit.
19. Testing requirements are defined.
20. Implementation readiness is stated.

A specification must not be approved if it requires implementation agents to guess.

---

## 10. ADR Review Checklist

An ADR is acceptable when:

1. The decision summary is clear.
2. Status is valid.
3. Context is complete.
4. The decision is specific.
5. Scope and exclusions are clear.
6. Options were considered.
7. Consequences are documented.
8. Compatibility impact is documented.
9. Security impact is documented.
10. Performance impact is documented.
11. Offline-first impact is documented.
12. Affected documents are listed.
13. Affected modules are listed.
14. Implementation requirements are clear.
15. Testing requirements are clear.
16. Migration requirements are defined if needed.
17. The ADR does not violate the Constitution.
18. The ADR is consistent with AES.
19. The ADR is consistent with Architecture or explicitly updates it.
20. The approval section is complete.

An ADR must not be accepted if it hides tradeoffs or approves vague architecture.

---

## 11. RFC Review Checklist

An RFC is acceptable when:

1. Proposal summary is clear.
2. Motivation is documented.
3. Background is sufficient.
4. Proposal is specific enough to review.
5. Scope is explicit.
6. Non-goals are explicit.
7. User impact is documented.
8. Product impact is documented.
9. Architecture impact is documented.
10. Data impact is documented.
11. API or SDK impact is documented.
12. Security impact is documented.
13. Offline-first impact is documented.
14. Alternatives are considered.
15. Open questions are listed.
16. Required follow-up documents are identified.
17. Acceptance criteria are present.
18. The RFC does not imply automatic implementation approval.

An RFC must not be approved as a substitute for an ADR or specification when those are required.

---

## 12. Template Review Checklist

A template is acceptable when:

1. It has a clear purpose.
2. It defines when to use the template.
3. It defines file naming rules.
4. It defines required metadata.
5. It contains all required sections.
6. It explains section purpose where needed.
7. It prevents uncontrolled AI behavior.
8. It is consistent with AES.
9. It is reusable.
10. It does not include project-specific accidental content.

Templates must be stable because future documents depend on them.

---

## 13. AI Output Review Checklist

An AI-generated result is acceptable when:

1. The AI executed only the assigned task.
2. The AI verified preconditions.
3. The AI changed only allowed files.
4. The AI did not create unrequested files.
5. The AI did not add implementation code to documentation tasks.
6. The AI did not invent architecture.
7. The AI did not add dependencies.
8. The AI did not continue to the next task.
9. The AI produced the expected report.
10. The reported files match the actual changed files.
11. No hidden scope expansion occurred.
12. No required content was omitted.

If the AI output violates strict scope, it must be rejected or reverted.

---

## 14. Repository Review Checklist

Before commit, verify:

1. The repository structure remains valid.
2. Files are stored in the correct folders.
3. File names match ID and purpose.
4. Markdown files are readable.
5. No temporary files are included.
6. No editor backup files are included.
7. No generated junk files are included.
8. No binary files are added without reason.
9. No unrelated files are modified.
10. The commit contains exactly the intended task output.

Sprint-0 commits should be small and documentation-only.

---

## 15. Dependency Review

Every dependency must be explicit.

Review must check:

1. Required input files exist.
2. Referenced documents exist or are clearly future placeholders.
3. Dependency order is logical.
4. A lower-authority document does not override a higher-authority document.
5. A task does not depend on a document that has not been created unless the task explicitly stops on absence.
6. A document does not create circular authority.

Hidden dependencies are not allowed.

---

## 16. Scope Review

Review must confirm that the change does not exceed its stated scope.

Scope violations include:

- Creating extra files
- Modifying unrelated files
- Adding unrequested sections
- Creating architecture inside implementation tasks
- Adding implementation code during documentation-only tasks
- Adding features not requested
- Renaming IDs
- Moving files without approval
- Changing dependency direction
- Changing public APIs without ADR

Scope violations must be treated as Major or Critical issues.

---

## 17. AI Executability Review

A task or specification is AI-executable when:

1. The AI can identify the target file.
2. The AI can identify allowed files.
3. The AI can identify forbidden actions.
4. The AI can verify preconditions.
5. The AI can perform validation.
6. The AI can produce the expected report.
7. The AI does not need to guess missing behavior.
8. The AI does not need to make architectural decisions.

If an AI agent must guess, the document is not ready.

---

## 18. Commit Readiness

A change is ready for commit when:

1. Review decision is Approved or Approved With Minor Corrections.
2. No Critical issue remains.
3. No unresolved Major issue remains unless explicitly accepted.
4. All required files exist.
5. No unauthorized files changed.
6. Validation was performed.
7. The commit message can reference one task ID.
8. The change is reversible.

Recommended commit message format:

```text
TASK-000009: create review standard
```

---

## 19. Review Report Format

A review report must use this structure:

```markdown
# Review Report

Reviewed Item: <file path or task ID>  
Review Decision: <Approved | Approved With Minor Corrections | Needs Revision | Rejected | Blocked | Superseded>  
Reviewer: <name or role>  
Date: <YYYY-MM-DD>  

## Summary

<Short factual summary.>

## Checks Passed

- <check>

## Issues Found

| Severity | Issue | Required Action |
|---|---|---|
| <Critical/Major/Minor/Editorial> | <Issue> | <Action> |

## Scope Compliance

<Compliant | Not Compliant>

## Commit Readiness

<Ready | Not Ready>

## Notes

<Optional notes>
```

Review reports may be stored later if a formal review archive is created.

During Sprint-0, short review notes are acceptable when the task output is simple.

---

## 20. Rejection Rules

A change must be rejected when:

- It violates the Aurora Constitution.
- It violates AES without approved exception.
- It changes architecture without ADR.
- It creates uncontrolled implementation.
- It modifies files outside scope.
- It invents missing requirements.
- It hides compatibility impact.
- It introduces hidden dependencies.
- It cannot be reviewed.
- It cannot be reverted safely.

Rejection is not failure.

Rejection protects the project.

---

## 21. Blocked Review Rules

A review is blocked when:

- Required input files are missing.
- The task scope is unclear.
- The target file is unclear.
- Dependency documents conflict.
- Required review information is unavailable.
- The AI output report is missing or unreliable.

Blocked review means no approval decision can be made yet.

---

## 22. Sprint-0 Review Rules

During Sprint-0, review must verify:

1. No Aurora Studio code is created.
2. No Python packages are created.
3. No GUI files are created.
4. No database files are created.
5. No plugins are created.
6. Only specification repository files are created.
7. Governance and templates are internally consistent.
8. The system becomes more deterministic after each task.

Sprint-0 is successful when future implementation can be controlled by specification and task documents.

---

## 23. Summary

Aurora Review Standard exists to keep the project controlled.

No task, specification, ADR, RFC, template or AI-generated output should pass merely because it looks plausible.

A change is acceptable only when it is scoped, traceable, consistent, reviewable and ready for commit.

Review protects Aurora from accidental complexity.

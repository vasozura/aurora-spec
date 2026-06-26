# AI Agent Acceptance Checklist

Document ID: TEST-000005  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 07-Testing/TEST-000005_AI_AGENT_ACCEPTANCE_CHECKLIST.md  
Document Type: AI-Agent Review Checklist  
Depends On: 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, TEST-000001_AURORA_TEST_STRATEGY.md, TEST-000003_SPEC_VALIDATION_RULES.md  

---

## 1. Purpose

This document defines the acceptance checklist for work produced by AI agents such as Claude, Codex or similar implementation assistants.

The checklist exists because AI agents often overreach, continue beyond scope, create extra files, modify unrelated files or silently invent missing requirements.

Aurora requires controlled AI execution.

---

## 2. Scope

This checklist applies to:

- Documentation tasks
- Specification generation tasks
- API contract tasks
- Data contract tasks
- Test specification tasks
- Future implementation tasks
- Future refactor tasks

---

## 3. Pre-Execution Checklist

Before running an AI task, verify:

- Active Task ID is clear.
- The task file is the only instruction source for execution.
- Required input documents exist.
- Target files are explicit.
- Forbidden actions are explicit.
- Stop condition is explicit.
- The task does not ask for vague continuation.
- The task does not ask the AI to guess missing requirements.

If any item fails, do not run the task.

---

## 4. Scope Compliance Checklist

After execution, verify:

- Only allowed target files were created or modified.
- No unrelated files were changed.
- No hidden files were added.
- No package files were changed unless explicitly allowed.
- No dependencies were added unless explicitly allowed.
- No generated cache or build output was committed.
- No code was added in documentation-only tasks.
- No documentation was rewritten outside target scope.

---

## 5. Content Compliance Checklist

Verify the output:

- Matches requested document type.
- Contains required metadata.
- Contains required sections.
- Uses the specified target path.
- Preserves required terminology.
- Does not contradict governance.
- Does not contradict architecture.
- Does not contradict previous approved specs.
- Does not mark implementation ready without prerequisites.
- Does not introduce provider-specific syntax into core layers.

---

## 6. AI Overreach Checklist

Reject output if the AI agent:

- Continues into the next task.
- Creates implementation code when only specification was requested.
- Creates schemas when only conceptual contracts were requested.
- Adds provider-specific details without authorization.
- Rewrites prior approved documents without instruction.
- Invents missing folder structure beyond target files.
- Changes task IDs.
- Changes document IDs.
- Removes non-scope or forbidden actions.
- Marks incomplete specs as ready for implementation.

---

## 7. Code Task Checklist

For future code tasks, verify:

- Code changes match exact target files.
- Tests were added or updated if required.
- Validation commands were run.
- Errors are handled explicitly.
- Offline-first behavior is preserved.
- Module boundaries are respected.
- Queries do not mutate state.
- Commands validate inputs.
- Events are emitted after state changes.
- Provider access is routed through plugin/export boundaries.
- No secrets or private data are hardcoded.

---

## 8. Test Evidence Checklist

Acceptable evidence may include:

- Test command output
- Lint command output
- Type check output
- Manual validation report
- Changed file list
- Summary of checks performed
- Known limitations
- Confirmation that no forbidden files changed

If evidence is missing, the task should not be considered complete unless it is a documentation-only task with manual review.

---

## 9. Report Checklist

The AI agent's final report must include:

- Created or changed file paths
- Confirmation that required inputs existed
- Confirmation that no other files were changed
- Confirmation that forbidden actions were not performed
- Confirmation that validation was completed
- Any blocked or failed checks
- Stop statement indicating no continuation beyond active task

A report that hides uncertainty is unacceptable.

---

## 10. Rejection Reasons

Reject AI output if:

- It violates target scope.
- It modifies unrelated files.
- It creates code when code is forbidden.
- It creates provider-specific logic in core.
- It marks incomplete work as implementation-ready.
- It removes safety or ownership boundaries.
- It silently invents missing requirements.
- It fails required validation.
- It cannot explain what changed.
- It continues beyond the active task.

---

## 11. Acceptance Result Template

```text
AI Agent Review Result:
Task ID:
Reviewer:
Date:

Result:
Accepted / Accepted With Notes / Needs Revision / Rejected / Blocked

Changed Files:
- ...

Scope Compliance:
Pass / Fail

Forbidden Actions:
Pass / Fail

Validation:
Pass / Fail

Test Evidence:
- ...

Required Fixes:
- ...

Approved For Commit:
Yes / No

Approved For Next Task:
Yes / No
```

---

## 12. Acceptance Criteria

This document is acceptable when:

1. Pre-execution checklist is defined.
2. Scope compliance checklist is defined.
3. Content compliance checklist is defined.
4. AI overreach checklist is defined.
5. Code task checklist is defined.
6. Test evidence checklist is defined.
7. Report checklist is defined.
8. Rejection reasons are defined.
9. Acceptance result template is included.
10. Implementation readiness is explicitly marked Not Ready.

---

## 13. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This checklist defines review behavior only.

Automation may be introduced later.

---

## 14. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

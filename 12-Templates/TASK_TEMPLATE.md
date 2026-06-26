---
id: TEMPLATE-0002
title: Implementation Task Template
version: 0.1.0
status: Draft
owner: Aurora Labs
created: 2026-06-26
updated: 2026-06-26
depends_on: [GOV-0001, GOV-0002]
---

# Implementation Task Template

## Purpose

This template defines the required structure for all Aurora Studio implementation and specification tasks.
Every task issued to an AI agent or human contributor must follow this structure.

## Scope

All tasks written for `aurora-spec/08-Tasks/`.

## Non-Goals

- This template does not contain implementation guidance.
- This template does not define architecture.

## Ownership

Owner: Aurora Labs
Change authority: Architecture review required for template changes.

## Change Rules

- Tasks must not be modified after they are assigned to an agent.
- If a task requires change after assignment, close it and create a new task.

---

## Template

Copy everything below this line into the new task file.

---

```markdown
---
id: TASK-XXXXXX
title: [Task Title]
version: 0.1.0
status: [Ready | In Progress | Blocked | Complete | Cancelled]
sprint: [Sprint-N]
module: [MOD-XXXX or N/A]
repository: [aurora-spec | aurora-studio]
type: [Repository Initialization | Specification | Implementation | Review | Template]
priority: [Critical | High | Medium | Low]
blocked_by: []
created: YYYY-MM-DD
updated: YYYY-MM-DD
---

# TASK-XXXXXX — [Task Title]

## Objective

[One paragraph describing exactly what this task must accomplish.]

## AI Preamble

[Paste the full AI Implementation Protocol preamble from GOV-0002 here.]

## Inputs

[List all inputs the agent needs: files, documents, IDs, context.]

## Allowed Files

[Exhaustive list of files the agent may create or modify.]

## Forbidden Files

[Exhaustive list of files or patterns the agent must not touch.]

## Implementation Steps

1. [Step 1]
2. [Step 2]
3. [Step N]

## Acceptance Criteria

- [ ] [Criterion 1]
- [ ] [Criterion 2]
- [ ] [Criterion N]

## Validation Commands

```shell
# Commands that must succeed after implementation
```

## Report Format

Return only:
1. [Expected deliverable 1]
2. [Expected deliverable 2]
3. [Expected deliverable N]
4. Any missing information or deviations from specification.
```

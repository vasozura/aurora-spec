# Aurora Task Template

Document ID: TEMPLATE-000001  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 12-Templates/TASK_TEMPLATE.md  
Document Type: Task Template  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md  

---

## 1. Purpose

This template defines the standard structure for every Aurora task document.

Every task given to a human contributor, Claude Code, Codex, Gemini CLI, Cursor or any other AI implementation agent must follow this structure unless an approved exception exists.

The goal is deterministic execution.

A task must be small, scoped, reviewable, reversible and testable.

---

## 2. Usage Rule

Copy this template when creating a new task.

Replace every placeholder wrapped in angle brackets.

Do not remove required sections.

Do not merge unrelated work into one task.

Do not allow the AI agent to continue beyond the task.

---

## 3. File Naming Rule

Task files must use this pattern:

```text
TASK-000000_SHORT_ACTION_NAME.md
```

Example:

```text
TASK-000006_CREATE_ADR_TEMPLATE.md
```

Task files should be stored in:

```text
08-Tasks/Sprint-0/
```

or in the relevant sprint folder.

---

## 4. Required Task Template

```markdown
# TASK-000000: <Short Task Title>

Task ID: TASK-000000  
Version: 0.1.0  
Status: Draft  
Priority: <Critical | High | Medium | Low>  
Sprint: <Sprint Name>  
Document Type: AI Implementation Task  
Target Repository: <aurora-spec | aurora-studio | aurora-assets>  
Target File: <path/to/target/file.md>  
Depends On: <TASK-ID or Document-ID>  
Required Input: <required input file paths>  

---

## 1. Objective

<Write a clear objective in one to three paragraphs.>

This task must describe exactly what should be created, changed or verified.

The objective must not contain hidden requirements.

---

## 2. Strict Scope

Create or update only this file:

\`\`\`text
<target file path>
\`\`\`

Do not create any other file unless explicitly listed here.

Allowed files:

\`\`\`text
<file path 1>
<file path 2>
\`\`\`

If only one file is allowed, list only one file.

---

## 3. Preconditions

Before executing this task, verify that the following files or conditions exist:

\`\`\`text
<required file or condition 1>
<required file or condition 2>
\`\`\`

If a precondition is missing, stop and report:

\`\`\`text
TASK-000000 cannot be executed because <missing requirement> is incomplete.
\`\`\`

Do not continue if any precondition fails.

---

## 4. Required Action

<Describe the exact action to perform.>

If this is a documentation task, write the Markdown content from section 8 of this task into the target file.

If this is an implementation task, follow the implementation instructions exactly.

Do not invent additional behavior.

Do not expand scope.

Do not continue to the next task.

---

## 5. Forbidden Actions

The AI implementation agent must not:

- Modify files outside the allowed scope.
- Create unrequested files.
- Rename files, folders, IDs or modules.
- Add dependencies unless explicitly allowed.
- Invent architecture.
- Modify public APIs unless explicitly required.
- Add implementation code to documentation-only tasks.
- Continue to the next task.
- Guess missing requirements.
- Hide deviations from the report.

Add task-specific forbidden actions below:

- <task-specific forbidden action 1>
- <task-specific forbidden action 2>

---

## 6. Validation

After completing the required action, verify:

1. `<target file path>` exists.
2. The file is valid UTF-8.
3. No files outside the allowed scope were changed.
4. No forbidden action was performed.
5. The output follows the required structure.
6. The output is ready for review.

Add task-specific validation checks below:

7. <task-specific validation check>
8. <task-specific validation check>

---

## 7. Expected Report

After completion, provide only:

1. Created or updated file path
2. Preconditions verified
3. Validation performed
4. Confirmation that no other files were changed
5. Confirmation that no forbidden actions were performed
6. Deviations, if any
7. Short readiness note for Git commit

Do not continue beyond TASK-000000.

---

## 8. Content or Implementation Instructions

<For documentation tasks, place the exact Markdown content to write here.>

<For implementation tasks, place exact implementation instructions here.>

Do not leave this section vague.
```

---

## 5. Required Sections Explained

### Objective

The objective defines the result.

It must be specific.

Bad objective:

```text
Improve the project.
```

Good objective:

```text
Create the ADR template used by all future Architecture Decision Records.
```

---

### Strict Scope

The scope limits what the AI agent may touch.

If a file is not listed, the AI must not modify it.

---

### Preconditions

Preconditions prevent the AI from working on an invalid foundation.

If required files are missing, the AI must stop.

---

### Required Action

Required action defines what the AI must do.

This section must be operational.

---

### Forbidden Actions

Forbidden actions protect the project from scope creep.

Every task must include general and task-specific forbidden actions.

---

### Validation

Validation defines how the result is checked.

Validation must be concrete.

---

### Expected Report

The expected report forces the AI to summarize factual results only.

The report must not contain unverified claims.

---

### Content or Implementation Instructions

This section contains the exact content or implementation steps.

Documentation tasks should include the full Markdown content to write.

Implementation tasks should include exact technical instructions.

---

## 6. AI Safety Rule

If the task is incomplete, contradictory or unclear, the AI agent must stop and report the problem.

The AI agent must not guess.

Stopping is correct behavior when requirements are incomplete.

---

## 7. Task Size Rule

A valid Aurora task should normally change one controlled unit.

Preferred examples:

- One Markdown document
- One template
- One ADR
- One module phase
- One data model
- One public interface
- One test specification
- One implementation unit

Invalid examples:

- Build the whole app
- Create all modules
- Implement the UI and backend
- Design the architecture and code it
- Fix everything
- Continue until done

---

## 8. Review Checklist

A task is ready for use when:

1. It has a unique Task ID.
2. It has a clear target file.
3. It has explicit dependencies.
4. It has strict scope.
5. It has preconditions.
6. It has required action.
7. It has forbidden actions.
8. It has validation.
9. It has an expected report.
10. It does not allow uncontrolled continuation.

---

## 9. Summary

This template exists to keep Aurora development controlled.

Every task must behave like a contract.

The AI agent receives a task, executes only that task, reports the result and stops.

No improvisation.

No silent expansion.

No architectural shamanism.

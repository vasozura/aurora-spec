---
id: TEMPLATE-0003
title: Architecture Decision Record Template
version: 0.1.0
status: Draft
owner: Aurora Labs
created: 2026-06-26
updated: 2026-06-26
depends_on: [GOV-0001, GOV-0003]
---

# Architecture Decision Record Template

## Purpose

This template defines the required structure for all Aurora Studio Architecture Decision Records (ADRs).
An ADR documents a significant architectural decision, why it was made, and what it replaces.

## Scope

All ADRs written for `aurora-spec/10-ADR/`.

## Non-Goals

- ADRs document decisions already made. Proposals go in `11-RFC/` first.
- This template does not define review criteria.

## Ownership

Owner: Aurora Labs
Change authority: Architecture review required for template changes.

## Change Rules

- ADRs are immutable once approved. A new ADR must supersede an old one.
- ADRs may not be deleted. Move to `99-Archive/` if superseded.

---

## Template

Copy everything below this line into the new ADR file.

---

```markdown
---
id: ADR-XXXXXX
title: [Decision Title]
version: 0.1.0
status: [Proposed | Accepted | Rejected | Superseded]
owner: Aurora Labs
created: YYYY-MM-DD
updated: YYYY-MM-DD
supersedes: []
superseded_by: []
depends_on: []
---

# ADR-XXXXXX — [Decision Title]

## Status

[Proposed | Accepted | Rejected | Superseded]

## Context

[Describe the situation that forced this decision.
What problem existed? What constraints applied?
What was ambiguous or in conflict?]

## Decision

[State the decision clearly and precisely.
One or two sentences maximum.
"We will…" form preferred.]

## Options Considered

### Option A — [Name]

[Description]

Pros:
- [Pro 1]

Cons:
- [Con 1]

### Option B — [Name]

[Description]

Pros:
- [Pro 1]

Cons:
- [Con 1]

### Option C — [Name] _(chosen)_

[Description]

Pros:
- [Pro 1]

Cons:
- [Con 1]

## Consequences

### Positive

- [Positive consequence 1]

### Negative

- [Negative consequence 1]

### Neutral

- [Neutral consequence 1]

## Affected Modules

[List MOD- IDs affected by this decision.]

## Affected APIs

[List API- IDs affected by this decision.]

## Rollback Strategy

[How can this decision be reversed if it proves wrong?
Is rollback possible? What is the cost?]
```

---
id: TEMPLATE-0004
title: Request for Comment Template
version: 0.1.0
status: Draft
owner: Aurora Labs
created: 2026-06-26
updated: 2026-06-26
depends_on: [GOV-0001, GOV-0003]
---

# Request for Comment Template

## Purpose

This template defines the required structure for all Aurora Studio Requests for Comment (RFCs).
An RFC is a proposal for a change or addition that has not yet been decided.
RFCs precede ADRs for significant decisions.

## Scope

All RFCs written for `aurora-spec/11-RFC/`.

## Non-Goals

- RFCs are proposals, not decisions. Decisions are recorded in `10-ADR/`.
- This template does not grant authority to implement the proposal.

## Ownership

Owner: Aurora Labs
Change authority: Any contributor may file an RFC. Architecture team decides outcome.

## Change Rules

- An RFC may be updated until it reaches `Decided` status.
- Once decided, the RFC is closed and an ADR is created if the proposal was accepted.
- RFCs may not be deleted. Move to `99-Archive/` if closed.

---

## Template

Copy everything below this line into the new RFC file.

---

```markdown
---
id: RFC-XXXXXX
title: [Proposal Title]
version: 0.1.0
status: [Open | Under Review | Decided | Withdrawn]
owner: Aurora Labs
author: [Name or role]
created: YYYY-MM-DD
updated: YYYY-MM-DD
decision_deadline: YYYY-MM-DD
decision: [Accepted | Rejected | Deferred | blank if open]
resulting_adr: []
depends_on: []
---

# RFC-XXXXXX — [Proposal Title]

## Status

[Open | Under Review | Decided | Withdrawn]

## Problem

[Describe the problem or gap this RFC addresses.
Why is a change needed? What is currently broken, missing, or inconsistent?]

## Proposal

[Describe the proposed change or addition clearly and precisely.
What exactly would change? What new thing would exist?]

## Alternatives Considered

### Alternative A — [Name]

[Description and why it was not chosen as the proposal.]

### Alternative B — [Name]

[Description and why it was not chosen as the proposal.]

## Impact

### Affected Documents

[List document IDs that would need to change if this RFC is accepted.]

### Affected Modules

[List MOD- IDs affected.]

### Affected APIs

[List API- IDs affected.]

### Affected Tasks

[List TASK- IDs that would be blocked, modified, or created.]

## Open Questions

1. [Question 1]
2. [Question 2]

## Decision Deadline

[YYYY-MM-DD — date by which a decision must be made.]

## Decision

[Leave blank until decided.]

Decision: [Accepted | Rejected | Deferred]
Decided by: [Name or role]
Decided on: [YYYY-MM-DD]
Resulting ADR: [ADR-XXXXXX or N/A]
```

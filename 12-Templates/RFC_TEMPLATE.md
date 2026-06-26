# Aurora RFC Template

Document ID: TEMPLATE-000003  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 12-Templates/RFC_TEMPLATE.md  
Document Type: RFC Template  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 02-Architecture/ARCHITECTURE.md  

---

## 1. Purpose

This template defines the standard structure for Aurora Requests for Comments.

A Request for Comments, abbreviated as RFC, is used to propose, discuss and evaluate ideas before they become approved specifications, ADRs, tasks or rejected proposals.

RFCs exist to prevent important ideas from remaining only in chat history, informal notes or undocumented AI outputs.

An RFC is not an implementation task.

An RFC is not automatically approved architecture.

An RFC is a structured proposal.

---

## 2. When To Use An RFC

Use an RFC when an idea:

- Needs discussion before approval
- May affect product direction
- May affect architecture
- May affect module responsibility
- May affect user workflow
- May introduce a new major feature
- May introduce a new concept into Aurora Film Language
- May require a future ADR
- May require multiple specifications
- May affect plugins, SDKs or public interfaces
- Is important but not ready for implementation

Do not use an RFC for:

- Small spelling corrections
- Formatting cleanup
- Simple task execution
- Already-approved implementation work
- Minor wording changes
- Private scratch notes

---

## 3. File Naming Rule

RFC files must use this pattern:

```text
RFC-000000_SHORT_PROPOSAL_NAME.md
```

Example:

```text
RFC-000001_DEFINE_AURORA_FILM_LANGUAGE_SCOPE.md
```

RFC files must be stored in:

```text
11-RFC/
```

RFC IDs must never be reused.

---

## 4. RFC Status Values

Allowed RFC statuses:

- `Draft`
- `Review`
- `Accepted`
- `Rejected`
- `Superseded`
- `Archived`

Meaning:

`Draft` means the proposal is being written.

`Review` means the proposal is ready for evaluation.

`Accepted` means the proposal may become an ADR, specification or task.

`Rejected` means the proposal was considered but not adopted.

`Superseded` means another RFC replaced this proposal.

`Archived` means the RFC is kept for historical reference only.

---

## 5. Required RFC Template

```markdown
# RFC-000000: <Proposal Title>

Document ID: RFC-000000  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 11-RFC/RFC-000000_<SHORT_PROPOSAL_NAME>.md  
Document Type: Request for Comments  
Depends On: <related Constitution, AES, Architecture, Module, API, DATA, AFL or TASK documents>  
Supersedes: <RFC-ID or None>  
Superseded By: <RFC-ID or None>  

---

## 1. Proposal Summary

<Write a short summary of the proposal in one to three paragraphs.>

The summary must clearly state what is being proposed.

---

## 2. Motivation

<Explain why this proposal exists.>

Include:

- What problem it solves
- What opportunity it creates
- Why the current state is insufficient
- Why the proposal matters to Aurora

---

## 3. Background

<Provide context required to understand the proposal.>

Include links or references to relevant documents, tasks, ADRs, modules, interfaces or prior decisions.

---

## 4. Proposal

<Describe the proposed idea clearly.>

The proposal must be specific enough to review.

The proposal must not require implementation agents to guess.

---

## 5. Scope

This RFC applies to:

- <product area, module, workflow, architecture area or concept>

This RFC does not apply to:

- <excluded area>

---

## 6. Non-Goals

This RFC does not propose:

- <non-goal 1>
- <non-goal 2>

Non-goals are required to prevent scope expansion.

---

## 7. User Impact

Expected user impact:

- <user impact>

Affected users or roles:

- <creator, editor, plugin developer, AI workflow designer, system integrator, etc.>

---

## 8. Product Impact

Expected product impact:

- <product impact>

Affected product areas:

- <area>

---

## 9. Architecture Impact

Architecture impact:

\`\`\`text
<None | Low | Medium | High>
\`\`\`

Explanation:

<Explain whether this RFC may affect architecture, dependency direction, module boundaries, plugin boundaries or system layers.>

If architecture impact is Medium or High, an ADR may be required.

---

## 10. Data Impact

Data impact:

\`\`\`text
<None | Low | Medium | High>
\`\`\`

Explanation:

<Explain whether this RFC may affect project data, metadata, schemas, storage, migration or compatibility.>

---

## 11. API or SDK Impact

API or SDK impact:

\`\`\`text
<None | Low | Medium | High>
\`\`\`

Explanation:

<Explain whether this RFC may affect public APIs, plugin SDKs or integration contracts.>

---

## 12. Security Impact

Security impact:

\`\`\`text
<None | Low | Medium | High>
\`\`\`

Explanation:

<Explain permissions, trust boundaries, plugin risks, file access risks, external service risks or user ownership concerns.>

---

## 13. Offline-First Impact

Offline-first impact:

\`\`\`text
<None | Compatible | Requires Online Capability | Not Applicable>
\`\`\`

Explanation:

<Explain whether the proposal affects offline operation.>

Aurora must remain offline-first unless an exception is explicitly justified.

---

## 14. Alternatives Considered

### Alternative A: <Alternative Name>

Description:

<Describe the alternative.>

Advantages:

- <advantage>

Disadvantages:

- <disadvantage>

Reason not selected:

<Explain.>

---

### Alternative B: <Alternative Name>

Description:

<Describe the alternative.>

Advantages:

- <advantage>

Disadvantages:

- <disadvantage>

Reason not selected:

<Explain.>

---

## 15. Open Questions

The following questions remain open:

- <question 1>
- <question 2>

Open questions must be resolved before this RFC can become an approved specification or ADR.

---

## 16. Required Follow-Up Documents

If accepted, this RFC may require:

- ADR: <Yes | No | Maybe>
- Product specification: <Yes | No | Maybe>
- Architecture update: <Yes | No | Maybe>
- Module specification: <Yes | No | Maybe>
- Interface specification: <Yes | No | Maybe>
- Data specification: <Yes | No | Maybe>
- Test specification: <Yes | No | Maybe>
- AI implementation tasks: <Yes | No | Maybe>

Expected follow-up documents:

- <document ID or future placeholder>

---

## 17. Acceptance Criteria

This RFC is acceptable when:

1. The proposal is clear.
2. Motivation is documented.
3. Scope and non-goals are explicit.
4. User impact is documented.
5. Product impact is documented.
6. Architecture impact is documented.
7. Data impact is documented.
8. API or SDK impact is documented.
9. Security impact is documented.
10. Offline-first impact is documented.
11. Alternatives are considered.
12. Open questions are listed.
13. Required follow-up documents are identified.
14. The RFC does not violate the Aurora Constitution.
15. The RFC is consistent with the Aurora Engineering Standard.

---

## 18. Review Decision

Reviewer:

\`\`\`text
<Reviewer name or role>
\`\`\`

Decision:

\`\`\`text
<Accepted | Rejected | Needs Revision | Superseded | Archived>
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

## 6. RFC Quality Rules

An RFC must be:

- Clear
- Scoped
- Reviewable
- Linked to relevant documents
- Honest about tradeoffs
- Explicit about uncertainty
- Explicit about follow-up work

An RFC must not:

- Act as implementation permission by itself
- Hide architecture changes
- Hide compatibility risks
- Combine unrelated proposals
- Replace an ADR when an ADR is required
- Replace a specification when a specification is required
- Allow uncontrolled AI implementation

---

## 7. RFC Lifecycle

A typical RFC lifecycle is:

```text
Idea
  ↓
RFC Draft
  ↓
Review
  ↓
Accepted or Rejected
  ↓
If accepted:
  ADR and/or Specification
  ↓
AI Tasks
  ↓
Implementation
```

Acceptance of an RFC does not automatically authorize implementation.

Implementation requires approved specifications and tasks.

---

## 8. Superseding Rule

If an RFC replaces a previous RFC:

1. The new RFC must list the previous RFC under `Supersedes`.
2. The previous RFC must be updated to `Superseded`.
3. The previous RFC must list the new RFC under `Superseded By`.
4. Affected follow-up documents must be reviewed.

No RFC may be silently overwritten.

---

## 9. Summary

This template ensures that Aurora ideas are captured before they become architecture, specifications or implementation tasks.

Good ideas are not enough.

They must be structured, reviewed and connected to the engineering system.

Aurora must not be built from scattered inspiration.

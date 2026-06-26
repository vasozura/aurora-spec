# aurora-spec

Aurora Specification Repository — Single Source of Truth for Aurora Studio.

## What This Repository Is

This repository contains the complete product specification for Aurora Studio.
It is the authoritative source for all product decisions, architecture, data models, APIs, and AI language definitions.

## Core Principles

**Aurora Studio is specification-driven.**
No implementation code may be written before the relevant specification has been written, reviewed, and approved.

**This repository is the Single Source of Truth.**
If a behaviour, interface, or constraint is not documented here, it does not exist.
If code contradicts this repository, the code is wrong.

**Code must follow specification.**
The `aurora-studio` repository is a downstream consumer of this repository.
Developers and AI agents implement what is specified here — they do not invent it.

**AI agents must follow governance documents.**
Every AI coding agent must read and comply with:
- `00-Governance/AURORA_CONSTITUTION.md`
- `00-Governance/AI_IMPLEMENTATION_PROTOCOL.md`
- `00-Governance/REVIEW_STANDARD.md`

Agents that violate governance must stop and produce a Missing Information Report.

## Sprint 0 Scope

Sprint 0 contains no application code.
Sprint 0 output is this repository: governance documents, templates, and initial specification skeletons.

No Python, no GUI, no database, no plugins, no business logic exists yet.

## Repository Structure

```
aurora-spec/
├── 00-Governance/     Engineering rules, constitution, AI protocol, review standard
├── 01-Product/        Product vision, roadmap, requirements
├── 02-Architecture/   System architecture and layer definitions
├── 03-Modules/        Per-module specifications (8-phase lifecycle)
├── 04-Interfaces/     Public API contracts
├── 05-Data/           Data models
├── 06-AI/             Aurora Film Language specification
├── 07-SDK/            SDK contracts and extension points
├── 08-Tasks/          Implementation task backlog
├── 09-Tests/          Test specifications
├── 10-ADR/            Architecture Decision Records
├── 11-RFC/            Requests for Comment
├── 12-Templates/      Document templates
└── 99-Archive/        Superseded documents
```

## ID System

All documents use stable IDs. See `00-Governance/GLOSSARY.md` for the full prefix list.

## Related Repositories

| Repository | Purpose |
|---|---|
| `aurora-aes` | Aurora Engineering Standard — methodology rules |
| `aurora-spec` | This repository — product specification |
| `aurora-studio` | Executable application — implements this spec |

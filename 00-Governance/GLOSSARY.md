---
id: GOV-0004
title: Glossary
version: 0.1.0
status: Draft
owner: Aurora Labs
created: 2026-06-26
updated: 2026-06-26
depends_on: [GOV-0001]
---

# Glossary

## Purpose

This document defines all authoritative terms, abbreviations, and ID prefixes used across the Aurora Studio project.
When a term appears in any specification, architecture document, or task, its meaning is defined here.

## Scope

- All repositories: `aurora-aes`, `aurora-spec`, `aurora-studio`
- All contributors (human and AI)

## Non-Goals

- This is not a product specification.
- This is not an architecture document.
- This does not define implementation rules.

## Ownership

Owner: Aurora Labs
Change authority: Any contributor may propose additions. Removals and redefinitions require architecture review.

## Change Rules

- New terms may be added by PR with no RFC required.
- Existing terms may not be renamed or removed without an ADR.
- ID prefix assignments are permanent once assigned.

---

## ID Prefix Registry

| Prefix | Element Type | Example |
|---|---|---|
| `MOD-` | Module | MOD-0001 |
| `TASK-` | Implementation or specification task | TASK-000001 |
| `ADR-` | Architecture Decision Record | ADR-000001 |
| `RFC-` | Request for Comment | RFC-000001 |
| `API-` | Public API Contract | API-000001 |
| `TEST-` | Test Specification | TEST-000001 |
| `DATA-` | Data Model | DATA-000001 |
| `AFL-` | Aurora Film Language element | AFL-000001 |
| `STD-` | Engineering Standard | STD-000001 |
| `GOV-` | Governance document | GOV-0001 |
| `PROD-` | Product document | PROD-0001 |
| `ARCH-` | Architecture document | ARCH-0001 |
| `TEMPLATE-` | Template document | TEMPLATE-0001 |

---

## Term Definitions

### Aurora Studio

The executable Creative Operating System for AI filmmaking. Implemented in the `aurora-studio` repository.

### aurora-spec

The specification repository. Single Source of Truth for all product decisions. This repository.

### aurora-aes

The Aurora Engineering Standard repository. Defines methodology, not product.

### AFL — Aurora Film Language

The internal cinematic data model used by Aurora Studio. AFL is the source of truth for creative intent. Prompt text is an export output of AFL, not the input.

### Module

A bounded unit of functionality in Aurora Studio. Every module must pass the 8-phase lifecycle before implementation begins.

### 8-Phase Module Lifecycle

The required sequence every module must complete:
1. Vision
2. Specification
3. Architecture
4. Data Model
5. Public API
6. Tests
7. AI Tasks
8. Review

### Single Source of Truth

`aurora-spec` is the only authoritative source for product definitions. Code in `aurora-studio` must conform to it, not the reverse.

### Missing Information Report

A structured report produced by an AI agent when a specification is incomplete, inconsistent, or impossible to implement safely. The agent must stop work and produce this report instead of guessing.

### Sprint 0

The founding sprint. Output is `aurora-spec` governance and template documents only. No executable application code.

### ADR — Architecture Decision Record

A document recording a significant architecture decision, its context, options considered, and consequences.

### RFC — Request for Comment

A document proposing a change or addition that has not yet been decided. RFCs precede ADRs.

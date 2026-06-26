---
id: ARCH-0001
title: Aurora Studio Architecture
version: 0.1.0
status: Draft
owner: Aurora Labs
created: 2026-06-26
updated: 2026-06-26
depends_on: [GOV-0001, PROD-0001]
---

# Aurora Studio Architecture

## Purpose

This document defines the high-level system architecture of Aurora Studio.
It establishes layer boundaries, dependency rules, and communication patterns that all modules must follow.

## Scope

- All layers and subsystems of Aurora Studio
- Dependency direction rules
- Plugin system boundaries
- Communication patterns

## Non-Goals

- This document does not define per-module architecture.
- This document does not define API contracts (see `04-Interfaces/`).
- This document does not define data models (see `05-Data/`).
- This document is not an implementation guide.

## Ownership

Owner: Aurora Labs
Change authority: ADR required for any architectural change.

## Change Rules

- No layer boundary may be changed without an ADR.
- No new layer may be introduced without an RFC followed by an ADR.
- Module specs must reference the layer they belong to.

---

## Architecture Body

> **Status: Skeleton — full architecture to be written in TASK-000005.**

The following sections are placeholders. They must be completed and approved before any module is specified.

### Layer Model

_[To be completed in TASK-000005]_

Planned layers:
1. Desktop Layer
2. Core Layer
3. Application Services Layer
4. Domain Layer
5. Infrastructure Layer
6. Plugin Layer

### Dependency Rules

_[To be completed in TASK-000005]_

Higher layers may depend on lower layers. Lower layers must not depend on higher layers.

### Event Communication

_[To be completed in TASK-000005]_

### Plugin Boundaries

_[To be completed in TASK-000005]_

### Offline-First Rules

_[To be completed in TASK-000005]_

Aurora Studio must function without network access. Network is optional and always proxied through defined service interfaces.

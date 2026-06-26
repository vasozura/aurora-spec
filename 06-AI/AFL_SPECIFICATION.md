---
id: AFL-0001
title: Aurora Film Language Specification
version: 0.1.0
status: Draft
owner: Aurora Labs
created: 2026-06-26
updated: 2026-06-26
depends_on: [GOV-0001, ARCH-0001]
---

# Aurora Film Language (AFL) Specification

## Purpose

This document defines Aurora Film Language (AFL), the internal cinematic data model used by Aurora Studio.
AFL is the structured representation of creative intent inside Aurora Studio.

## Scope

- All AFL element definitions
- The relationship between AFL and export formats
- The principle that prompts are outputs, not inputs

## Non-Goals

- This document does not define Python data classes (see `05-Data/`).
- This document does not define export plugin implementations.
- This document does not define the UI for editing AFL elements.

## Ownership

Owner: Aurora Labs
Change authority: ADR required for any AFL element change. New elements require RFC first.

## Change Rules

- AFL element definitions are stable once approved.
- No AFL element may be renamed without an ADR documenting migration impact.
- Export formats are downstream of AFL and must adapt to AFL, not the reverse.

---

## Core Principle

**Prompts are export outputs. AFL is the internal model.**

Aurora Studio does not work in prompt text. It works in structured cinematic intent expressed as AFL.
When a user exports to an AI video provider, Aurora generates prompt text from AFL elements.
The prompt is a rendering of the internal model, not the model itself.

---

## AFL Element Definitions

> **Status: Skeleton — full AFL specification to be written in TASK-000006.**

The following elements are listed as placeholders. Each requires a full definition in TASK-000006.

### AFL-0001 Scene

_[To be completed in TASK-000006]_

A scene is the top-level container of cinematic intent.

### AFL-0002 Shot

_[To be completed in TASK-000006]_

### AFL-0003 Beat

_[To be completed in TASK-000006]_

### AFL-0004 Character

_[To be completed in TASK-000006]_

### AFL-0005 Emotion

_[To be completed in TASK-000006]_

### AFL-0006 Symbol

_[To be completed in TASK-000006]_

### AFL-0007 Camera

_[To be completed in TASK-000006]_

### AFL-0008 Composition

_[To be completed in TASK-000006]_

### AFL-0009 Motion

_[To be completed in TASK-000006]_

### AFL-0010 Transition

_[To be completed in TASK-000006]_

### AFL-0011 Visual Meaning

_[To be completed in TASK-000006]_

### AFL-0012 Export Intent

_[To be completed in TASK-000006]_

Export Intent defines the target AI system and any system-specific constraints. It is a rendering instruction, not part of the creative model.

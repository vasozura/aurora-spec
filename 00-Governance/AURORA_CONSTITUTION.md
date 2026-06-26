# Aurora Constitution

Document ID: GOV-000001  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 00-Governance/AURORA_CONSTITUTION.md  
Authority Level: Highest  
Created For: Aurora Studio  
Document Type: Governance Specification  

---

## 1. Purpose

This document defines the immutable engineering, product, architectural and AI-development principles of Aurora Studio.

The Aurora Constitution is the highest authority in the Aurora project.

No specification, architecture document, implementation task, pull request, generated code, plugin, public API, AI-generated output, or future feature may violate this Constitution.

If a conflict exists between this Constitution and any other document, this Constitution takes precedence.

---

## 2. Mission

Aurora Studio exists to become a Creative Operating System for AI filmmaking.

Aurora transforms creative intent into structured cinematic workflows that can be understood, edited, reviewed, versioned and exported to different AI systems.

Aurora is designed to help creators build films before generation begins.

---

## 3. Vision

Every creator deserves an intelligent creative environment.

Aurora shall become the professional workspace where stories, characters, emotions, scenes, symbols, camera language, sound, rhythm and cinematic structure are designed before any AI system generates images, video, music, voice or text.

Aurora must not depend on any single AI model, provider or platform.

Aurora must survive model changes, provider changes and technology shifts.

---

## 4. Core Philosophy

Aurora is not a prompt generator.

Aurora is not an AI model.

Aurora is not a video generator.

Aurora is not a chat interface.

Aurora is a creative workflow platform.

Prompts are outputs.

Film language is internal.

AI generation is an execution step, not the core product.

The core product is structured cinematic intent.

---

## 5. Authority Model

The Aurora Constitution has the highest authority.

The authority order is:

1. Aurora Constitution
2. Aurora Engineering Standard
3. Architecture Decision Records
4. Module Specifications
5. Interface Specifications
6. Data Specifications
7. Task Specifications
8. Implementation Code
9. Tests
10. Generated Outputs

Code must follow the specification.

The specification must not be rewritten merely to justify accidental implementation.

---

## 6. Normative Language

The following words have strict meanings:

- MUST means mandatory.
- MUST NOT means forbidden.
- SHOULD means recommended unless there is a documented reason.
- SHOULD NOT means discouraged unless there is a documented reason.
- MAY means optional.
- REQUIRED means mandatory.
- FORBIDDEN means not allowed.

Any AI implementation agent must interpret these terms strictly.

---

## 7. Constitutional Laws

### LAW-001: Human Creativity Has Priority

Human creative intent always has priority over automation.

AI may assist, suggest, structure, analyze and generate.

Humans decide.

---

### LAW-002: Aurora Core Must Be AI-Provider Independent

Aurora Core must never depend on a specific AI provider, AI model, API vendor, cloud platform or proprietary generation system.

All external AI systems must communicate with Aurora through plugins, adapters or SDK-defined interfaces.

---

### LAW-003: Specification Before Implementation

Every public feature must have an approved specification before implementation begins.

Implementation without specification is not allowed.

---

### LAW-004: Architecture Must Not Be Invented During Implementation

Implementation follows architecture.

Implementation must never create architecture by accident.

If architecture is missing, incomplete or contradictory, implementation must stop and report the problem.

---

### LAW-005: Single Responsibility Per Module

Every module must have one clear responsibility.

A module must not perform unrelated work.

If a module grows beyond its responsibility, it must be split through an approved specification or ADR.

---

### LAW-006: Stable Public APIs

Public APIs must remain stable.

Breaking changes require an Architecture Decision Record.

No public API may be changed silently.

---

### LAW-007: Reproducible Projects

Every Aurora project must be reproducible.

Opening the same Aurora project on another supported computer must produce identical project structure, metadata and interpretation.

---

### LAW-008: Offline First

Offline work is a first-class capability.

Aurora must remain usable without an Internet connection whenever technically possible.

Cloud services are optional extensions, not mandatory foundations.

---

### LAW-009: Modular by Default

Every major subsystem must be modular.

Subsystems should be replaceable without rewriting Aurora Core.

Tight coupling is forbidden unless explicitly approved by architecture.

---

### LAW-010: Plugins Extend, Not Modify

Plugins may extend Aurora.

Plugins must never modify Aurora Core directly.

Plugins must operate only through documented interfaces.

---

### LAW-011: Architectural Decisions Must Be Documented

Every significant architectural decision must be documented in an ADR.

Undocumented architectural changes are not allowed.

---

### LAW-012: Tests Are Part of Completion

Every implementation must include automated tests whenever applicable.

A feature without appropriate tests is incomplete.

---

### LAW-013: Changes Must Be Reversible

Every major user-facing change should be reversible whenever technically possible.

Undo, version history, backup and recoverability are fundamental design goals.

---

### LAW-014: Performance Is Product Quality

Performance is a feature.

Slow software damages creative flow.

Aurora must treat responsiveness, startup time, project loading time and export performance as product quality requirements.

---

### LAW-015: Aurora Film Language Is Internal

The internal representation of cinematic information shall be Aurora Film Language.

Prompt text is an export format.

Prompt text must not become the internal source of truth.

---

### LAW-016: User Ownership Comes First

Aurora never assumes ownership of user projects, creative assets, prompts, scripts, generated media or artistic decisions.

User work belongs to the user.

---

### LAW-017: Specification Repository Is the Source of Truth

The aurora-spec repository is the Single Source of Truth for product behavior, architecture, module responsibilities, interfaces, data models and AI implementation tasks.

The aurora-studio codebase must follow aurora-spec.

---

### LAW-018: AI Implementation Must Be Deterministic

AI implementation agents must act as implementation engineers, not architects.

If a specification is incomplete, the AI must stop and report the missing information.

The AI must not guess, invent architecture, add hidden features or silently change scope.

---

### LAW-019: Small Completed Units Are Preferred

Small completed modules are preferred over large unfinished systems.

Tasks must be small enough to review, test and revert.

Large vague tasks are forbidden.

---

### LAW-020: Built for Decades

Aurora is built for decades, not demonstrations.

Long-term maintainability has priority over short-term convenience.

---

### LAW-021: No Hidden Dependencies

Aurora must not depend on hidden services, undocumented runtime requirements, invisible cloud behavior or untracked external state.

All dependencies must be explicit.

---

### LAW-022: Cross-Platform by Design

Aurora should be designed for Windows and Linux from the beginning.

Platform-specific behavior must be isolated and documented.

---

### LAW-023: Security Boundaries Are Mandatory

Plugins, scripts, AI agents and import/export systems must operate within defined security boundaries.

No extension may receive unrestricted access by default.

---

### LAW-024: Data Must Be Understandable

Aurora project data must be understandable, inspectable and recoverable.

Binary-only opaque project formats should be avoided unless technically justified.

---

### LAW-025: Review Is Mandatory

Every specification, architecture decision, task and implementation must be reviewable.

If a change cannot be reviewed clearly, it is not ready.

---

## 8. AI Agent Rules

Any AI system working on Aurora must follow these rules:

1. The AI is not the architect unless explicitly assigned that role.
2. The AI must execute only the assigned task.
3. The AI must not continue to the next task without instruction.
4. The AI must not invent missing requirements.
5. The AI must not add dependencies unless explicitly allowed.
6. The AI must not create files outside the allowed scope.
7. The AI must not rename IDs, modules, files or folders.
8. The AI must report ambiguity instead of guessing.
9. The AI must preserve public interfaces.
10. The AI must provide a short implementation report after each task.

---

## 9. Specification Rules

Every specification document must include:

- Document ID
- Version
- Status
- Owner
- Purpose
- Scope
- Non-scope
- Dependencies
- Acceptance criteria
- Change history

Specifications must be written so that an AI implementation agent can execute them without additional interpretation.

---

## 10. Task Rules

Every implementation task must include:

- Task ID
- Status
- Priority
- Sprint
- Target files
- Objective
- Scope
- Non-scope
- Required action
- Forbidden action
- Acceptance criteria
- Expected report

Tasks must be small, deterministic and reviewable.

---

## 11. Conflict Resolution

If two documents conflict, use the following order:

1. Aurora Constitution
2. Aurora Engineering Standard
3. Approved ADR
4. Approved module specification
5. Approved interface specification
6. Approved data specification
7. Approved task
8. Existing implementation

If the conflict cannot be resolved, implementation must stop until the conflict is reviewed.

---

## 12. Change Control

This Constitution may change only through an approved constitutional change process.

Any change must include:

- Reason for change
- Impact analysis
- Affected documents
- Migration requirements
- Review decision
- Version update

Silent modification is forbidden.

---

## 13. Final Statement

The Aurora Constitution exists to protect Aurora from accidental complexity, unstable architecture, short-term decisions, vendor lock-in, uncontrolled AI implementation and undocumented product drift.

Every contributor, whether human or AI, is expected to follow this Constitution.

Aurora must be built with discipline before speed.

This document has the highest authority within the Aurora project.

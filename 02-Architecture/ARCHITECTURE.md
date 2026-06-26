# Aurora Architecture

Document ID: ARCH-000001  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 02-Architecture/ARCHITECTURE.md  
Document Type: Architecture Specification  
Depends On: 00-Governance/AURORA_CONSTITUTION.md  

---

## 1. Purpose

This document defines the high-level architecture of Aurora Studio.

It describes the major system layers, their responsibilities, dependency rules, communication rules, data ownership rules, plugin boundaries and implementation constraints.

Implementation details belong to individual module specifications.

This document does not define code structure, class names, database schemas or GUI layouts.

---

## 2. Architectural Goal

Aurora Studio must be:

- Modular
- Extensible
- Offline-first
- Plugin-based
- AI-provider independent
- Testable
- Maintainable
- Deterministic
- Cross-platform where technically possible
- Suitable for long-term evolution

Aurora must be designed as a creative workflow platform, not as a prompt generator.

---

## 3. Architectural Authority

This document is subordinate to:

```text
00-Governance/AURORA_CONSTITUTION.md
```

If this document conflicts with the Constitution, the Constitution takes precedence.

Architecture must never be invented during implementation.

If implementation requires architectural clarification, work must stop until the architecture is updated through an approved process.

---

## 4. High-Level Architecture

Aurora Studio is composed of the following major layers:

```text
Aurora Desktop
    ↓
Aurora Core
    ↓
Application Services
    ↓
Domain Layer
    ↓
Infrastructure
    ↓
Plugins
```

Dependencies must point downward only.

Circular dependencies are forbidden.

No layer may access the private internals of another layer.

Communication must happen through public APIs, events or approved interfaces.

---

## 5. Layer 1: Aurora Desktop

Aurora Desktop is responsible for the user interface.

Responsibilities:

- Main application window
- Menus
- Dialogs
- Timeline interface
- Scene panels
- Asset panels
- Property panels
- User interaction
- Visual feedback
- UI state presentation

Aurora Desktop must not contain business logic.

Aurora Desktop must not directly access plugin internals.

Aurora Desktop must not directly manipulate persistent project data.

Aurora Desktop sends user intentions to Application Services or Aurora Core through approved interfaces.

---

## 6. Layer 2: Aurora Core

Aurora Core is the central product layer.

Responsibilities:

- Project lifecycle
- Scene management
- Asset management
- Timeline management
- Event system
- Workflow coordination
- Module registration
- Core state management
- Internal consistency rules

Aurora Core must not depend on any specific AI provider.

Aurora Core must not contain GUI code.

Aurora Core must not contain vendor-specific generation logic.

Aurora Core must communicate with external systems only through plugins or SDK-defined interfaces.

---

## 7. Layer 3: Application Services

Application Services coordinate user actions and system workflows.

Responsibilities:

- Execute user commands
- Coordinate modules
- Dispatch events
- Validate workflow steps
- Connect UI intentions to domain behavior
- Manage use-case-level operations

Application Services may call Aurora Core, Domain Layer and Infrastructure through approved interfaces.

Application Services must not contain GUI rendering code.

Application Services must not contain provider-specific plugin logic.

---

## 8. Layer 4: Domain Layer

The Domain Layer contains the core business concepts of Aurora.

Examples:

- Project
- Film
- Scene
- Sequence
- Timeline
- Shot
- Asset
- Character
- Emotion
- Symbol
- Camera
- Composition
- Motion
- Transition
- Sound
- Prompt Export Intent

The Domain Layer defines meaning.

The Domain Layer must not contain GUI code.

The Domain Layer must not contain networking code.

The Domain Layer must not depend on plugins.

The Domain Layer must not depend on specific AI models.

---

## 9. Layer 5: Infrastructure

Infrastructure provides technical capabilities required by the product.

Responsibilities:

- Filesystem access
- Project storage
- Database access
- Logging
- Configuration
- Cache
- Import
- Export
- Local resource management
- Platform-specific adapters

Infrastructure must not contain business decisions.

Infrastructure must not define cinematic meaning.

Infrastructure must not control product workflow.

Infrastructure exists to support higher layers.

---

## 10. Layer 6: Plugins

Plugins provide external integrations and optional capabilities.

Examples:

- Video generation providers
- Image generation providers
- Text generation providers
- Local AI models
- Audio tools
- FFmpeg integration
- Speech tools
- Music tools
- Export targets
- Import formats

Plugins may extend Aurora.

Plugins must not modify Aurora Core.

Plugins must operate only through documented interfaces.

Plugins must declare:

- Plugin ID
- Version
- Author
- Capabilities
- Supported Aurora version
- Configuration schema
- Required permissions
- Offline/online behavior

Plugins must be replaceable.

---

## 11. Dependency Rules

Allowed dependency direction:

```text
Aurora Desktop
    → Aurora Core
    → Application Services
    → Domain Layer
    → Infrastructure
    → Plugins
```

Rules:

1. Dependencies must point downward.
2. Circular dependencies are forbidden.
3. Public APIs must be used for cross-layer communication.
4. Direct access to private internals is forbidden.
5. Vendor-specific logic must not enter Aurora Core.
6. GUI logic must not enter Domain Layer.
7. Infrastructure must not define business meaning.
8. Plugins must not modify Core internals.

---

## 12. Communication Rules

Modules may communicate through:

- Public APIs
- Events
- Command interfaces
- Query interfaces
- SDK-defined contracts

Modules must not communicate through:

- Hidden global state
- Private internal imports
- Direct mutation of unrelated module data
- Undocumented side effects
- Provider-specific shortcuts

---

## 13. Event System

Aurora must support an internal event system for major state changes.

Initial event examples:

- ProjectCreated
- ProjectOpened
- ProjectSaved
- ProjectClosed
- SceneCreated
- SceneUpdated
- SceneDeleted
- AssetImported
- AssetRemoved
- TimelineChanged
- ExportStarted
- ExportFinished
- PluginLoaded
- PluginUnloaded
- ErrorRaised

The exact event schema must be defined in a later interface specification.

This document only defines the architectural requirement for an event system.

---

## 14. Plugin Architecture

Plugins are external capability providers.

A plugin must not be required for Aurora Core to start.

A missing plugin must not corrupt a project.

A disabled plugin must not prevent access to non-plugin project data.

Plugin capabilities must be discoverable.

Plugin permissions must be explicit.

Plugin failures must be isolated.

---

## 15. Data Ownership

Every module owns its own data.

Cross-module data modification must happen only through public APIs or approved services.

No module may silently modify another module's internal data.

Project data must be inspectable and recoverable wherever technically possible.

Opaque binary-only formats should be avoided unless justified by an approved ADR.

---

## 16. Offline-First Architecture

Aurora must work offline whenever technically possible.

Local project creation, editing, saving and exporting of supported local formats must not require Internet access.

Cloud services are optional extensions.

Online AI providers are plugins, not core requirements.

A project must remain openable even when online providers are unavailable.

---

## 17. Security Boundaries

Aurora must define security boundaries for:

- Plugins
- Scripts
- AI agents
- Importers
- Exporters
- External executables
- Cloud providers

No extension may receive unrestricted access by default.

Sensitive operations must require explicit permission.

---

## 18. Error Handling

Errors must not crash Aurora whenever recovery is possible.

Recoverable errors must produce meaningful messages.

Critical failures must be logged.

Plugin failures must be isolated from Aurora Core where technically possible.

Project corruption must be prevented through safe write strategies and recovery mechanisms.

---

## 19. Logging

Aurora must log important system actions and errors.

Logs must help diagnose:

- Project loading issues
- Plugin loading issues
- Import/export failures
- Workflow failures
- Validation failures
- Performance problems

Logging must not expose private user content unless explicitly required and documented.

---

## 20. Threading and Responsiveness

Heavy operations must not block the user interface.

Examples of heavy operations:

- Video analysis
- Audio analysis
- AI generation requests
- Export jobs
- Large project loading
- Large asset import
- Plugin execution

Aurora Desktop must remain responsive during long-running operations.

The exact concurrency model must be defined in a later architecture or module specification.

---

## 21. Testing Expectations

Every module should have:

- Unit tests
- Integration tests where applicable
- Acceptance tests for user-facing behavior
- Regression tests for fixed defects

Architecture-sensitive behavior must be tested.

Plugin boundaries must be tested.

Project compatibility must be tested.

---

## 22. Future Extension Areas

The architecture must allow future support for:

- Cloud synchronization
- Collaboration
- Marketplace
- Distributed rendering
- Multi-GPU rendering
- Local AI models
- Remote AI providers
- AI agents
- Advanced timeline editing
- Professional export workflows

Future extensions must not require rewriting Aurora Core.

---

## 23. Non-Goals

This document does not define:

- Python package structure
- Class names
- GUI layout
- Database schema
- Plugin SDK details
- AFL schema
- Public API details
- Testing file names
- Build system configuration

Those topics must be defined in later specifications.

---

## 24. Acceptance Criteria

This architecture is acceptable when:

1. All major system layers are defined.
2. Each layer has clear responsibilities.
3. Dependency direction is explicit.
4. Plugin boundaries are explicit.
5. Offline-first behavior is stated.
6. Data ownership rules are stated.
7. Security boundaries are stated.
8. Testing expectations are stated.
9. Implementation details are not invented.
10. The document remains consistent with the Aurora Constitution.

---

## 25. Summary

Aurora Studio is a modular creative workflow platform built around stable architecture, structured cinematic intent and AI-provider independence.

Aurora Core owns product meaning.

Plugins provide external capabilities.

Prompts are outputs.

Aurora Film Language will become the internal representation of cinematic information.

Architecture stability has priority over implementation speed.

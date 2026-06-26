# Aurora Glossary

Document ID: PROD-000001  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 01-Product/GLOSSARY.md  
Document Type: Product Glossary  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 02-Architecture/ARCHITECTURE.md  

---

## 1. Purpose

This document defines the standard terminology used across Aurora Studio and the `aurora-spec` repository.

The glossary exists to prevent inconsistent meaning across specifications, architecture documents, AI tasks, module definitions, data models, APIs and future implementation code.

Every contributor and AI implementation agent must use these terms consistently.

If a term is not defined here and affects implementation, it must be added or clarified before implementation begins.

---

## 2. Authority

This glossary is subordinate to:

- 00-Governance/AURORA_CONSTITUTION.md
- 00-Governance/AURORA_ENGINEERING_STANDARD.md
- 02-Architecture/ARCHITECTURE.md

If this glossary conflicts with the Constitution, the Constitution takes precedence.

If this glossary conflicts with the Architecture document, the Architecture document takes precedence until the conflict is reviewed.

---

## 3. Usage Rules

Terms in this glossary must be used consistently across all Aurora documents.

A term must not be redefined locally unless the local document explicitly states a narrower meaning.

If a future specification introduces a new concept, that concept should be added to this glossary when it becomes reusable.

AI implementation agents must not invent alternate meanings for glossary terms.

---

## 4. Core Project Terms

| Term | Definition |
|---|---|
| Aurora | The overall product ecosystem for structured AI filmmaking workflows. |
| Aurora Studio | The future desktop application used by creators to design, manage, structure and export cinematic workflows for AI-assisted filmmaking. |
| Aurora Spec | The version-controlled specification knowledge base that defines Aurora product behavior, architecture, modules, interfaces, data models, AI tasks and standards. |
| `aurora-spec` | The repository containing Aurora specifications, governance documents, templates, ADRs, RFCs, tasks and related controlled documents. |
| `aurora-studio` | The future implementation repository containing application code for Aurora Studio. |
| `aurora-assets` | A future supporting repository or workspace for sample media, reference assets, test assets and non-code materials. |
| Creative Operating System | The long-term product vision for Aurora: a structured environment where creative intent is planned before AI generation begins. |
| AI Filmmaking | A filmmaking workflow where AI systems may assist with image generation, video generation, voice, sound, music, editing, analysis or automation. |
| Creative Intent | The human-defined artistic, emotional, narrative and cinematic goal that Aurora structures before generation. |
| Structured Cinematic Intent | Creative intent represented in a formal, reviewable and reusable structure rather than as free-form prompts only. |

---

## 5. Governance Terms

| Term | Definition |
|---|---|
| Aurora Constitution | The highest-authority governance document defining immutable engineering and product laws for Aurora. |
| AES | Aurora Engineering Standard. The governance document defining how specifications, tasks, reviews and AI implementation work must be structured. |
| Review Standard | The governance document defining how Aurora documents and AI outputs are reviewed before use or commit. |
| AI Implementation Protocol | The governance document defining how AI implementation agents must execute Aurora tasks. |
| Governance Document | A controlled document that defines rules, authority, standards or process for Aurora development. |
| Authority Order | The hierarchy used to resolve conflicts between Aurora documents. |
| Controlled Document | A versioned document with ID, status, owner, path, document type and dependencies. |
| Single Source of Truth | The authoritative source that implementation must follow. For product definition, this is `aurora-spec`. |
| Constitution Conflict | Any contradiction between a document, task, code change or AI output and the Aurora Constitution. |
| Scope Creep | Unauthorized expansion of work beyond the approved task or specification. |

---

## 6. Document and Process Terms

| Term | Definition |
|---|---|
| Specification | A controlled document that defines required behavior, responsibility, data, interfaces, workflows or constraints before implementation. |
| Task | A small, scoped, reviewable unit of work assigned to a human or AI implementation agent. |
| ADR | Architecture Decision Record. A controlled document recording a significant architectural decision. |
| RFC | Request for Comments. A controlled proposal used before a major idea becomes an ADR, specification or task. |
| Template | A reusable document structure used to create consistent tasks, specifications, ADRs or RFCs. |
| Review | The process of checking whether a document or output is scoped, valid, consistent and ready. |
| Acceptance Criteria | Conditions that must be satisfied before a document, task or implementation is accepted. |
| Preconditions | Required files, documents or conditions that must exist before a task may begin. |
| Strict Scope | The exact boundary of files and actions allowed in a task. |
| Forbidden Actions | Actions explicitly prohibited within a task. |
| Expected Report | The factual report an AI implementation agent must return after completing or stopping a task. |
| Implementation Readiness | The state in which a specification has enough approved information for implementation to begin. |
| Change Control | The process used to track, review and approve significant changes to controlled documents or architecture. |

---

## 7. Architecture Terms

| Term | Definition |
|---|---|
| Aurora Desktop | The user interface layer of Aurora Studio. It handles windows, menus, dialogs, timeline panels and visual interaction. |
| Aurora Core | The central product layer responsible for project lifecycle, scenes, assets, timeline, events, workflow coordination and internal consistency. |
| Application Services | The layer that coordinates user actions and system workflows between UI, core, domain and infrastructure. |
| Domain Layer | The layer containing core business and cinematic concepts such as Project, Scene, Timeline, Character, Emotion and Camera. |
| Infrastructure | The layer providing technical capabilities such as filesystem access, storage, logging, configuration, cache, import and export. |
| Plugin | An external capability provider that extends Aurora through documented interfaces without modifying Aurora Core. |
| SDK | Software Development Kit. The public set of interfaces and tools that future plugins or integrations use to interact with Aurora. |
| Public API | A documented interface exposed by a module, SDK, plugin boundary or service. |
| Private Internal | Implementation detail that must not be accessed directly by other modules. |
| Dependency Direction | The allowed direction in which one layer or module may depend on another. |
| Circular Dependency | A dependency loop between modules or layers. Circular dependencies are forbidden. |
| Event System | The internal mechanism used to communicate major state changes such as ProjectOpened, SceneCreated or ExportFinished. |
| Module | A bounded subsystem with one clear responsibility. |
| Interface | A documented contract through which modules, plugins or services communicate. |
| Data Ownership | The rule that each module owns its own data and other modules may modify it only through approved interfaces. |

---

## 8. Product and Workflow Terms

| Term | Definition |
|---|---|
| Project | The top-level creative workspace containing all structured information for a film or AI filmmaking workflow. |
| Film | The conceptual creative work being developed inside Aurora. |
| Sequence | A larger narrative or timeline segment containing one or more scenes or shots. |
| Scene | A meaningful dramatic, visual or narrative unit within a film. |
| Shot | A smaller cinematic unit within a scene, usually representing one camera perspective or generated video segment. |
| Timeline | The structured ordering of scenes, shots, assets, events, sounds and transitions over time. |
| Asset | Any reusable creative material used by a project, including images, video, audio, scripts, references, prompts, characters or generated media. |
| Character | A named or structured participant in the cinematic workflow, story or scene. |
| Location | A physical, fictional or conceptual place where a scene or shot occurs. |
| Scene Manager | The future module responsible for creating, organizing and managing scenes. |
| Timeline Manager | The future module responsible for time-based ordering and relationships. |
| Asset Manager | The future module responsible for importing, organizing, referencing and managing assets. |
| Project Manager | The future module responsible for project creation, opening, saving, closing and lifecycle rules. |
| Workflow | A structured sequence of actions that transforms creative intent into reviewable outputs. |
| Export | The process of converting Aurora internal structures into an external format such as prompts, JSON, video generation requests or files. |
| Import | The process of bringing external material into Aurora in a controlled way. |

---

## 9. Cinematic Language Terms

| Term | Definition |
|---|---|
| AFL | Aurora Film Language. The future internal representation of cinematic meaning in Aurora. |
| Aurora Film Language | The structured internal language used to represent scenes, shots, camera, emotion, symbolism, motion, rhythm and cinematic meaning. |
| Prompt | Text output generated from internal Aurora structures for use in an AI system. A prompt is an export format, not the internal source of truth. |
| Prompt Export Intent | The structured intent that guides how Aurora exports internal cinematic meaning into prompt text for a specific model or provider. |
| Emotion | A structured representation of emotional state, tone or transformation within a scene, shot, character or sequence. |
| Symbol | A recurring or meaningful visual, narrative or emotional object used in cinematic design. |
| Camera | The structured representation of camera behavior, framing, lens style, angle or movement. |
| Composition | The visual arrangement of subjects, objects, space, depth and attention within a frame. |
| Motion | The representation of movement within a shot, including subject movement, camera movement or environmental movement. |
| Transition | The cinematic relationship or bridge between shots, scenes or sequences. |
| Visual Meaning | The intended interpretation carried by visual elements, composition, symbolism, movement, lighting or cinematic structure. |
| Rhythm | The pacing, repetition, timing or emotional cadence of a cinematic sequence. |
| Tone | The overall emotional and stylistic atmosphere of a scene, sequence or film. |
| Style | A structured description of visual, sonic or narrative treatment. |
| Reference | A source image, video, audio, text or concept used to guide creative direction. |

---

## 10. AI and Plugin Terms

| Term | Definition |
|---|---|
| AI Provider | An external or local AI system that performs generation, analysis, transformation or assistance. |
| AI Model | A specific machine learning model used by an AI provider or local system. |
| AI Agent | A system that can execute tasks, modify files, generate code, review content or assist in development. |
| AI Implementation Agent | An AI agent assigned to execute Aurora tasks under strict scope and protocol. |
| Adapter | A component that translates Aurora internal structures into a provider-specific interface or request format. |
| Provider Plugin | A plugin that connects Aurora to a specific AI provider or model family. |
| Local Model | An AI model running on the user's machine or local infrastructure. |
| Online Provider | A cloud or remote AI service that requires network access. |
| Capability | A declared function of a plugin, such as image generation, video generation, audio analysis or prompt export. |
| Permission | Explicit access granted to a plugin or agent, such as file access, network access or project access. |
| Plugin Boundary | The controlled interface between Aurora Core and plugins. |
| Vendor Lock-In | A dependency on one provider or technology that prevents replacement or long-term flexibility. |

---

## 11. Data and Storage Terms

| Term | Definition |
|---|---|
| Project Data | Structured information stored by an Aurora project. |
| Metadata | Data describing project content, structure, state, assets, versions or relationships. |
| Schema | A formal structure defining fields, types and relationships for data. |
| Migration | A controlled change from one data structure or version to another. |
| Compatibility | The ability of Aurora to preserve behavior, data access or public contracts across versions. |
| Backward Compatibility | The ability of a newer Aurora version to open or understand older project data or interfaces. |
| Forward Compatibility | The ability of older systems to tolerate or safely ignore newer data where possible. |
| Opaque Format | A format that cannot be easily inspected or recovered by humans or tools. |
| Recoverability | The ability to restore or reconstruct project data after failure, corruption or accidental change. |
| Version History | The preserved record of changes over time. |

---

## 12. Quality Terms

| Term | Definition |
|---|---|
| Deterministic | Producing predictable behavior from the same inputs and specification. |
| Reviewable | Clear enough that a human or AI reviewer can inspect correctness and scope. |
| Reversible | Able to be undone, reverted or recovered without unacceptable damage. |
| Testable | Defined clearly enough that expected behavior can be verified. |
| Maintainable | Structured so that future changes remain understandable and controlled. |
| Extensible | Designed so new capabilities can be added without rewriting core systems. |
| Modular | Divided into independent components with clear responsibilities. |
| Offline-First | Designed to function without Internet access whenever technically possible. |
| Cross-Platform | Designed to work on more than one operating system where technically possible. |
| Performance | The responsiveness, speed and resource behavior of the system. |
| Reliability | The ability to behave correctly and recover from expected failures. |
| Security Boundary | A defined limit controlling what a plugin, script, AI agent or external tool may access. |

---

## 13. Ambiguous Terms To Avoid

The following terms must not be used as implementation requirements unless further defined:

| Ambiguous Term | Required Clarification |
|---|---|
| Smart | Define exact behavior. |
| Automatic | Define trigger, input, output and override behavior. |
| Advanced | Define capabilities. |
| Professional | Define measurable or observable qualities. |
| High quality | Define acceptance criteria. |
| Fast | Define performance target or expectation. |
| Better | Define comparison target. |
| Similar | Define similarity dimension and threshold. |
| Creative | Define allowed transformation or suggestion behavior. |
| Optimized | Define optimization goal and constraint. |

AI implementation agents must not implement ambiguous terms without clarification.

---

## 14. Term Change Rules

A glossary term may be changed only when:

1. The reason for change is documented.
2. Affected documents are identified.
3. Compatibility impact is considered.
4. The version is updated.
5. Review is performed.

Terms that affect architecture, public APIs or data models may require an ADR.

---

## 15. Acceptance Criteria

This glossary is acceptable when:

1. Core project terms are defined.
2. Governance terms are defined.
3. Architecture terms are defined.
4. Product and workflow terms are defined.
5. Cinematic language terms are defined.
6. AI and plugin terms are defined.
7. Data and storage terms are defined.
8. Quality terms are defined.
9. Ambiguous terms to avoid are listed.
10. The glossary is consistent with the Aurora Constitution.
11. The glossary is consistent with AES.
12. The glossary is consistent with the Architecture document.

---

## 16. Summary

The Aurora Glossary establishes shared meaning.

Shared meaning is required before reliable specifications, AI tasks and implementation can exist.

Without a glossary, Aurora would slowly split into inconsistent interpretations.

The glossary prevents that drift.

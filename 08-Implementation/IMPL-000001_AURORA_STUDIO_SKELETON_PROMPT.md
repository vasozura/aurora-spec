# Aurora Studio Skeleton Prompt

Document ID: IMPL-000001  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 08-Implementation/IMPL-000001_AURORA_STUDIO_SKELETON_PROMPT.md  
Document Type: Controlled Implementation Prompt  
Depends On: AURORA_CONSTITUTION.md, AURORA_ENGINEERING_STANDARD.md, AI_IMPLEMENTATION_PROTOCOL.md, REVIEW_STANDARD.md, ARCHITECTURE.md, ROADMAP.md, AFL-000001 through AFL-000010, MOD-000001 through MOD-000010, API-000001 through API-000005, DATA-000001, TEST-000001 through TEST-000005  

---

## 1. Purpose

This document defines the first controlled implementation prompt for Aurora Studio.

This prompt is intended for a future Claude/Codex execution step.

This prompt should be used only after the specification repository has the governance, architecture, AFL, module, interface, data and testing foundation documents in place.

This prompt does not implement Aurora Studio by itself.

This prompt defines the first implementation skeleton task.

---

## 2. Target Implementation Repository

The implementation repository should be separate from the specification repository.

Recommended implementation repository name:

```text
aurora-studio
```

The specification repository remains:

```text
aurora-spec
```

The implementation repository must treat `aurora-spec` as the source of truth for requirements.

---

## 3. Implementation Goal

Create the first minimal Aurora Studio code skeleton.

The goal is not to implement product features.

The goal is to create a clean, testable, offline-first, provider-independent application structure that can receive future implementation tasks safely.

The skeleton must establish:

- Package structure
- Module boundaries
- Basic command/query/event placeholders
- Basic data contract placeholders
- Basic validation placeholders
- Basic test structure
- Basic documentation references
- No provider integrations
- No GUI
- No database
- No plugin execution
- No AI generation
- No prompt export implementation

---

## 4. Recommended Initial Stack

Use a minimal Python implementation skeleton.

Recommended baseline:

```text
Python 3.11+
Standard library only for runtime skeleton
unittest for tests
```

Do not add external runtime dependencies.

Do not add web frameworks.

Do not add GUI frameworks.

Do not add AI SDKs.

Do not add database packages.

Do not add plugin frameworks.

Do not add provider SDKs.

A future ADR may change the implementation stack.

This first skeleton must remain simple.

---

## 5. Active Implementation Task Prompt

Use the following prompt for the first controlled code task.

---

# IMPLEMENTATION TASK: Create Aurora Studio Minimal Skeleton

Task ID: IMPLEMENTATION-000001  
Version: 0.1.0  
Status: Ready For Controlled Execution  
Target Repository: aurora-studio  
Task Type: Code Skeleton Creation  
Source Specification Repository: aurora-spec  
Required Specification Inputs:  
- 00-Governance/AURORA_CONSTITUTION.md  
- 00-Governance/AURORA_ENGINEERING_STANDARD.md  
- 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md  
- 00-Governance/REVIEW_STANDARD.md  
- 02-Architecture/ARCHITECTURE.md  
- 03-Modules/MOD-000001_PROJECT_MANAGER_SPEC.md  
- 03-Modules/MOD-000002_WORKSPACE_SPEC.md  
- 03-Modules/MOD-000003_SCENE_MANAGER_SPEC.md  
- 03-Modules/MOD-000004_SHOT_MANAGER_SPEC.md  
- 03-Modules/MOD-000005_TIMELINE_MANAGER_SPEC.md  
- 03-Modules/MOD-000006_ASSET_MANAGER_SPEC.md  
- 03-Modules/MOD-000007_CHARACTER_MANAGER_SPEC.md  
- 03-Modules/MOD-000008_AFL_ENGINE_SPEC.md  
- 03-Modules/MOD-000009_PROMPT_EXPORT_MANAGER_SPEC.md  
- 03-Modules/MOD-000010_PLUGIN_MANAGER_SPEC.md  
- 04-Interfaces/API-000001_CORE_INTERFACE_PRINCIPLES.md  
- 04-Interfaces/API-000002_PROJECT_WORKSPACE_INTERFACES.md  
- 04-Interfaces/API-000003_SCENE_SHOT_INTERFACES.md  
- 04-Interfaces/API-000004_ASSET_CHARACTER_INTERFACES.md  
- 04-Interfaces/API-000005_AFL_PROMPT_PLUGIN_INTERFACES.md  
- 05-Data/DATA-000001_CORE_DATA_CONTRACTS.md  
- 07-Testing/TEST-000001_AURORA_TEST_STRATEGY.md  
- 07-Testing/TEST-000004_IMPLEMENTATION_TEST_BOUNDARIES.md  
- 07-Testing/TEST-000005_AI_AGENT_ACCEPTANCE_CHECKLIST.md  

---

## 5.1 Objective

Create the minimal implementation skeleton for Aurora Studio.

This task must create structure only.

It must not implement product behavior.

It must not implement GUI.

It must not implement database persistence.

It must not implement AI provider integration.

It must not implement prompt export.

It must not implement plugin execution.

The skeleton must be importable and testable.

---

## 5.2 Allowed Files To Create

Create only the following files and directories:

```text
README.md
pyproject.toml
src/aurora_studio/__init__.py
src/aurora_studio/core/__init__.py
src/aurora_studio/core/errors.py
src/aurora_studio/core/result.py
src/aurora_studio/core/events.py
src/aurora_studio/core/ids.py
src/aurora_studio/core/readiness.py
src/aurora_studio/modules/__init__.py
src/aurora_studio/modules/project_manager.py
src/aurora_studio/modules/workspace.py
src/aurora_studio/modules/scene_manager.py
src/aurora_studio/modules/shot_manager.py
src/aurora_studio/modules/timeline_manager.py
src/aurora_studio/modules/asset_manager.py
src/aurora_studio/modules/character_manager.py
src/aurora_studio/modules/afl_engine.py
src/aurora_studio/modules/prompt_export_manager.py
src/aurora_studio/modules/plugin_manager.py
src/aurora_studio/contracts/__init__.py
src/aurora_studio/contracts/project.py
src/aurora_studio/contracts/workspace.py
src/aurora_studio/contracts/scene.py
src/aurora_studio/contracts/shot.py
src/aurora_studio/contracts/asset.py
src/aurora_studio/contracts/character.py
src/aurora_studio/contracts/afl.py
src/aurora_studio/contracts/export.py
src/aurora_studio/contracts/plugin.py
src/aurora_studio/contracts/validation.py
tests/__init__.py
tests/test_imports.py
tests/test_module_boundaries.py
tests/test_offline_skeleton.py
```

Do not create any other files.

If a tool requires temporary files, do not commit them.

---

## 5.3 Required Structure

The package must use this top-level import:

```python
import aurora_studio
```

The skeleton must define module classes or placeholders for:

- ProjectManager
- Workspace
- SceneManager
- ShotManager
- TimelineManager
- AssetManager
- CharacterManager
- AFLEngine
- PromptExportManager
- PluginManager

These classes must be minimal.

They must not implement product behavior beyond identity, readiness reporting and basic placeholder methods that raise explicit `NotImplementedError` or return controlled readiness values.

---

## 5.4 Required Core Utilities

Create minimal core utilities:

### errors.py

Define controlled base errors:

- AuroraError
- ValidationError
- OwnershipError
- UnsupportedOperationError
- NotReadyError

### result.py

Define a minimal result object or dataclass:

- success
- message
- data
- errors

Do not create complex framework behavior.

### events.py

Define a minimal event dataclass:

- event_type
- source
- payload
- occurred_at

Do not implement event bus behavior.

### ids.py

Define simple ID helper functions.

IDs must not depend on provider output or prompt text.

### readiness.py

Define readiness states:

- Not Ready
- Ready For Design
- Ready For Implementation
- Deprecated

Use constants or an enum.

---

## 5.5 Required Contract Placeholders

Each contract file must define lightweight dataclasses or placeholders that reflect conceptual ownership only.

Do not define final schemas.

Do not define persistence rules.

Do not define migrations.

Required placeholder concepts:

| File | Required Placeholder |
|---|---|
| project.py | ProjectRef or ProjectMetadata |
| workspace.py | WorkspaceState |
| scene.py | SceneRef |
| shot.py | ShotRef |
| asset.py | AssetRef |
| character.py | CharacterRef |
| afl.py | AFLValidationReport |
| export.py | ExportArtifactRef |
| plugin.py | PluginMetadata |
| validation.py | ValidationIssue and ValidationReport |

These must be clearly marked as placeholder contracts.

---

## 5.6 Required Module Placeholder Behavior

Each module class must expose:

```python
module_name
readiness
get_readiness()
```

`readiness` must default to:

```text
Not Ready
```

Modules must not perform real operations.

If placeholder command methods are included, they must not mutate real project data.

They may raise `NotImplementedError` with clear messages.

---

## 5.7 README Requirements

`README.md` must state:

- This is the Aurora Studio implementation repository.
- `aurora-spec` is the source of truth.
- This skeleton is not feature-complete.
- No AI provider integration exists yet.
- No GUI exists yet.
- No database exists yet.
- No plugin execution exists yet.
- Runtime skeleton uses Python standard library only.
- How to run tests with standard library `unittest`.

Example command:

```bash
python -m unittest
```

---

## 5.8 pyproject.toml Requirements

Create a minimal `pyproject.toml`.

It must include:

- Project name: `aurora-studio`
- Python requirement: `>=3.11`
- No runtime dependencies
- Basic package discovery using `src` layout if applicable

Do not add external dependencies.

---

## 5.9 Required Tests

Create minimal tests using Python standard library `unittest`.

Tests must verify:

1. `aurora_studio` imports successfully.
2. All module classes import successfully.
3. All module classes report readiness as `Not Ready`.
4. Contract placeholder classes import successfully.
5. No online provider dependency is required.
6. No GUI dependency is required.
7. No database dependency is required.

Tests must not require Internet access.

Tests must not call providers.

Tests must not use external packages.

---

## 5.10 Forbidden Actions

Do not:

- Implement real project persistence.
- Implement Scene creation.
- Implement Shot creation.
- Implement timeline editing.
- Implement asset import.
- Implement character management.
- Implement AFL validation logic.
- Implement prompt export.
- Implement provider integration.
- Implement plugin loading.
- Implement GUI.
- Implement web server.
- Add FastAPI.
- Add Flask.
- Add Django.
- Add PySide.
- Add PyQt.
- Add Gradio.
- Add Streamlit.
- Add OpenAI SDK.
- Add video model SDKs.
- Add database dependencies.
- Add pytest.
- Add pydantic.
- Add numpy.
- Add any external dependency.
- Create files outside the allowed list.
- Modify specification repository files.
- Continue to the next task.

---

## 5.11 Validation Commands

After creating the skeleton, run:

```bash
python -m unittest
```

If the repository uses `src` layout and import path is not automatically available, use an approach that works locally without external dependencies.

Do not install external packages.

---

## 5.12 Expected Report

After completion, report only:

1. Created file list
2. Confirmation that no files outside allowed list were created
3. Confirmation that no external dependencies were added
4. Confirmation that no GUI/database/provider/plugin implementation was added
5. Test command executed
6. Test result
7. Any known limitations
8. Stop statement

Do not continue beyond IMPLEMENTATION-000001.

---

## 6. Review Checklist For This Prompt

Before using this prompt, verify:

- The specification repository has TASK-000001 through TASK-000021 complete.
- The implementation target repository is clean or intentionally prepared.
- The AI agent understands it is creating skeleton only.
- No feature implementation is expected.
- No external dependencies are allowed.
- The stop condition is clear.

---

## 7. Implementation Readiness

Implementation readiness:

```text
Ready For Controlled Execution
```

Reason:

This document does not implement Aurora Studio.

It defines a constrained first code skeleton prompt with strict file boundaries, no external dependencies and standard-library tests.

The prompt is suitable as the first implementation bridge after specification foundation review.

---

## 8. Acceptance Criteria

This document is acceptable when:

1. Target implementation repository is named.
2. Implementation goal is limited to skeleton creation.
3. Recommended stack is minimal and explicit.
4. Allowed files are explicit.
5. Required structure is explicit.
6. Required core utilities are listed.
7. Required contract placeholders are listed.
8. Required module placeholder behavior is listed.
9. README requirements are listed.
10. pyproject requirements are listed.
11. Required tests are listed.
12. Forbidden actions are explicit.
13. Validation command is defined.
14. Expected report is defined.
15. Stop condition is explicit.
16. Implementation readiness is marked Ready For Controlled Execution.

---

## 9. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

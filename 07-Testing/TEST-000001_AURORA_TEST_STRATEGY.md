# Aurora Test Strategy

Document ID: TEST-000001  
Version: 0.1.0  
Status: Draft  
Owner: Aurora Labs  
Repository: aurora-spec  
Path: 07-Testing/TEST-000001_AURORA_TEST_STRATEGY.md  
Document Type: Test Strategy Specification  
Depends On: 00-Governance/AURORA_CONSTITUTION.md, 00-Governance/AURORA_ENGINEERING_STANDARD.md, 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md, 00-Governance/REVIEW_STANDARD.md, 02-Architecture/ARCHITECTURE.md, 03-Modules/MOD-000001_PROJECT_MANAGER_SPEC.md through 03-Modules/MOD-000010_PLUGIN_MANAGER_SPEC.md, 04-Interfaces/API-000001_CORE_INTERFACE_PRINCIPLES.md through 04-Interfaces/API-000005_AFL_PROMPT_PLUGIN_INTERFACES.md, 05-Data/DATA-000001_CORE_DATA_CONTRACTS.md, 06-AI/AFL-000001_AURORA_FILM_LANGUAGE_OVERVIEW.md through 06-AI/AFL-000010_PROMPT_EXPORT_INTENT_SPEC.md  

---

## 1. Purpose

This document defines the first Aurora test strategy.

The purpose of testing in Aurora is not only to catch code bugs.

Testing must protect:

- User creative work
- Project integrity
- AFL meaning
- Module boundaries
- Data ownership
- Offline-first behavior
- Provider independence
- Plugin safety
- AI implementation discipline

Aurora must not move into implementation without a clear test strategy.

---

## 2. Authority

This document is subordinate to:

- 00-Governance/AURORA_CONSTITUTION.md
- 00-Governance/AURORA_ENGINEERING_STANDARD.md
- 00-Governance/AI_IMPLEMENTATION_PROTOCOL.md
- 00-Governance/REVIEW_STANDARD.md
- 02-Architecture/ARCHITECTURE.md

If this document conflicts with the Aurora Constitution, the Constitution takes precedence.

---

## 3. Scope

This strategy covers:

- Documentation review tests
- Specification validation tests
- Future implementation tests
- Interface tests
- Data contract tests
- AFL behavior tests
- Module boundary tests
- Offline-first tests
- Plugin boundary tests
- AI-agent execution checks
- Regression expectations

This document does not create executable tests.

---

## 4. Non-Scope

This document does not define:

- Test framework selection
- Python test files
- CI configuration
- Test runner commands
- Mock implementations
- Provider integration tests
- GUI automation tests
- Database migration tests
- Performance benchmark code

Those require later implementation-specific tasks.

---

## 5. Testing Principles

Aurora testing must follow these principles:

1. Source meaning must be protected.
2. Prompts are outputs, not source truth.
3. Module ownership must be enforced.
4. Queries must not mutate state.
5. Commands must validate inputs.
6. Events must describe completed facts.
7. Offline-first behavior must be tested.
8. Provider-specific logic must remain isolated.
9. Plugins must not bypass boundaries.
10. AI-generated code must be tested before acceptance.
11. Documentation must be reviewable before code.
12. No implementation should rely on undocumented behavior.

---

## 6. Test Levels

Aurora will use these conceptual test levels:

| Level | Purpose |
|---|---|
| Document Review Tests | Check whether specification documents are complete and consistent. |
| Specification Validation Tests | Check whether requirements, scope and acceptance criteria are internally coherent. |
| Unit Tests | Test isolated implementation units. |
| Contract Tests | Test module interfaces and data contracts. |
| Integration Tests | Test controlled module cooperation. |
| Regression Tests | Protect previously working behavior. |
| Offline Tests | Verify local work does not require online services. |
| Plugin Boundary Tests | Verify plugin permissions and isolation. |
| Export Tests | Verify export artifacts do not mutate AFL source meaning. |

---

## 7. Documentation Tests

Documentation tests must verify that a document:

- Has required metadata
- Has clear purpose
- Has scope and non-scope
- Has authority and dependencies
- Has acceptance criteria
- Has implementation readiness
- Does not authorize work outside its maturity
- Does not contradict governance
- Does not create hidden provider dependency
- Does not blur source meaning and export artifact

Documentation tests may be manual at first.

Later they may become automated lint or validation checks.

---

## 8. Specification Validation Tests

Specification validation must check:

- Requirements are testable
- Ownership boundaries are clear
- Dependencies do not create circular logic
- Forbidden actions are explicit in AI tasks
- Interface concepts match module responsibility
- Data ownership matches module ownership
- AFL source meaning remains provider-independent
- Implementation readiness is accurate
- Missing prerequisite documents are identified

---

## 9. Unit Test Expectations

Future implementation unit tests must verify behavior inside a single implementation unit.

Unit tests should be used for:

- ID generation behavior
- Validation functions
- Data transformation functions
- Interface command handlers
- Query handlers
- Error generation
- State transition rules
- Compatibility checks

Unit tests must not call online providers.

---

## 10. Contract Test Expectations

Contract tests must verify that module interfaces follow approved contracts.

Contract tests should verify:

- Commands validate input
- Commands change only owned state
- Queries are read-only
- Events are emitted only after completed state changes
- Errors are meaningful
- Ownership boundaries are enforced
- Data contracts are respected

Contract tests are required before module integration can be accepted.

---

## 11. Integration Test Expectations

Integration tests must verify controlled cooperation between modules.

Integration tests should cover:

- Project creation and workspace activation
- Scene creation and Shot creation
- Asset linking to Character
- Character reference validation
- AFL validation across Scene and Shot
- Prompt export preparation without provider call
- Plugin capability validation without unrestricted access

Integration tests must not rely on online services unless explicitly marked as provider integration tests.

---

## 12. Offline-First Test Expectations

Offline-first tests must verify:

- Project can be opened offline
- Project can be saved offline
- Workspace can be used offline
- Scene and Shot editing work offline
- AFL validation works offline
- Asset metadata is accessible offline when local
- Prompt export preparation can run offline when provider execution is not requested
- Online-only operations fail clearly when offline

Offline-first behavior is not optional.

---

## 13. Provider Independence Test Expectations

Provider independence tests must verify:

- AFL core fields do not contain provider-specific syntax
- Prompt export artifacts are separate from AFL source data
- Provider-specific behavior is isolated to plugins or adapters
- Changing export target does not rewrite Scene or Shot meaning
- Provider limitations do not corrupt source meaning

---

## 14. Plugin Boundary Test Expectations

Plugin boundary tests must verify:

- Plugins declare metadata
- Plugins declare capabilities
- Plugins declare permissions
- Plugins cannot access full project data by default
- Plugins receive minimum necessary data
- Plugin failure does not corrupt core project data
- Disabled plugins cannot execute operations
- Online provider plugins require explicit user-initiated or approved operation

---

## 15. Data Integrity Test Expectations

Data integrity tests must verify:

- Stable identity is preserved
- Version fields are respected
- Unsupported versions fail safely
- Source meaning is not replaced by export artifacts
- Validation reports are reviewable
- Errors report whether data changed
- Save/load preserves expected data
- Migration behavior is explicit when later implemented

---

## 16. AFL Test Expectations

AFL tests must verify:

- Scene meaning is preserved
- Shot meaning is preserved
- Emotion remains structured
- Camera remains structured
- Composition remains structured
- Symbols are not decoration when marked symbolic
- Motion is distinguishable from Camera Motion
- Transitions are relationships, not only effects
- Prompt Export Intent does not replace AFL
- AFL can be validated offline

---

## 17. AI-Agent Test Expectations

AI-agent-generated outputs must be checked for:

- Exact target file compliance
- No extra files
- No forbidden implementation
- No hidden dependency additions
- No modification of unrelated documents
- No skipped acceptance criteria
- No silent continuation into the next task
- Correct implementation readiness state
- Clear report after completion

AI agents must stop after the active task.

---

## 18. Regression Expectations

Every accepted implementation task must define what behavior must not regress.

Regression tests should protect:

- Project open/save
- Scene creation
- Shot creation
- Validation behavior
- Offline behavior
- Export artifact separation
- Plugin permission enforcement
- Data compatibility
- User creative data integrity

---

## 19. Test Evidence

Accepted implementation should produce evidence.

Evidence may include:

- Test command output
- Test report file
- Manual review checklist
- Validation log
- Summary of changed files
- Summary of passed and failed tests

The exact format must be defined in later implementation tasks.

---

## 20. Implementation Readiness

Implementation readiness:

```text
Not Ready
```

Reason:

This document defines the high-level test strategy only.

Executable tests require concrete implementation tasks, test framework decisions, data schemas and code structure.

---

## 21. Acceptance Criteria

This document is acceptable when:

1. Testing purpose is defined.
2. Testing principles are defined.
3. Test levels are defined.
4. Documentation tests are defined.
5. Specification validation tests are defined.
6. Unit test expectations are defined.
7. Contract test expectations are defined.
8. Integration test expectations are defined.
9. Offline-first test expectations are defined.
10. Provider independence test expectations are defined.
11. Plugin boundary test expectations are defined.
12. Data integrity test expectations are defined.
13. AFL test expectations are defined.
14. AI-agent test expectations are defined.
15. Regression expectations are defined.
16. Implementation readiness is explicitly marked Not Ready.

---

## 22. Change History

| Version | Date | Change | Author |
|---|---|---|---|
| 0.1.0 | 2026-06-27 | Initial draft | Aurora Labs |

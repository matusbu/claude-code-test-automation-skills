# Test Strategy — [Project Name]

## System Under Test Description

[Brief system description — architecture, services, communication patterns, key technologies]

---

## How the Levels Relate

```
Level 1 — Unit          → [Brief description, e.g., Fast, isolated logic]
Level 2 — Integration   → [Brief description, e.g., Real dependencies, framework context]
Level 3 — E2E           → [Brief description, e.g., Complete flows, live system]
```

---

## Level 1 — Unit Tests

**Purpose:** Verify isolated logic. All I/O and framework infrastructure replaced by mocks.

### Covers
- [Class/component and what's tested]
- [Class/component and what's tested]

### Excludes
- Real database
- Real network
- [Other infrastructure]

### Tooling
| Tool | Role |
|---|---|
| [Framework] | Test runner |
| [Mock library] | Mocking |
| [Assertion library] | Assertions |

---

## Level 2 — Integration Tests

**Purpose:** [Full context or key integrations] against real dependencies.

### Covers
- [Repository/data layer]
- [API layer]
- [Framework integration]

### Excludes
- [External services] — replaced by stubs
- [Specific flows not tested here]

### Tooling
| Tool | Role |
|---|---|
| [Framework] | Full context |
| [Container tech] | Real dependencies (requires Docker) |
| [Stub server] | External stubs |

---

## Level 3 — E2E Tests

**Purpose:** Verify complete business flows through live system.

### Design

[Describe the structural pattern for this level — e.g., Screenplay pattern (Serenity/J), Gherkin scenarios with Cucumber/SerenityBDD, or a custom actor/DSL approach. Explain how tests are organised and why this approach aids readability and maintenance.]

### Covers
- [Capability or business rule — describe scope broadly, not specific test cases, e.g., "Complete flows from entry point to any terminal state"]
- [Observable system behaviour — e.g., "Events/messages arrive in correct order for each flow"]

### Excludes
- Exhaustive edge cases — covered at Level 1
- Input validation — covered at Level 1 and 2

### Tooling
| Tool | Role |
|---|---|
| [Framework] | Test runner |
| [API client] | HTTP calls |
| [Environment] | Full stack |

---

## Level 4 — [Frontend / Contract / Performance Tests]

> **Note:** Add additional test levels as needed for your project (e.g., component tests, contract tests, visual regression, performance tests)

**Purpose:** [What this level verifies]

### Design

[Describe the structural pattern for this level — e.g., Page Object Model with Playwright (UI tests); load profile and virtual user model with k6 or Gatling (performance tests). Explain key design decisions that shape how tests at this level are written.]

### Covers
- [Capability or behaviour rule — e.g., "All supported component states render correctly" or "P99 latency stays under X ms at Y RPS"]
- [Another rule area]

### Excludes
- [What's not covered and why]

### Tooling
| Tool | Role |
|---|---|
| [Framework] | [Role] |
| [Library] | [Role] |

---

## Build / CI Organization

| Level | Tag | Command | When to Run |
|---|---|---|---|
| 1 — Unit | `@Tag("unit")` | `mvn test` | Every commit |
| 2 — Integration | `@Tag("integration")` | `mvn verify` | Every PR |
| 3 — E2E | `@Tag("e2e")` | `mvn verify -Pe2e` | Pre-merge/nightly |
| 4 — [Optional] | `[tag]` | `[command]` | `[when]` |

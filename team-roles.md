# Team Roles in BDR

BDR adoption involves multiple roles working together. This document defines the responsibilities of each role in the BDR ecosystem.

## Roles Overview

| Role | Primary Focus | Key Responsibilities |
|------|---------------|---------------------|
| **Automation QA (AQA)** | Technical Implementation | Layer 0, Layer 1, Infrastructure |
| **Manual QA / Business Analyst** | Business Logic | Layer 3, Report Validation |
| **Developer** | Feature Development | Layer 2, Layer 1, Maintenance |
| **Test Lead / Architect** | Standards & Strategy | Methodology Enforcement, Coaching |

---

## Automation QA (AQA)

The technical backbone of BDR implementation.

### Responsibilities

- **Implement Layer 0 and Layer 1** — Technical implementation: Page Objects, API clients, database connectors.
- **Maintain test frameworks and infrastructure** — Parallel execution, CI integration, test environments.
- **Ensure test stability and performance** — Anti-flakiness strategies, debugging, optimization.
- **Create reusable Flows** — Atomic interactions that can be composed into Domain actions.

### Key Artifacts

| Layer | Artifact Type | Examples |
|-------|---------------|----------|
| Layer 0 | Page Objects, API Clients | `LoginPage`, `CartAPI` (file extensions depend on the stack) |
| Layer 1 | Flows | `LoginFlow`, `CartFlow` (file extensions depend on the stack) |

---

## Manual QA / Business Analyst

The bridge between business requirements and test specifications.

### Responsibilities

- **Define Layer 3 scenarios** — Write test scenarios in pure business language.
- **Collaborate with developers** — Define Layer 2 domain actions that reflect business intent.
- **Review Allure reports** — Validate that test results match business expectations.
- **Maintain traceability** — Ensure test coverage maps to user stories and acceptance criteria.

### Key Artifacts

| Layer | Artifact Type | Examples |
|-------|---------------|----------|
| Layer 3 | Scenarios | `checkout_happy_path`, `auth_login` (file extensions depend on the stack) |
| Layer 2 | Domain Classes | `Customer`, `Admin` (implemented in the chosen programming language) |

---

## Developer

Contributor to test code as part of feature development.

### Responsibilities

- **Contribute to Layer 2 and Layer 1** — Implement domain actions and flows as part of feature work.
- **Maintain test code alongside production code** — Shared repositories, co-located test files.
- **Use BDR reports for regression detection** — Catch broken business logic during refactoring.
- **Write tests for new features** — Follow BDR patterns from the start.

### Key Artifacts

| Layer | Artifact Type | Examples |
|-------|---------------|----------|
| Layer 2 | Domain Actions | `Customer.addItemToCart()` |
| Layer 1 | Flows | `CartFlow.confirmAddition()` |

---

## Test Lead / Architect

The guardian of BDR standards and continuous improvement.

### Responsibilities

- **Define and enforce BDR standards** — Code review guidelines, naming conventions, layer boundaries.
- **Coach team members** — Training sessions, pair programming, documentation.
- **Drive continuous improvement** — Analyze flakiness trends, optimize execution time, improve reporting.
- **Align methodology across teams** — Cross-team consistency, shared patterns, knowledge sharing.

### Key Artifacts

| Type | Examples |
|------|----------|
| Standards | `CONTRIBUTING.md`, Code review checklists |
| Metrics | Flakiness reports, Coverage dashboards |

---

## Collaboration Matrix

| Task | AQA | Manual QA | Developer | Lead |
|------|-----|-----------|-----------|------|
| Write Layer 3 Scenarios | ✓ | ✓✓✓ | ✓ | ✓ |
| Implement Layer 2 | ✓ | | ✓✓✓ | ✓ |
| Implement Layer 1 | ✓✓✓ | | ✓✓ | |
| Implement Layer 0 | ✓✓✓ | | ✓ | |
| Review Reports | ✓✓ | ✓✓✓ | ✓ | ✓✓ |
| Maintain Infrastructure | ✓✓✓ | | ✓ | ✓ |

*Legend: ✓✓✓ = Primary owner, ✓✓ = Regular contributor, ✓ = Occasional contributor*

---

*This role structure ensures clear ownership while promoting collaboration across the team.*

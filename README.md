# BDR Methodology: Behavior-Driven Living Requirements

> **The Universal Standard for Scalable Test Automation.**

[![TypeScript Implementation](https://img.shields.io/badge/Reference_Implementation-Playwright%2FTS-blue)](https://github.com/dmitryAQA/playwright-bdr-template)
[![Community](https://img.shields.io/badge/Community-Discussion-orange)](https://github.com/dmitryAQA/bdr-methodology/discussions)

## Table of Contents

- [The Manifesto](#the-manifesto)
- [Core Principles](#core-principles)
- [Documentation](#documentation)
- [Reference Implementations](#reference-implementations)
- [Contributing](#contributing)

## The Manifesto

We are building a methodology that transforms test automation from a "maintenance burden" into the **Single Source of Truth** about the product.

Based on our experience with 1000+ tests, we value:

1.  **Living Requirements** over Stale Documentation.
2.  **Behavioral Code** over Tool-Specific Scripts.
3.  **Infinite Reproducibility** over Infinite Retries.
4.  **Business Transparency** over Technical Black Boxes.

That is, while there is value in the items on the right, we value the items on the left more.

## Core Principles

### ✅ We Do:
- **Write tests in Business Language.** The Scenario Layer must read like a User Story.
- **Invest in Reporting.** The report is not just a log; it is a legal document of feature delivery.
- **Separate Concerns.** Technical details (selectors, API) live in a separate layer from Business Logic.
- **Strive for Zero Frustration.** Every failure must immediately answer "What?", "Where?", and "Why?".

### ❌ We Don't:
- **Write tests "for the tool".** If we switch from Playwright to Selenium, the Specification Layer should not change.
- **Ignore "Noise".** Flakiness is a violation of "Infinite Reproducibility".
- **Hoard "Secret Knowledge".** We make results accessible to Managers, Analysts, and Designers.

## Documentation

### Core Concepts
- **[4-Layer Architecture](architecture.md)**: The structural standard for BDR projects.
- **[Universal Pseudo-code](universal-pseudo-code.md)**: Framework-agnostic language for BDR specifications.
- **[Workflow](workflow.md)**: From Jira Ticket to BDR Spec.
- **[Ecosystem Mapping](ecosystem-mapping.md)**: How BDR maps to different languages and frameworks.

### Guides
- **[Anti-Flakiness Guide](guides/anti-flakiness.md)**: Strategies for stability.
- **[Scaling Patterns](guides/scaling-patterns.md)**: How to handle 1000+ tests.
- **[Folder Structure](guides/folder-structure.md)**: Project organization conventions.
- **[Data Management](guides/data-management.md)**: Test data strategies.
- **[Diagnostic Integrity](guides/diagnostic-integrity.md)**: Rich debugging in reports.
- **[Migration Guide](guides/migration-guide.md)**: How to port legacy projects.

### Reference
- **[Team Roles](team-roles.md)**: Responsibilities in BDR adoption.
- **[FAQ](faq.md)**: Frequently asked questions.

## Reference Implementations

The methodology is abstract, but here are the concrete implementations:

| Language | Framework | Repository | Status |
| :--- | :--- | :--- | :--- |
| **TypeScript** | Playwright | [**playwright-bdr-template**](https://github.com/dmitryAQA/playwright-bdr-template) | ✅ **Official Standard** |

_Contributions for other languages are warmly welcomed! See [CONTRIBUTING.md](CONTRIBUTING.md)._

## Contributing

BDR is an open standard. We welcome:
- New implementation examples (Java, C#, Go).
- Translations of the Manifesto.
- Case studies of BDR adoption.

See [CONTRIBUTING.md](CONTRIBUTING.md) for details.

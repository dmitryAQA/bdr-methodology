# BDR Methodology: Behavior-Driven Living Requirements

[View Website](https://dmitryAQA.github.io/bdr-methodology/)

> **BDD without the Cucumber overhead. Given/When/Then — straight in code.**

[![TypeScript Implementation](https://img.shields.io/badge/Reference_Implementation-Playwright%2FTS-blue)](https://github.com/dmitryAQA/playwright-bdr-template)
[![Community](https://img.shields.io/badge/Community-Discussion-orange)](https://github.com/dmitryAQA/bdr-methodology/discussions)

---

## About the Author

I'm Dmitry, a QA Automation Engineer. I got tired of watching teams spend more time maintaining `.feature` files than actually testing their product — so I designed a simpler approach.

BDR keeps everything that's good about BDD (Given/When/Then, business-readable scenarios, living documentation) and removes the part that slows you down (Cucumber, Gherkin, step definition hunting).

**I'm currently open to QA Automation roles — remote, contract, or full-time.**
[dmitryAQA@outlook.com](mailto:dmitryAQA@outlook.com)
Telegram: [@DmitryMeAQA](https://t.me/DmitryMeAQA)

---

## Table of Contents

- [The Manifesto](#the-manifesto)
- [Core Principles](#core-principles)
- [Documentation](#documentation)
- [Reference Implementations](#reference-implementations)
- [Contributing](#contributing)

---

## The Manifesto

BDR transforms test automation from a "maintenance burden" into the **Single Source of Truth** about the product.

I value:

1. **Living Requirements** over Stale Documentation.
2. **Behavioral Code** over Tool-Specific Scripts.
3. **Infinite Reproducibility** over Infinite Retries.
4. **Business Transparency** over Technical Black Boxes.

That is, while there is value in the items on the right, I value the items on the left more.

---

## Core Principles

### I Do:

- **Write tests in Business Language.** The Scenario Layer must read like a User Story.
- **Invest in Reporting.** The report is not just a log; it is a legal document of feature delivery.
- **Separate Concerns.** Technical details (selectors, API calls) live in a separate layer from Business Logic.
- **Strive for Zero Frustration.** Every failure must immediately answer "What?", "Where?", and "Why?".

### I Don't:

- **Write tests "for the tool".** If I switch from Playwright to Selenium, the Specification Layer should not change.
- **Ignore "Noise".** Flakiness is a violation of "Infinite Reproducibility".
- **Hoard "Secret Knowledge".** Results must be accessible to Managers, Analysts, and Designers — not just engineers.

---

## Why Not Just Use Cucumber?

Cucumber is a great idea wrapped in a painful implementation. The moment your team grows, you start paying the Gherkin tax:

- A developer renames a button → 30 step definitions break
- Business writes a scenario → engineer spends an hour wiring it up
- Test fails → you hunt across `.feature` files to understand what happened

BDR gives you the same Given/When/Then structure, the same readable scenarios, the same living documentation — but written directly in TypeScript (or your language of choice). Your IDE understands it. Refactoring works. Reports are rich.

---

## Documentation

### Core Concepts

- **[4-Layer Architecture](./architecture.md)**: The structural standard for BDR projects.
- **[Universal Pseudo-code](./universal-pseudo-code.md)**: Framework-agnostic language for BDR specifications.
- **[Workflow](./workflow.md)**: From Jira Ticket to BDR Spec.
- **[Ecosystem Mapping](./ecosystem-mapping.md)**: How BDR maps to different languages and frameworks.

### Guides

- **[Anti-Flakiness Guide](./guides/anti-flakiness.md)**: Strategies for stability.
- **[Scaling Patterns](./guides/scaling-patterns.md)**: How to handle growing test suites.
- **[Folder Structure](./guides/folder-structure.md)**: Project organization conventions.
- **[Data Management](./guides/data-management.md)**: Test data strategies.
- **[Diagnostic Integrity](./guides/diagnostic-integrity.md)**: Rich debugging in reports.
- **[Migration Guide](./guides/migration-guide.md)**: How to port legacy projects.

### Reference

- **[Team Roles](./team-roles.md)**: Responsibilities in BDR adoption.
- **[FAQ](./faq.md)**: Frequently asked questions.

---

## Reference Implementations

| Language       | Framework  | Repository                                                                          | Status       |
| -------------- | ---------- | ----------------------------------------------------------------------------------- | ------------ |
| **TypeScript** | Playwright | [**playwright-bdr-template**](https://github.com/dmitryAQA/playwright-bdr-template) | **Official** |

_Contributions for other languages are warmly welcomed! See [CONTRIBUTING.md](./CONTRIBUTING.md)._

---

## Contributing

BDR is an open standard. Contributions welcome:

- New implementations (Java, C#, Python, Go)
- Translations of the Manifesto
- Case studies of BDR adoption

See [CONTRIBUTING.md](./CONTRIBUTING.md) for details.

# Contributing to BDR

Thank you for your interest in contributing to the Behavior-Driven Living Requirements (BDR) Methodology! BDR is an open standard, and we rely on the community to adapt it to new languages and frameworks.

## How can I contribute?

### 1. New Implementations (Java, Python, C#, etc.)
We need reference repositories for other languages! If you have built a BDR-compliant framework in a language other than TypeScript, please:
1. Create a public repository (e.g., `python-bdr-template`).
2. Ensure it follows the [4-Layer Architecture](architecture.md).
3. Submit a Pull Request to update the `README.md` in this repository, adding your link to the "Reference Implementations" table.

### 2. Translations
BDR is global. If you want to translate the Manifesto or Guides into your native language:
1. Create a folder `i18n/<language-code>/` (e.g., `i18n/ru/`).
2. Copy the markdown files and translate them.
3. specific technical terms like "Flow", "Spec", "Layer" should generally remain in English or have the English term in parentheses.

### 3. Improvements to the Standard
If you find a gap in the methodology (e.g., "How to handle mobile gestures?", "How to do visual regression?"):
1. Open a **Discussion** first.
2. Propose a new Guide (e.g., `guides/visual-testing.md`).
3. Once approved, submit a PR.

## Code of Conduct

This project adheres to the Contributor Covenant code of conduct. By participating, you are expected to uphold this code.

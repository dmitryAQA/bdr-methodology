# Frequently Asked Questions (FAQ)

## 1. How does BDR differ from classic BDD (Cucumber/Gherkin)?
- **BDD (Gherkin)** requires maintaining separate text files (`.feature`) and regular expressions to link text to code. This creates massive overhead when maintaining thousands of tests.
- **BDR** implements the BDD idea via **Code-First**. We don't waste time parsing text; we write specifications directly in the language of business, which automatically turn into reporting (Living Requirements).

## 2. Can BDR be used with Unit Tests?
Yes, but BDR is focused on **E2E (End-to-End) and Integration Tests**. Unit tests verify function logic, while BDR documents system behavior from a user's perspective. BDR complements unit tests by giving business stakeholders insight into how features work.

## 3. Is Allure mandatory?
BDR requires **hierarchical reporting with step support**, and Allure is currently the best industry standard for this. However, the methodology can work with any tool that allows grouping actions and attaching screenshots/data to steps.

## 4. How does BDR help developers?
Developers don't need to learn new DSLs or specification languages. They work in their familiar IDE, using the same programming language as the main project (e.g., TypeScript). At the same time, they get clear feedback on what business logic they broke during refactoring.

## 5. Do I need to be an expert in all languages to adopt BDR?
No. BDR is primarily an **Architectural Contract**. You can adopt it on just one stack (e.g., Playwright/TS), and it will already bring value. Knowledge of other languages is only needed if you want to create a "Reference Implementation" for another team.

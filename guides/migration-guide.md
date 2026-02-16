# Migrating to BDR: How to Port a Legacy Project

Moving to BDR doesn't mean deleting everything old and rewriting from scratch. We recommend a gradual replacement strategy.

## 1. Analyze "Pain Points"
Start with the most unstable (flaky) or critical tests.
1. Isolate a test.
2. Wrap its current actions into Layer 1 (Flows) and Layer 0 (Technical).
3. Rewrite the scenario itself (Layer 3) into pure business language.

## 2. Strangler Pattern
New features are written strictly in BDR. Old tests live in a separate `legacy/` folder.
- You don't fix bugs in `legacy/` tests. You rewrite them to BDR when changes are required.
- Over time, the volume of BDR tests will exceed legacy, and you can painlessly remove the remnants.

## 3. Reporting Integration
Even if half the tests are not yet on BDR, configure Allure to merge results. This allows the business to see the full picture while engineers perform refactoring.

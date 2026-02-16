# Data Management in BDR

Test data is the "fuel" for automation. Low-quality data leads to false positives and flakiness.

## 1. Isolation by Contract
Every test must own its data.
- **No Shared Accounts**: If two tests use the same user, they will inevitably collide (Race Condition).
- **On-the-fly Creation**: Create entities (users, orders) directly in the test code (via API in Layer 1).

## 2. Factory Pattern
Instead of storing huge JSON files with data, BDR recommends using the **Data Factories** pattern.
- You call a method `UserFactory.createStandardUser()`.
- The factory returns an object with default data, which can be overridden only for a specific test.

## 3. Staging and Environments
BDR separates **Static Data** (which cannot be created, e.g., list of cities) and **Dynamic Data** (transactions).
- Static data is stored in Layer 0 constants.
- Dynamic data is cleaned up after each test (Cleanup mechanism).

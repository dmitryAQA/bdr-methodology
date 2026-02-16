# Scaling Patterns for BDR (1000+ Tests)

To keep the project fast and maintainable as it grows to hundreds and thousands of tests, BDR dictates the following engineering patterns:

## 1. Lazy Initialization (Lazy DI)
**Problem**: "Fixture Hell". If dozens of objects (Page Objects, Flows) are created at the start of every test, it slows down startup and consumes unnecessary memory.

**Solution**: Create dependencies only at the moment of their first call.
- In most modern frameworks (Playwright, Pytest), this is implemented via **fixtures or hooks** that initialize Layer 1 or Layer 2 classes only when the test accesses them.
- This ensures that if a test only needs `LoginFlow`, the system will not waste resources creating `CartFlow`, `PaymentFlow`, etc.

## 2. API + UI Orchestration
BDR encourages a hybrid approach for stability and speed:
- **API for Setup**: Creating users, filling the cart, or other mundane actions are done via API (Layer 0/1). It is fast and reliable.
- **UI for Verification**: Only key business behavior is verified via the browser.
- **Unified Report**: In the report (e.g., Allure), both types of actions appear as logical steps of a single process.

## 3. Global Infrastructure Guards
Before running the test suite (Global Setup), BDR recommends confirming the "vitality" of the environment. This is critical for stability and resource saving.
- **Fail-fast**: If the environment is down, the run fails immediately.
- For details on how this protects against false positives (flakes), read the **[Anti-Flakiness Guide](./anti-flakiness.md)**.

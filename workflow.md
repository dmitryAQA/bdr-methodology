# BDR Workflow: From User Story to Living Documentation

This guide bridges the gap between high-level business requirements and automated test reports.

## 1. Input: User Story (Jira/Requirement)
Let's imagine a standard requirement:
> **As a** Customer,
> **I want to** add a backpack to the cart,
> **So that** I can buy it later.

## 2. The Bridge: BDR Layer 3 (Scenario)
We translate intent directly into code *without* technical details. This is your **Code-First Scenario**.

```text
SCENARIO "Customer buys a backpack"
    ACTOR "Customer"
    DO Customer.login()
    DO Customer.addItemToCart("Backpack")
    VERIFY Customer.hasPurchased("Backpack")
```

## 3. Mapping: Layer 2 (Domain/Behavior)
We define *what* the business action means. Each domain action maps to an Allure Step.

```text
ACTION Customer.addItemToCart(name)
    STEP "Customer adds {name} to the cart"
    FLOW Inventory.selectItem(name)
    FLOW Cart.confirmAddition()
```

## 4. Result: Living Documentation (Allure Report)
When the test runs, the report doesn't just say `test passed`. It reflects the **structure of the User Story**:

✅ **User can add a backpack to the cart**
  - [Step] User logs in
  - [Step] **User adds "Sauce Labs Backpack" to the cart**
    - [Sub-step] Clicks "Add to Cart"
    - [Sub-step] Verifies cart badge increased
  - [Step] Verifies item is in cart

## Why this is not BDD (Gherkin)
- **No Translation Layer**: You don't need to maintain `.feature` files and regex mappings.
- **Pure Code**: Developers and QA work in the same environment.
- **Auto-Sync**: When behavior changes in code, the "Documentation" (Report) updates automatically.

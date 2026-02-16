# Universal BDR Pseudo-code Standard

This document defines the framework-agnostic language used to describe BDR scenarios and behaviors. It is designed to be readable by humans, LLMs, and easily mapped to any programming language.

## Table of Contents

- [Layer 3: Scenario](#layer-3-scenario)
- [Layer 2: Domain (Actions)](#layer-2-domain-actions)
- [Layer 1: Flows (Interactions)](#layer-1-flows-interactions)
- [Layer 0: Technical (Wrappers)](#layer-0-technical-wrappers)
- [Keywords Reference](#keywords-reference)

## Layer 3: Scenario

**Focus:** Business intent and outcome.

```text
SCENARIO "Scenario Name"
  ACTOR "Role/User Type"
  
  // Setup (optional)
  GIVEN Actor.hasCondition(param)
  
  // Execution
  DO Actor.businessAction(param)
  
  // Verification
  VERIFY Actor.hasState(expectedValue)
```

### Example: User Purchase Flow

```text
SCENARIO "User buys a backpack"
  ACTOR "Customer"
  
  GIVEN Customer.isLoggedIn()
  DO Customer.addItemToCart("Backpack")
  DO Customer.checkout()
  VERIFY Customer.hasPurchased("Backpack")
```

## Layer 2: Domain (Actions)

**Focus:** Orchestrating business flows and steps.

```text
ACTION Actor.businessAction(param)
  STEP "Human readable description for reporting"
  
  FLOW ModuleName.atomicAction(param)
  FLOW AnotherModule.confirmAction()
```

### Example: Add Item to Cart

```text
ACTION Customer.addItemToCart(name)
  STEP "Customer adds {name} to the cart"
  
  FLOW Inventory.selectItem(name)
  FLOW Cart.confirmAddition()
```

## Layer 1: Flows (Interactions)

**Focus:** Bridging Domain to technical components.

```text
FLOW ModuleName.atomicAction(param)
  STEP "Interacting with technical component"
  
  UI Component.performAction(param)
  API Service.sendRequest(data)
  DB Repository.saveRecord(entity)
```

### Example: Cart Flow

```text
FLOW Cart.confirmAddition()
  STEP "Press Add to Cart button"
  
  UI CartPage.addButton.click()
  UI CartPage.cartBadge.waitForIncrease()
```

## Layer 0: Technical (Wrappers)

**Focus:** Native tool interaction (Playwright, Selenium, etc).

```text
UI Component.performAction(param)
  NATIVE tool.click(this.selector)
  NATIVE tool.fill(this.selector, param)

API Service.sendRequest(data)
  NATIVE httpClient.post(this.endpoint, data)

DB Repository.saveRecord(entity)
  NATIVE database.insert(this.table, entity)
```

### Example: UI Click

```text
UI Component.click()
  STEP "Perform native click"
  NATIVE tool.click(this.selector)
```

## Keywords Reference

| Keyword | Layer | Description |
|---------|-------|-------------|
| **SCENARIO** | 3 | Starts a test scenario. |
| **ACTOR** | 3 | Defines the entity performing actions (User, Admin). |
| **GIVEN** | 3 | Optional setup condition (pre-condition). |
| **DO** | 3 | Executes a business-level action. |
| **VERIFY** | 3 | Asserts a condition. |
| **ACTION** | 2 | Defines a domain-level behavior. |
| **STEP** | 2, 1 | Marks a block for reporting (Allure step). |
| **FLOW** | 2, 1 | Calls an atomic interaction. |
| **UI** | 1, 0 | Points to the UI technical layer. |
| **API** | 1, 0 | Points to the API technical layer. |
| **DB** | 1, 0 | Points to the database layer. |
| **NATIVE** | 0 | Direct call to the underlying tool (Playwright/Selenium). |

---

*This pseudo-code standard ensures that BDR specifications remain readable and portable across different technology stacks.*

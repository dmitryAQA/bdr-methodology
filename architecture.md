# BDR: 4-Layer Architecture

BDR scales by separating responsibility into four distinct layers. This structure ensures that changes in technical implementation (Layer 0) do not break business logic (Layer 2) or test scenarios (Layer 3).

## Table of Contents

- [Layer 3: Scenario (Intent)](#layer-3-scenario-intent)
- [Layer 2: Domain (Business Actions)](#layer-2-domain-business-actions)
- [Layer 1: Flow (Atomic Interactions)](#layer-1-flow-atomic-interactions)
- [Layer 0: Technical (Tool)](#layer-0-technical-tool)
- [Why this works](#why-this-works)
- [Universal Keywords Reference](#universal-keywords-reference)

## Layer 3: Scenario (Intent)
**What are we testing?**  
This layer contains the test scenarios themselves. It uses high-level, human-readable commands. It contains ZERO technical details (no selectors, URLs, or API frameworks).

```text
SCENARIO "User buys a backpack"
  ACTOR "Customer"
  GIVEN Customer.isLoggedIn()
  DO Customer.login()
  DO Customer.addItemToCart("Backpack")
  DO Customer.checkout()
  VERIFY Customer.hasPurchased("Backpack")
```

## Layer 2: Domain (Business Actions)
**How does the business describe this action?**  
This layer maps high-level intents to orchestrated flows. It represents the "Ubiquitous Language" of the business.

```text
ACTION Customer.addItemToCart(name)
  STEP "Customer adds {name} to the cart"
  FLOW Inventory.selectItem(name)
  FLOW Cart.confirmAddition()
```

## Layer 1: Flow (Atomic Interactions)
**How do we interact with parts of the system?**  
This layer contains reusable atomic actions. It is the bridge between the domain and the technical implementation.

```text
FLOW Cart.confirmAddition()
  STEP "Press Add to Cart button"
  UI CartPage.addButton.click()
  UI CartPage.cartBadge.waitForIncrease()
```

## Layer 0: Technical (Tool)
**Which tool are we using?**  
A native wrapper for your test tool (Playwright, Selenium, Cypress). This is the ONLY place where tool-specific code lives.

```text
UI Component.click()
  STEP "Perform native click"
  NATIVE tool.click(this.selector)
```

---

### Why this works:
- **Reduced Maintenance Costs**: If a CSS selector changes, you only update Layer 0 or 1.
- **Improved Readability**: Layer 3 reads like a manual test script.
- **Stack Agnostic**: You can replace Playwright with Selenium by rewriting only Layer 0.

## Universal Keywords Reference

To maintain consistency across languages (Java, Python, TS), BDR uses these standard terms in pseudocode and documentation:

| Keyword | Description |
|---------|-------------|
| **SCENARIO** | Starts a test scenario (Layer 3). |
| **ACTOR** | Defines the entity performing actions (User, Admin). |
| **GIVEN** | Optional setup condition (pre-condition). |
| **DO** | Executes a high-level business action. |
| **VERIFY** | Asserts a condition. |
| **ACTION** | Defines a domain-level behavior (Layer 2). |
| **STEP** | Marks a block for reporting (Allure step). |
| **FLOW** | Calls an atomic interaction (Layer 1). |
| **UI** | Points to the UI technical layer. |
| **API** | Points to the API technical layer. |
| **DB** | Points to the database layer. |
| **NATIVE** | Direct call to the underlying tool (Playwright/Selenium). |

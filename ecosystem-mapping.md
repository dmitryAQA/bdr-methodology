# BDR Ecosystem Mapping

BDR is an architectural standard. This table shows how its core concepts map to popular tools and frameworks in different ecosystems.

| BDR Concept | Playwright (TS) | Pytest (Python) | JUnit/TestNG (Java) | Go (Testing) |
| :--- | :--- | :--- | :--- | :--- |
| **Layer 3 (Scenario)** | `test('name', ...)` (or equivalent) | `def test_name():` | `@Test` | `func TestName(t *testing.T)` |
| **Layer 2 (Domain)** | Classes in `domain/` | Classes/Modules | Domain Classes | Structs / Receivers |
| **Layer 1 (Flow)** | Classes in `flows/` | Classes/Modules | Actions/Pages | Logic Packages |
| **Layer 0 (Tech)** | `Page`, `APIRequest` | `Playwright-python` | `Selenium`, `RestAssured` | `Playwright-go`, `net/http` |
| **Steps (Reporting)** | `test.step()` | `@allure.step` | `@Step` (Allure) | `allure.Step` |
| **Setup/Teardown** | Fixtures | Fixtures | `@Before / @After` | `t.Cleanup()` |
| **Assertions** | `expect()` | `assert` | `assertThat()` | `testify/assert` |

## Mapping Summary

The goal of BDR is to keep the **Domain** and **Specification** layers as similar as possible across all stacks. The **Technical** layer is the only one where you use tool-specific APIs.

### Example: Allure Steps

Regardless of the language, BDR requires that every **Layer 2 action** and **Layer 1 flow** is wrapped in a reportable step:

- **TS (Playwright)**: `await test.step("Description", ...)`
- **Python (Pytest)**: `@allure.step("Description")`
- **Java (JUnit)**: `@Step("Description")`
- **Go (Allure-Go)**: `allure.Step(allure.NewStep("Description", ...))`

This ensures that the final **Living Documentation** looks identical regardless of the underlying technology.

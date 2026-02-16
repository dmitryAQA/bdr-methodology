# Folder Structure and BDR Conventions

Correct file organization is half the battle in long-term project maintenance.

## Core Folders

### 1. `scenarios/` (or `specs/`, `tests/`) — Layer 3
Here lie the scenario files (business specifications).
- **When to split**: As soon as file count exceeds 10-15.
- **Split Style**: By business feature or domain (e.g., `checkout/`, `auth/`, `profile/`).

### 2. `domain/` — Layer 2
Classes representing "Business Actors" (User, Admin, Partner). They orchestrate flows.

### 3. `flows/` — Layer 1
Atomic business actions.
- **Rule**: One file per logical module (e.g., `LoginFlow`, `CartFlow`). The file extension depends on the programming language used (e.g., `.ts`, `.py`, `.java`).

### 4. `pom/` (or `api/`, `db/`) — Layer 0
Technical implementation.
- For UI: Page Object Models.
- For API: API Clients.

## When to Split Files?
- **Single Responsibility Principle**: If your `CartFlow` starts handling search and payment too — it's time to extract `SearchFlow` and `PaymentFlow`.
- **Layer 3 Growth**: If one scenario file contains more than 10 tests, split it by sub-features.

## Naming Conventions
- **Flows**: Always end with `...Flow` (e.g., `InventoryFlow`).
- **Domain**: Nouns representing roles (e.g., `Customer`).
- **Scenarios**: Briefly reflect the nature of the check (e.g., `checkout_happy_path`). The file extension depends on the programming language used (e.g., `.ts`, `.py`, `.java`).

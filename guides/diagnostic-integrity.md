# Diagnostic Integrity

BDR claims: **"Video is the Detective, Tables are the Spoiler"**. We strive for the engineer to know the cause of the failure even before watching the video or trace viewer.

## 1. Data Comparison Tables
If a test fails on data verification (e.g., cart price mismatch), BDR requires attaching a **Comparison Table** directly to the report step.
- Before: `VERIFY price.is(100)` -> Error.
- After: Report shows table: `| Parameter | Expected | Actual |`.

## 2. Contextual Attachments
Every failure must be accompanied by:
- **System State (Snapshot)**: localStorage contents, cookies.
- **Business Context**: Which specific user and at what step of the "business flow" the failure occurred.

## 3. Readable Errors (Why it failed)
Instead of a technical stack trace `Error: timeout 5000ms`, BDR Layer 2 should generate business errors:
> "Error: Failed to add item 'Backpack' to cart. 'Add to cart' button was blocked by warehouse state."

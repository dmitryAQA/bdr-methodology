# Technical Guide: Anti-Flakiness

This document outlines specific technical solutions that uphold the BDR value of **"Infinite Reproducibility"**.

## 1. The Problem: Intermittent Failures
A test that fails "sometimes" without a code change destroys trust in the report. If we cannot trust the report, BDR loses its meaning.

## 2. Smart Waits Strategy
We do not use static delays (e.g., `Wait.5s()`). Instead, Layer 0 (Technical) must implement:
- **Auto-waiting**: Waiting for an element to be ready for action.
- **State-driven checks**: Waiting for a system state change, not just element appearance.

## 3. Infrastructure Health-checks
Before blaming the test code, we must ensure the "patient is alive".
- **Global Setup**: Before running the test suite, we verify the availability of critical services (DB, API, Auth).
- **Fail Fast**: If infrastructure is down, the run must fail immediately. This protects the "reputation" of tests from failures caused by environment instability.

## 4. Data Isolation
Every test in BDR must be independent.
- **Fresh Users**: Create unique data for each run.
- **Cleanup**: Automatic data cleanup after completion (via hooks or Teardown mechanisms).

## 5. Rich Debugging in Reports
To eliminate the cause of flakiness, the report must provide:
- **Trace Viewer**: Step-by-step execution playback.
- **Video/Screenshots**: Visual confirmation of DOM state at the moment of failure.
- **Network Logs**: Statuses of all API requests.

---
*This guide is part of the implementation of Layer 0 and Layer 1 strategies.*

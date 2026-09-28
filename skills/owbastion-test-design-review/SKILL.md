---
name: owbastion-test-design-review
description: >
  Review whether OWBastion tests protect durable behavior instead of mirroring
  current implementation. Use whenever a change adds, removes, rewrites, fixes,
  or updates tests, assertions, fixtures, snapshots, expected outputs, support
  states, or test-only production surface; also use for hard-coded
  version/count/date/member inventories, tests edited only to restore green CI,
  duplicated coverage, dependency bumps that change expectations, or questions
  like "do we need this test?", "is this brittle?", and "why didn't tests catch
  this?" Do NOT use merely to run an unchanged suite or as independent
  acceptance verification when test design itself is not under review.
license: AGPL-3.0-only
---

# OWBastion Test Design Review

Use the current repository's `AGENTS.md`, routed testing documentation, and owner-side contracts as authority. This skill is a review procedure, not a testing policy.

## Durable claim

Every durable test should protect a stable feature through at least one observable contract, real regression, failure mode, or invariant. Code changing does not by itself justify another test.

Expected values need a basis independent from the implementation under test: accepted API/business/gameplay behavior, reviewed fixture truth, a real regression, a runtime observation, or another authoritative reference.

## Review questions

- What stable feature owns the test?
- What distinct plausible wrong implementation would it catch?
- Does existing unit/integration/contract/runtime coverage already catch the same failure?
- Would the assertion survive a correct internal rewrite?
- Is it asserting observable semantics rather than helper calls, wrapper shape, current counts, current versions, or mutable inventories?
- Is the chosen layer the smallest one that exposes the failure clearly?
- Does the test require production changes solely for access?

Do not add or retain production APIs, public visibility, test-only hooks, configuration, state, or architectural indirection solely to make internals testable. Prefer an existing observable boundary or rewrite the test.

Issue/PR numbers are history, not test taxonomy. Do not organize committed tests or fixtures around work-item identifiers.

## Decision

Return one recommendation:

```text
Recommendation: keep | consolidate | rewrite | delete
Feature: <stable owning feature>
Claim: <observable contract, regression, failure mode, or invariant>
Existing coverage: <overlap or distinct gap>
Cost/coupling: <fixture, brittleness, or production-pollution cost>
Rationale: <why this coverage is or is not durable>
```

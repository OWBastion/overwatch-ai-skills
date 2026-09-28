---
name: owbastion-engineering-quality-review
description: >
  Review whether an OWBastion design or implementation admits only the minimum
  persistent mechanism needed by the current contract and keeps behavior in its
  coherent owner. Use when changes add state, services, adapters, APIs,
  configuration, feature flags, compatibility layers, cross-repository
  contracts, generic interpreters, behavior-driving metadata, or substantial
  responsibility to an existing module; also when the user asks whether a
  design is over-engineered, can be simpler, or lives in the right owner. Do
  NOT use for routine formatting, mechanical edits, test-design review, or
  post-hoc repository cleanup outside the changed responsibility.
license: AGPL-3.0-only
---

# OWBastion Engineering Quality Review

Use this procedure under the current repository's `AGENTS.md`, Issue contract, ownership rules, and routed architecture documentation.

## Principle

Start from the current requirement and direct solution. A mechanism is justified only when removing, deferring, inlining, or reusing existing machinery would violate a current contract, invariant, ownership boundary, measurable constraint, or real workflow.

The smallest diff is not necessarily the simplest design. Compare persistent concepts: state, schemas, services, adapters, APIs, flags, dependencies, protocols, synchronization, compatibility paths, and cross-repository obligations.

## Review

For each material mechanism:

1. State the concrete requirement or contract it serves.
2. Identify the existing/direct path that avoids the mechanism.
3. Test whether the mechanism can be removed, deferred, inlined, or merged into an existing owner.
4. Check responsibility: would a maintainer looking for this domain behavior find it in the proposed location?
5. Keep the mechanism only when the simpler design fails the current requirement or increases total maintenance cost.

Do not self-authorize unresolved product behavior, public contracts, privacy/security boundaries, gameplay rules, or cross-repository ownership.

## Output

```text
Concern: <material mechanism or responsibility problem>
Contract: <current requirement or owner-side authority>
Direct alternative: <simpler path considered>
Why it fails or succeeds: <concrete reason>
Required change: <smallest correction, or owner decision if unresolved>
```

No actionable concern is a valid result.

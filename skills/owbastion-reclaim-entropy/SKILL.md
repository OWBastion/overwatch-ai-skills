---
name: owbastion-reclaim-entropy
description: >
  Find or remove OWBastion maintenance entropy such as duplicate truth, dead or
  redundant abstractions, obsolete fallbacks, compatibility residue,
  post-migration leftovers, duplicated state/configuration, abandoned
  extension points, and support artifacts whose owning behavior disappeared.
  Use for focused cleanup, entropy audits, migration cleanup, "what can we
  delete?", "is this still load-bearing?", or repeated agentic changes that
  accumulated layers. Do NOT use for routine feature implementation, aesthetic
  refactoring, or self-authorizing removal of public, compatibility, privacy,
  persisted-data, or cross-repository contracts.
license: AGPL-3.0-only
---

# OWBastion Reclaim Entropy

The objective is to remove maintenance obligations, not maximize deleted lines.

## Investigation model

For each candidate:

1. Name the obligation being maintained: state, API, schema, adapter, fallback, dependency, fixture, generated artifact, duplicated fact, or lifecycle mechanism.
2. Trace real consumers: production, generated/dynamic, test-only, cross-repository, and external where applicable.
3. Identify what makes it load-bearing: current contract, ownership decision, compatibility, persistence, privacy/security, lifecycle requirement, or real consumer.
4. Compare the cut with the replacement cost. Prefer deletion or consolidation onto one canonical owner; reject changes that merely move the same complexity behind another wrapper.

Repository search, dead-code warnings, fixture counts, and green tests generate candidates; they do not prove a safe deletion.

Do not self-authorize removal of public APIs, persisted formats, Agents API contracts, gameplay compatibility, privacy/security checks, released artifact contracts, or another repository's owned behavior.

Tests that exist only for a removed internal mechanism may disappear with it. Tests protecting surviving observable behavior must remain or be replaced by an equivalent or stronger check.

## Output

```text
Candidate: <maintenance obligation>
Consumers: <real callers or external/dynamic consumers>
Contract: <why it is or is not load-bearing>
Change: <exact deletion/consolidation>
Net effect: <concepts/state/contracts removed; replacement cost>
Authority: implementation-level | owner decision required
Verify: <smallest decisive check>
```

Finding no worthwhile cut is a valid result.

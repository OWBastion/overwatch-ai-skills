---
name: owbastion-verify-change
description: >
  Independently falsify whether a material OWBastion change is correct and
  complete using authority outside the implementation being checked. Use in PR
  review or an assigned QA pass for gameplay semantics, state lifecycle,
  platform business rules, migrations, privacy/security boundaries,
  cross-service contracts, QQ idempotency/reply behavior, OCR parsing/layout or
  confidence behavior, and public/canonical boundary migrations; also when the
  user asks to prove a fix is complete or a regression escaped coverage. Do
  NOT use as a routine test runner, to decide whether a test should exist, or
  as a second agent re-reading its own implementation.
license: AGPL-3.0-only
---

# OWBastion Verify Change

Verification should distinguish a correct implementation from a plausible incorrect one. Independence comes from the authority, not from using another agent.

## Procedure

1. State one falsifiable claim about the changed behavior.
2. Identify an independent authority: accepted Issue/contract, production or reproducible runtime behavior, reviewed fixture truth, public API/schema, migration invariant, real regression, or owner-side cross-repository contract.
3. Choose the narrowest check that would fail if the claim were false.
4. Compare the observation with the authority. Where practical, remove, invert, or simplify the key behavior and confirm the targeted regression returns.
5. Record limitations instead of inferring correctness from green CI.

Rerunning tests authored with the change is supporting evidence, not independent verification. A same-model reviewer of the same assumptions does not create independence.

For boundary migrations, verify surviving accepted capabilities through the replacement boundary itself; legacy adapters staying green do not prove continuity.

## Output

```text
Claim: <falsifiable behavior>
Authority: <independent source>
Surface: <decisive check>
Observation: <result>
Verdict: VERIFIED | NOT VERIFIED | INCONCLUSIVE
Limitations: <material uncertainty or none>
```

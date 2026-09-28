# Agent guidance for overwatch-ai-skills

This repository owns reusable OWBastion agent procedures and discovery metadata. It does not own product behavior, repository architecture, or organization-wide engineering policy.

## Authoring rules

- Keep skills procedural. Link or defer to the target repository's `AGENTS.md`, routed docs, current contract, and Issue rather than copying those rules here.
- Treat frontmatter `description` as the discovery contract. Include semantic task/risk/artifact triggers, representative indirect triggers, and meaningful non-triggers.
- Prefer reasoning criteria over exhaustive checklists. Examples illustrate judgment; they must not silently become supported-case inventories.
- Keep mutable versions, counts, current issue state, rollout status, model inventories, and repository-specific command lists out of reusable skills.
- Do not add a skill merely because a task can be described as a workflow. A reusable skill needs a recurring judgment or procedure that materially improves work across repositories or repeated tasks.
- Skills cannot widen task scope or authorize architecture, product, privacy, security, compatibility, release, deployment, production mutation, or cross-repository ownership decisions.

## Quality of procedures

A skill should help an agent distinguish a correct action from a plausible wrong one. It should identify the authority it relies on, the smallest useful investigation surface, and a concise output or decision shape.

When the procedure concerns tests, verification, or cleanup:

- tests exist to protect durable behavior, regressions, failure modes, or invariants, not because code changed;
- expected results need an independent basis;
- production APIs, state, hooks, visibility, or indirection must not be introduced solely to make a test convenient;
- scanners and green CI are evidence, not proof;
- simplification removes maintenance obligations rather than merely lines.

## Delivery

All repository changes use a non-default branch and PR. Do not push directly to the default branch. Keep PR scope limited to the skill or governance change being made.

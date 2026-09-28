# overwatch-ai-skills

Reusable agent procedures for OWBastion and Overwatch Workshop development.

This repository follows the [Agent Skills Specification](https://agentskills.io/specification), with each skill centered on a canonical `SKILL.md`.

## Ownership boundary

This repository owns reusable **procedures and skill discovery metadata**. It is not the organization policy owner and must not become a second copy of repository architecture, product contracts, testing policy, or mutable project status.

- Repository `AGENTS.md` and routed documentation own repository-specific contracts and constraints.
- Issues and PRs own task scope and current work state.
- Skills describe how to investigate, review, verify, or simplify within those boundaries.
- A skill must not widen scope or self-authorize product, architecture, privacy, compatibility, release, or cross-repository decisions.

## Skill discovery

A skill description is an activation surface, not merely a summary of its body. Descriptions should make relevant work discoverable without requiring users to name the skill explicitly.

Prefer semantic triggers: changed artifacts, risk surfaces, failure signals, and natural user wording. Include important indirect cases such as a dependency bump that changes expectations or a refactor that introduces test-only production surface. State adjacent non-triggers so overlapping skills have clear ownership.

Before materially changing a skill, check its description against representative direct triggers, indirect triggers, and nearby non-trigger prompts.

## Available Skills

See [skills/README.md](skills/README.md) for the current catalog.

## Model Compatibility

- Codex: consume the skill via `SKILL.md`; optional UI metadata may live in `agents/openai.yaml`.
- Claude Code: consume the same `SKILL.md`; non-standard metadata files can be ignored safely.
- Any Agent Skills-compatible runtime: read frontmatter + markdown body from `SKILL.md`.

## Repository Layout

```text
overwatch-ai-skills/
  AGENTS.md
  skills/
    <skill-name>/
      SKILL.md
      agents/openai.yaml  # optional
      references/         # optional
      scripts/            # optional
      assets/             # optional
```

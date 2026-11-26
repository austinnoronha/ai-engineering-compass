# Cursor integration

This folder contains project-level templates for [Cursor](https://cursor.com/docs).

## Files

| Template here | Copy to your application repository | Purpose |
|---|---|---|
| [`rules/compass-foundation.mdc`](rules/compass-foundation.mdc) | `.cursor/rules/compass-foundation.mdc` | Short, always-applied instructions that connect the project to Compass |
| [`rules/engineering-sdlc.mdc`](rules/engineering-sdlc.mdc) | `.cursor/rules/engineering-sdlc.mdc` | Task-oriented lifecycle guidance |
| [`skills/engineering-sdlc/SKILL.md`](skills/engineering-sdlc/SKILL.md) | `.cursor/skills/engineering-sdlc/SKILL.md` | Reusable SDLC procedure |

Cursor also supports a root `AGENTS.md` for straightforward project instructions. The [shared integration template](../shared/AGENTS.md) can be copied to that location. Choose either a minimal AGENTS.md setup or the more structured project rules and skills; avoid duplicating large instructions across all locations.

## Install

From the root of your application repository, after cloning AI Engineering Compass elsewhere:

```bash
mkdir -p .cursor/rules .cursor/skills/engineering-sdlc
cp /path/to/ai-engineering-compass/integrations/cursor/rules/*.mdc .cursor/rules/
cp /path/to/ai-engineering-compass/integrations/cursor/skills/engineering-sdlc/SKILL.md .cursor/skills/engineering-sdlc/SKILL.md
```

Optionally install the shared baseline:

```bash
cp /path/to/ai-engineering-compass/integrations/shared/AGENTS.md ./AGENTS.md
```

Review the rules before committing. Adapt the project-specific commands, architecture, and security expectations.

## Official documentation

- [Cursor rules](https://cursor.com/docs/rules)
- [Cursor Agent Skills](https://cursor.com/docs/skills)
- [Cursor AGENTS.md support](https://cursor.com/docs/rules#agents-md)

## Canonical engineering standards

Cursor rules and skills point to the [AI Engineering Compass documentation index](https://github.com/austinnoronha/ai-engineering-compass/blob/main/docs/README.md). Consult the specific topic guides needed for the current task. The [shared instructions](../shared/AGENTS.md) define the broader lifecycle approach.

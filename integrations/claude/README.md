# Claude Code integration

This folder contains project-level templates for [Claude Code](https://code.claude.com/docs/en/overview).

## Files

| Template here | Copy to your application repository | Purpose |
|---|---|---|
| [`CLAUDE.md`](CLAUDE.md) | `CLAUDE.md` at repository root | Always-on project context and guidance for Claude Code |
| [`skills/engineering-sdlc/SKILL.md`](skills/engineering-sdlc/SKILL.md) | `.claude/skills/engineering-sdlc/SKILL.md` | Reusable lifecycle workflow for planning through release |
| [`agents/engineering-reviewer.md`](agents/engineering-reviewer.md) | `.claude/agents/engineering-reviewer.md` | Optional read-only engineering review subagent |

Claude Code's root `CLAUDE.md` is intended for durable project context. Reusable, procedural workflows belong in skills; specialized delegated tasks can be defined as subagents. Claude Code can also use a repository's `AGENTS.md` in place of `CLAUDE.md`. This pack provides both a shared `AGENTS.md` baseline and a Claude-specific `CLAUDE.md` template; review them together and remove duplicated instructions if you install both. Keep always-on context concise and avoid duplicating the full documentation library there.

## Install

From the root of your application repository, after cloning AI Engineering Compass elsewhere:

```bash
cp /path/to/ai-engineering-compass/integrations/claude/CLAUDE.md ./CLAUDE.md
mkdir -p .claude/skills/engineering-sdlc .claude/agents
cp /path/to/ai-engineering-compass/integrations/claude/skills/engineering-sdlc/SKILL.md .claude/skills/engineering-sdlc/SKILL.md
cp /path/to/ai-engineering-compass/integrations/claude/agents/engineering-reviewer.md .claude/agents/engineering-reviewer.md
```

The subagent is optional. Review the permissions and tool configuration against your own security policy before using it.

## Official documentation

- [Claude Code overview](https://code.claude.com/docs/en/overview)
- [Memory and CLAUDE.md](https://code.claude.com/docs/en/memory)
- [Skills](https://code.claude.com/docs/en/skills)
- [Subagents](https://code.claude.com/docs/en/sub-agents)
- [Settings](https://code.claude.com/docs/en/settings)

## Canonical engineering standards

Claude Code should consult the [AI Engineering Compass documentation index](https://github.com/austinnoronha/ai-engineering-compass/blob/main/docs/README.md) and the narrow topic guides relevant to the current task. The [shared instructions](../shared/AGENTS.md) show how to select those guides and apply them across the SDLC.

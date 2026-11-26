# Bring AI Engineering Compass into your repository

AI Engineering Compass can be used as a starter set of engineering standards for an existing or new software project. You do not need to copy this entire repository into every application.

The recommended approach is:

1. Keep your project's own architecture, run commands, domain knowledge, and constraints in its repository.
2. Add a small set of AI-assistant instructions that explain how to use the Compass.
3. Link to the canonical engineering guidance in the Compass `docs/` directory.
4. Ask the assistant to apply the guidance throughout the software development lifecycle (SDLC), not just while generating code.
5. Contribute generally useful improvements back to AI Engineering Compass through issues and pull requests.

## Choose an adoption model

### Option A: Canonical reference model

Keep only the small integration files in your application repository. Those files point to the canonical Compass documentation on GitHub.

Canonical documentation index:

- [All engineering standards and topic guides](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs)
- [Documentation index](https://github.com/austinnoronha/ai-engineering-compass/blob/main/docs/README.md)

**Advantages:** Your application repo stays small and the standards have one canonical home.

**Trade-off:** The assistant needs network access and the ability to open the linked documentation. A URL in an instruction file does not guarantee that an AI tool has fetched or read the page. Ask it to consult the relevant pages and verify that it has the context. If it cannot access the links, use Option B.

### Option B: Local standards snapshot

Copy the relevant Compass articles into your project, for example under `engineering/standards/`, and keep the original Compass URL in the copied article's attribution or source note.

**Advantages:** The guidance is available offline and can be reviewed in the same pull request as application changes.

**Trade-off:** Your copy will not update automatically. Periodically compare it with the [canonical docs](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs) and refresh it deliberately.

Do not copy every topic by default. Choose the standards that fit your architecture, stack, regulatory requirements, and team maturity.

## What to add to an application repository

| File or folder | Purpose | Required? |
|---|---|---|
| `AGENTS.md` | Shared baseline for assistants that support the AGENTS.md convention; describes how to work in the project and consult Compass. | Recommended |
| `CLAUDE.md` | Claude Code project instructions. | For Claude Code |
| `.claude/skills/engineering-sdlc/SKILL.md` | Reusable feature lifecycle workflow for Claude Code. | Recommended for Claude Code |
| `.claude/agents/engineering-reviewer.md` | A focused, read-only engineering reviewer for Claude Code. | Optional |
| `.cursor/rules/compass-foundation.mdc` | Always-on project guidance for Cursor Agent. | For Cursor |
| `.cursor/rules/engineering-sdlc.mdc` | Task-oriented SDLC workflow guidance for Cursor. | Recommended for Cursor |
| `.cursor/skills/engineering-sdlc/SKILL.md` | Reusable SDLC workflow skill for Cursor. | Optional / use when skills are enabled |

The integration templates in this folder are examples to copy and adapt. They are not a replacement for your own project's engineering instructions.

## Quick installation

Clone this repository somewhere outside your application repository:

```bash
git clone https://github.com/austinnoronha/ai-engineering-compass.git
```

Run the following commands from the root of your application repository. Copy only the integration(s) you use.

### Shared instructions

```bash
cp /path/to/ai-engineering-compass/integrations/shared/AGENTS.md ./AGENTS.md
```

### Claude Code

```bash
cp /path/to/ai-engineering-compass/integrations/claude/CLAUDE.md ./CLAUDE.md
mkdir -p .claude/skills/engineering-sdlc .claude/agents
cp /path/to/ai-engineering-compass/integrations/claude/skills/engineering-sdlc/SKILL.md .claude/skills/engineering-sdlc/SKILL.md
cp /path/to/ai-engineering-compass/integrations/claude/agents/engineering-reviewer.md .claude/agents/engineering-reviewer.md
```

If you do not want the optional reviewer subagent, skip the last command.

### Cursor

```bash
mkdir -p .cursor/rules .cursor/skills/engineering-sdlc
cp /path/to/ai-engineering-compass/integrations/cursor/rules/*.mdc .cursor/rules/
cp /path/to/ai-engineering-compass/integrations/cursor/skills/engineering-sdlc/SKILL.md .cursor/skills/engineering-sdlc/SKILL.md
```

You can use Cursor's root `AGENTS.md` support instead of the `.cursor/rules/` files for a very simple setup. Do not install duplicate instructions blindly; keep one clear source for each rule.

> Replace `/path/to/ai-engineering-compass` with the actual path where you cloned this repository. Review every copied file and tailor commands, frameworks, service boundaries, and security requirements to your application before committing.

## Point assistants to the canonical standards

The Compass documentation lives in one canonical location:

- [Documentation index](https://github.com/austinnoronha/ai-engineering-compass/blob/main/docs/README.md)
- [Fundamentals](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/fundamentals)
- [Software design](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/software-design)
- [Backend engineering](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/backend-engineering)
- [Frontend engineering](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/frontend-engineering)
- [Databases and storage](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/databases-and-storage)
- [Testing and quality](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/testing-and-quality)
- [Security and privacy](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/security-and-privacy)
- [Cloud and DevOps](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/cloud-and-devops)
- [Reliability and observability](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/reliability-and-observability)
- [AI-assisted engineering](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/ai-assisted-engineering)
- [Engineering workflow](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/engineering-workflow)

Use the narrowest relevant article for the task. For example, an API change should consider API design, error handling, security, testing, and operational concerns rather than loading every document for every request.

## Apply the standards across the SDLC

Use the AI assistant as an engineering partner across the lifecycle:

| Stage | What the assistant should help with | Human responsibility |
|---|---|---|
| Discover and plan | Clarify the problem, identify missing requirements, propose acceptance criteria, expose assumptions and risks. | Confirm the problem, scope, priorities, and acceptance criteria. |
| Design | Explore options, boundaries, data contracts, integrations, failure modes, and trade-offs. | Choose and approve the design; own significant technical decisions. |
| Implement | Make focused changes that follow project conventions and the relevant Compass guidance. | Review the code and decide what is accepted. |
| Verify | Suggest and run appropriate tests, static analysis, security checks, and manual verification where available. | Inspect results and ensure the evidence is sufficient. |
| Review | Inspect the full diff for correctness, maintainability, security, performance, and scope. | Make the final review and merge decision. |
| Release | Prepare migration, configuration, deployment, smoke-test, rollback, and release notes. | Approve and execute production changes under the team's controls. |
| Operate and learn | Help interpret logs, metrics, traces, incidents, and recurring problems; suggest documentation improvements. | Validate findings, manage incidents, and decide follow-up work. |

AI instructions are guidance, not an enforcement boundary. Keep deterministic controls such as CI checks, branch protection, tests, code owners, access control, secret scanning, and production approvals in the engineering platform.

## Keep application-specific instructions in the application repository

The Compass should provide reusable engineering practices. Your project repository should define:

- What the product does and who uses it.
- Its architecture, components, data flows, and integration boundaries.
- Supported languages, frameworks, versions, and package managers.
- Local development, test, build, and deployment commands.
- Project-specific code conventions and API contracts.
- Environments, configuration, infrastructure, and operational ownership.
- Security, privacy, compliance, and data-handling constraints.

Do not make the Compass the source of truth for application-specific facts.

## Contribute improvements back

When you discover a practice, checklist, example, or explanation that could help engineers in other repositories, please contribute it back.

1. Open an [issue](https://github.com/austinnoronha/ai-engineering-compass/issues) to discuss a substantial new topic.
2. Create a branch and make a focused change.
3. Use the [article template](https://github.com/austinnoronha/ai-engineering-compass/blob/main/templates/article-template.md).
4. Include scope, assumptions, trade-offs, verification guidance, and reliable references.
5. Open a [pull request](https://github.com/austinnoronha/ai-engineering-compass/compare) for review.

Keep project-specific standards in your application repository. Contribute generalized patterns and lessons to the Compass so the wider engineering community can benefit.

<div align="center">

<img src="assets/brand/ai-engineering-compass.svg" alt="AI Engineering Compass logo" width="760" />

### Your practical guide to building great software in the AI era.

Real code, proven patterns, and shared engineering wisdom for the AI era.

[Explore the guides](docs/README.md) · [Contribute](CONTRIBUTING.md) · [Brand and logo](docs/brand-guidelines.md) · [Suggest a topic](https://github.com/austinnoronha/ai-engineering-compass/issues/new/choose)

</div>

---

## What this is

Software engineering is changing quickly. AI tools are changing how we explore ideas, write code, review changes, and ship products. But the fundamentals still matter: clear thinking, good design, testing, security, maintainability, and learning from experience.

**AI Engineering Compass** is a practical, community-minded knowledge base for engineers building software in the AI era. Think of a compass: it does not force everyone down the same road. It helps you find direction when the choices are difficult.

This is a place to learn what to build, how to build it well, and where AI can help without replacing engineering judgement.

## What you will find

| Area | What it covers |
|---|---|
| **Hands-on code samples** | Small, focused examples with context, assumptions, and ways to verify them. |
| **Common patterns and architecture** | Practical approaches to boundaries, APIs, data, testing, and system design. |
| **Practical AI workflows** | Using AI to explore, implement, test, and review code while keeping humans accountable. |
| **Field notes and experiences** | Lessons from real engineering work, including what worked, what failed, and why. |
| **Curated learning hub** | Carefully selected documentation, talks, articles, and books worth your time. |

## Browse the compass

Start with the topic closest to the problem you are trying to solve.

- [Fundamentals](docs/fundamentals/README.md)
- [Software design](docs/software-design/README.md)
- [Backend engineering](docs/backend-engineering/README.md)
- [Frontend engineering](docs/frontend-engineering/README.md)
- [Databases and storage](docs/databases-and-storage/README.md)
- [Testing and quality](docs/testing-and-quality/README.md)
- [Security and privacy](docs/security-and-privacy/README.md)
- [Cloud and DevOps](docs/cloud-and-devops/README.md)
- [Reliability and observability](docs/reliability-and-observability/README.md)
- [AI-assisted engineering](docs/ai-assisted-engineering/README.md)
- [Engineering workflow](docs/engineering-workflow/README.md)
- [Examples](examples/README.md) · [Checklists](checklists/README.md) · [Learning resources](learning-resources/README.md) · [Field notes](field-notes/README.md)

The [documentation index](docs/README.md) is the full map.

## How we approach engineering

These are guiding principles, not rigid rules:

1. **Understand the problem before choosing the tool.** Start from user needs, constraints, and evidence.
2. **Prefer clarity over cleverness.** Make intent, ownership, and failure behaviour easy to understand.
3. **Choose proportionate design.** Add architecture when it solves a real problem, not to follow fashion.
4. **Treat quality as part of delivery.** Testing, security, documentation, and operations are part of a feature.
5. **Make trade-offs visible.** Explain where a recommendation fits and where it does not.
6. **Use AI with judgement.** AI can accelerate work; engineers remain responsible for correctness and consequences.
7. **Learn in the open.** Share useful lessons while protecting confidential, personal, and customer information.

## How to use this repository

You can use the material in several ways:

- Read a guide to understand a concept or compare approaches.
- Adapt a checklist during design, implementation, review, or release.
- Run an example and use it as a starting point, after checking its assumptions.
- Give an AI coding assistant the relevant `AGENTS.md` and topic guidance alongside your task.
- Propose an improvement when you find something unclear, incomplete, or out of date.

The content is framework-agnostic where possible. Technology-specific examples should state the versions and assumptions they depend on.

## Use Compass as a starter for your own repository

You can adopt these engineering standards in an existing or new application repository and use them with AI coding assistants. The goal is to give your assistant a shared engineering playbook across the SDLC, while keeping your own architecture and project decisions in your repository.

**Start here:** [Integration and adoption guide](integrations/README.md)

Ready-to-copy templates are provided for:

- **Claude Code:** root `CLAUDE.md`, a reusable `engineering-sdlc` skill, and an optional read-only engineering reviewer in `.claude/`.
- **Cursor:** project rules in `.cursor/rules/` and an SDLC skill in `.cursor/skills/`.
- **Other compatible assistants:** a shared `AGENTS.md` baseline where supported.

Choose between two approaches:

1. **Canonical reference:** keep the small assistant instruction files in your project and point them to the [canonical Compass documentation](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs). Ask your assistant to open the relevant pages for each task. A link alone does not mean the assistant has read the document.
2. **Local snapshot:** copy only the relevant standards into your own repository, retain attribution and the canonical source link, and refresh the copies when the Compass guidance changes.

Use the standards across discovery, planning, design, implementation, testing, review, release preparation, and operations. The assistant can help at each stage, but your engineers remain responsible for decisions, verification, approvals, and production changes.

Keep application-specific facts, commands, architecture, and policies in your own repository. When you develop a generally useful standard, example, checklist, or lesson, [contribute it back through an issue or pull request](CONTRIBUTING.md).

## Content quality and trust

This repository is a shared learning resource, not a universal rulebook.

- Articles identify their status and review date.
- Recommendations explain context and trade-offs.
- External claims should link to reliable sources, favouring official documentation and primary references.
- Examples should state prerequisites and be tested where practical.
- Personal experience should be labelled as experience, not presented as universal fact.
- Third-party material must be properly attributed and compatible with its license.

Read the [content standards](CONTRIBUTING.md) before contributing.

## Brand and logo

The AI Engineering Compass logo is part of the project's shared identity. **You are welcome to use it when referencing the project or contributing to it.** For example, you can include it in a contribution, tutorial, presentation, article, or community post that points people to this repository.

- [Primary horizontal logo (SVG)](assets/brand/ai-engineering-compass.svg)
- [Standalone compass-A mark (SVG)](assets/brand/compass-mark.svg)
- [Logo usage and visual guidelines](docs/brand-guidelines.md)
- [Brand asset license](LICENSE-BRAND)

The logo artwork is available under **CC BY 4.0**. Please credit **AI Engineering Compass** and link to this repository or the license. You may adapt the artwork under the license terms, but make it clear when a version has been modified. Do not use the logo in a way that suggests project endorsement, official maintainer status, or affiliation that does not exist.

## Licensing

- Documentation and written guidance: [Creative Commons Attribution 4.0 International](LICENSE-DOCS).
- Original code examples and code artifacts: [MIT License](LICENSE-CODE).
- Logo and brand artwork: [Creative Commons Attribution 4.0 International](LICENSE-BRAND).

Third-party materials retain their original licenses. Contributions must be yours to share under the applicable license. See [LICENSE](LICENSE) for the repository-level notice.

## Contributing

You do not need to be an expert or write a long article to contribute. Fix a confusing explanation, add a tested example, share a useful reference, or propose a topic. You can also use the project logo in your contribution by following the [brand guidelines](docs/brand-guidelines.md).

Please read [CONTRIBUTING.md](CONTRIBUTING.md), follow the [article template](templates/article-template.md), and open an issue or pull request.

---

<div align="center">

**Good engineering is not about following one road. It is about knowing how to choose the right direction.**

</div>

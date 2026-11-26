# AI Engineering Compass: guidance for AI assistants

This repository is a practical engineering knowledge base. Treat its content as guidance for human engineers and AI coding assistants.

## Working principles

1. Read the relevant article and its scope before suggesting changes.
2. Preserve the repository's practical, welcoming, framework-agnostic voice.
3. Do not turn contextual recommendations into universal rules.
4. Explain assumptions, trade-offs, limitations, and failure modes.
5. Prefer primary sources and official documentation for external claims.
6. Never invent APIs, library behaviour, benchmark results, citations, or test outcomes.
7. Protect confidential, personal, customer, and production information.
8. Keep examples focused. State language/runtime versions and prerequisites where relevant.
9. Distinguish verified facts, personal experience, and opinion.
10. Do not present generated code as tested unless it was actually executed.

## When editing an article

- Follow `templates/article-template.md`.
- Include status, last-reviewed date, and scope.
- Explain why the topic matters and when advice applies.
- Include examples only when they teach something concrete.
- Include anti-patterns, trade-offs, verification guidance, and references.
- Check links and relative paths.
- Avoid copying third-party text. Summarize in your own words and attribute sources.

## When adding code

- Make examples runnable or clearly label them as illustrative.
- Pin or state relevant dependency/runtime assumptions.
- Include tests or exact verification steps.
- Avoid secrets, untrusted input, and unnecessary external side effects.
- Use MIT licensing for original code artifacts.

## Before finishing

Review the full diff, validate Markdown links where possible, and report exactly what was changed and what checks were run.

# AI pairing workflow

**Status:** Recommended  
**Last reviewed:** 2026-11-26

AI assistants can help explore unfamiliar code, draft implementations, generate tests, and explain alternatives. They can also make plausible mistakes, miss hidden constraints, or produce changes that compile but are unsafe.

Treat the assistant as a collaborator whose work must be reviewed, not as the authority for the system.

## A practical loop

1. **Set context.** Explain the user problem, relevant files, constraints, language/runtime versions, and acceptance criteria.
2. **Ask for a plan.** For multi-file or high-risk changes, request a short plan and identify unknowns before editing.
3. **Constrain the change.** State what must not change, which interfaces are stable, and what tools or side effects are allowed.
4. **Implement in small steps.** Keep diffs reviewable and ask for explanations around non-obvious decisions.
5. **Verify independently.** Run tests, formatters, static analysis, security checks, and relevant manual checks.
6. **Review the diff.** Look for scope creep, generated boilerplate, incorrect assumptions, secrets, and unnecessary dependencies.
7. **Record learning.** Update documentation when a verified lesson is likely to help future work.

## Share context safely

Provide only the data required for the task. Remove credentials, customer data, proprietary prompts, personal information, and production payloads unless an approved tool and policy explicitly allow their use.

## Useful prompt pattern

Ask the assistant to state assumptions, propose options, explain risks, and identify tests. For example:

> Review this change for correctness and security. Identify assumptions, edge cases, and missing tests. Do not modify files. Cite relevant code locations and distinguish confirmed issues from suggestions.

## References

- [GitHub: Responsible use of Copilot](https://docs.github.com/en/copilot/responsible-use/copilot-code-completion)
- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications/)

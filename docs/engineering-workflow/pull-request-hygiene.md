# Pull request hygiene

**Status:** Recommended  
**Last reviewed:** 2026-11-26

A pull request is a communication tool as much as a code-change mechanism. A focused change with clear context is easier to review and safer to merge.

## Keep changes reviewable

- Prefer one coherent purpose per pull request.
- Split unrelated refactoring from functional changes when practical.
- Explain why the change is needed and what behaviour changes.
- Include tests, screenshots, or operational evidence where useful.
- Call out migrations, configuration changes, feature flags, and deployment order.
- Mention known limitations and follow-up work.

## Review responsibilities

Authors should make the change understandable and provide verification evidence. Reviewers should focus on correctness, maintainability, security, and user impact. Reviewers are not expected to infer missing requirements from code.

## Review checklist

- Is the purpose clear?
- Are requirements and edge cases addressed?
- Is the diff focused?
- Are tests appropriate and results reported?
- Are config, security, migrations, and operations considered?
- Can the change be rolled back or disabled if needed?

## References

- [GitHub: About pull requests](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

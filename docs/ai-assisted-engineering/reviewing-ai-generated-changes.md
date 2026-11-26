# Reviewing AI-generated changes

**Status:** Recommended  
**Last reviewed:** 2026-11-26

Generated code deserves the same review as human-written code, with extra attention to assumptions that may have been invented to fill gaps in context.

## Review beyond compilation

Check:

- Does the change solve the stated problem and respect scope?
- Are APIs, configuration keys, schemas, and dependencies real and compatible with project versions?
- Are authorization and tenant boundaries preserved?
- Are errors, retries, cancellation, timeouts, and partial failures handled?
- Are tests meaningful, deterministic, and capable of detecting regressions?
- Did the assistant introduce unnecessary abstraction or duplicate existing functionality?
- Are documentation and examples consistent with actual behaviour?

## Verify external claims

When an assistant cites a library API, version, security advisory, benchmark, or provider behaviour, verify it against authoritative sources. A plausible explanation is not evidence that the behaviour exists in the selected version.

## Inspect the actual diff

Do not review only the assistant's summary. Read every changed file and inspect generated configuration, lockfiles, dependency updates, scripts, and migrations.

## Review checklist

- [ ] Scope and acceptance criteria are met.
- [ ] No invented APIs, configuration, or dependencies.
- [ ] Security and data handling reviewed.
- [ ] Failure paths reviewed.
- [ ] Tests and checks run and results recorded.
- [ ] Full diff inspected.
- [ ] Documentation updated where needed.

## References

- [Google Engineering Practices: Code Review](https://google.github.io/eng-practices/review/)
- [GitHub: Reviewing proposed changes](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/reviewing-changes-in-pull-requests)

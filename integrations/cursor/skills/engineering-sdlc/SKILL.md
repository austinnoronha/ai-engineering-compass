---
name: engineering-sdlc
description: A practical workflow for planning, designing, implementing, testing, reviewing, and preparing software changes for release using AI assistance.
---

# Engineering SDLC

Use this workflow for feature development, bug fixes, refactoring, architecture changes, migrations, security improvements, and release preparation. Scale the steps to the risk of the work.

## Discover

- Understand the requested user or system outcome.
- Inspect project instructions, relevant code, tests, configuration, and architecture.
- Identify conventions, versions, dependencies, and unknowns.
- Do not invent project facts. State assumptions or ask a focused question when needed.

## Plan

- Define acceptance criteria that can be verified.
- Identify scope, dependencies, data sensitivity, security impact, and operational impact.
- Separate required work from optional follow-ups.
- Present a short plan for multi-file or high-risk changes.

## Design

- Prefer existing patterns unless evidence supports a change.
- Consider responsibilities, boundaries, APIs, schemas, state ownership, failure modes, authorization, observability, and operational support.
- Compare alternatives and explain significant trade-offs.
- Record significant decisions using the project's ADR/TDR process when available.

## Implement

- Make focused, reviewable changes.
- Follow actual project conventions and supported versions.
- Validate untrusted input at system boundaries.
- Keep secrets out of source code and logs.
- Avoid unrelated refactors, speculative abstractions, and unnecessary dependencies.

## Verify

- Run the most relevant unit, integration, contract, and end-to-end tests available.
- Run formatting, linting, type checking, and security checks where configured.
- Verify migrations and configuration changes appropriately.
- Never report a check as successful unless it was run and passed.
- Explain any tests or checks that could not be run.

## Review

Inspect the full diff. Look for:
- Incorrect behaviour, missing edge cases, and compatibility breaks.
- Security, authorization, privacy, and tenant isolation issues.
- Unbounded retries, missing timeouts, concurrency hazards, and unsafe side effects.
- Missing tests or weak assertions.
- Unnecessary complexity, scope creep, or missing documentation.

Give findings with severity and file/line references where possible. Separate confirmed defects from suggestions.

## Prepare delivery

Consider configuration and secrets, migrations, feature flags, deployment order, smoke tests, rollback, monitoring, release notes, and operational ownership. Do not deploy or change production infrastructure without explicit authorization and required approvals.

## Report

Summarize changes, actual test results, unverified areas, and remaining risks or decisions. AI-generated code is not complete engineering work until it has been reviewed and verified.

## Compass references

- [Documentation index](https://github.com/austinnoronha/ai-engineering-compass/blob/main/docs/README.md)
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

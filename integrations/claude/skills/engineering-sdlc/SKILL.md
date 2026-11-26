---
name: engineering-sdlc
description: Apply the AI Engineering Compass workflow when planning, designing, implementing, testing, reviewing, preparing releases, or investigating operational changes in a software repository.
---

# Engineering SDLC workflow

Use this skill for feature work, bug fixes, refactoring, migrations, architecture changes, security improvements, and production-readiness tasks. Scale the process to the risk and size of the change; do not impose heavyweight ceremony on a tiny edit.

## 1. Understand and discover

- Read the task and identify the intended user or system outcome.
- Inspect the relevant repository structure, implementation, tests, configuration, and project instructions.
- Identify existing conventions and supported versions.
- List constraints, dependencies, data sensitivity, integration points, and unknowns.
- Ask only for missing information that materially blocks safe progress; otherwise state assumptions.

## 2. Define the change

- Write concise acceptance criteria with observable outcomes.
- Identify out-of-scope items.
- Consider compatibility, migration, feature-flag, and rollout implications.
- For non-trivial work, present a plan before editing.

## 3. Design proportionately

- Prefer extending established patterns over introducing new architecture without evidence.
- Consider responsibilities, module boundaries, APIs, data contracts, state ownership, concurrency, failure modes, security, privacy, observability, and operational support as relevant.
- Compare alternatives and explain meaningful trade-offs.
- Record significant decisions in the repository's ADR/TDR format where one exists.

Relevant canonical references:
- [Software design](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/software-design)
- [Backend engineering](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/backend-engineering)
- [Frontend engineering](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/frontend-engineering)
- [Databases and storage](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/databases-and-storage)

## 4. Implement

- Keep changes focused and reviewable.
- Follow the project's language, framework, architecture, and naming conventions.
- Validate untrusted input at boundaries and keep permissions explicit.
- Handle errors intentionally; do not swallow unexpected exceptions.
- Use bounded, safe retries and idempotency for retryable side effects where relevant.
- Avoid unrelated refactors, speculative abstractions, and unrequested dependencies.
- Never hardcode secrets or expose sensitive data.

## 5. Verify

Choose verification based on risk and affected boundaries:

- Unit tests for focused logic.
- Integration or contract tests for component boundaries.
- End-to-end tests for important user journeys.
- Formatting, linting, type checking, static analysis, dependency and security checks where configured.
- Manual verification for UI, migration, or operational behaviour where automation is insufficient.

Do not claim a test passed unless it was run and passed. Report failures and tests that could not be run.

Relevant canonical references:
- [Testing and quality](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/testing-and-quality)
- [Security and privacy](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/security-and-privacy)

## 6. Review

Inspect the complete diff. Check:

- Acceptance criteria and scope.
- Correctness, edge cases, and compatibility.
- Naming, cohesion, coupling, and unnecessary complexity.
- Authentication, authorization, tenant isolation, and sensitive data handling.
- Timeouts, retries, concurrency, cancellation, and partial failure where relevant.
- Tests, observability, documentation, and operational readiness.

Prioritize findings by severity and include file/line references. Separate confirmed defects from suggestions.

## 7. Prepare delivery

Before declaring work ready, identify relevant:

- Configuration and secret changes.
- Database migrations and deployment ordering.
- Feature flags and compatibility concerns.
- Smoke tests, monitoring, rollback, and operational ownership.
- Release notes and user-facing documentation.

Do not deploy, release, run destructive operations, or alter production infrastructure without explicit authorization and required approvals.

Relevant canonical references:
- [Cloud and DevOps](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/cloud-and-devops)
- [Reliability and observability](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/reliability-and-observability)
- [Engineering workflow](https://github.com/austinnoronha/ai-engineering-compass/tree/main/docs/engineering-workflow)

## 8. Report completion

Summarize what changed, why, the checks actually run and their outcomes, anything not verified, and remaining risks or decisions. Do not equate generated code with completed engineering work.

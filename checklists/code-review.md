# Code review checklist

Use the questions relevant to the change. This is a prompt for engineering discussion, not a scorecard.

## Correctness and scope

- [ ] Does the change meet the stated requirement?
- [ ] Are boundary conditions and failure paths handled?
- [ ] Is the scope focused and understandable?

## Design and maintainability

- [ ] Are responsibilities and dependencies clear?
- [ ] Is the abstraction proportionate to the problem?
- [ ] Are names and interfaces understandable?

## Security and privacy

- [ ] Are trust boundaries and permissions handled?
- [ ] Are secrets and sensitive data protected?
- [ ] Is untrusted input handled safely?

## Quality and operations

- [ ] Are tests appropriate and useful?
- [ ] Are logs and metrics sufficient without leaking sensitive data?
- [ ] Are configuration, migration, deployment, and rollback concerns addressed?
- [ ] Is relevant documentation updated?

## Evidence

Record tests and checks that were run, plus anything that could not be verified.

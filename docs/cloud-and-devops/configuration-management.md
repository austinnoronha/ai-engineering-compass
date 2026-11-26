# Configuration management

**Status:** Recommended  
**Last reviewed:** 2026-11-26

Configuration is part of a feature's operational contract. A service that works only because a developer has undocumented local settings is not ready to run in another environment.

## Use explicit, typed settings

- Centralize configuration parsing and validation.
- Define required and optional values.
- Validate types, formats, ranges, and allowed values at startup.
- Keep environment-specific resource identifiers outside source code.
- Fail fast when required configuration is missing or malformed.
- Avoid silent fallback to development values in production.

## Separate configuration from secrets

Non-secret configuration may come from environment variables or managed configuration systems. Store credentials, tokens, private keys, and connection secrets in an approved secret manager. Use workload identity or role-based access rather than long-lived credentials where supported.

Example placeholder file:

```dotenv
APP_ENV=local
LOG_LEVEL=INFO
DATABASE_URL=postgresql://user:password@localhost:5432/app
OBJECT_STORE_BUCKET=replace-me
```

This is illustrative only. Do not commit real credentials. In a real project, use clearly fake local values and document how developers obtain secrets.

## Treat infrastructure dependencies explicitly

For each external dependency, document the resource identity, region, access policy, connectivity, encryption, lifecycle, and required startup or readiness behaviour. Examples include databases, object storage, queues, and identity providers.

## Test configuration

- Unit test settings validation and precedence.
- Test adapters against appropriate local or test infrastructure.
- Run deployment smoke tests in each target environment.
- Verify that API, worker, scheduler, and migration processes receive the settings they require.

## Review checklist

- Are required and optional settings documented?
- Are secrets separated from ordinary config?
- Are production-safe defaults used?
- Does the application fail clearly on invalid config?
- Are all runtime processes covered?
- Can an operator tell which resource and environment the process is using without exposing secrets?

## References

- [The Twelve-Factor App: Config](https://12factor.net/config)
- [AWS Secrets Manager](https://docs.aws.amazon.com/secretsmanager/latest/userguide/intro.html)

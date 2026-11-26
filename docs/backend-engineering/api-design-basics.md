# API design basics

**Status:** Recommended  
**Last reviewed:** 2026-11-26

An API is a contract between a provider and its consumers. Design it around consumer tasks and domain concepts, not around the internal shape of database tables or ORM objects.

## Practical guidance

- Use consistent resource names and HTTP semantics.
- Define request and response schemas explicitly.
- Validate input at the boundary and return actionable validation errors.
- Version deliberately when compatibility cannot be maintained.
- Document authentication, authorization, pagination, filtering, limits, and error behaviour.
- Avoid exposing internal stack traces, database models, or provider SDK objects.
- Treat idempotency as a first-class concern for operations that clients may retry.

## Example response

```json
{
  "data": {
    "id": "task_123",
    "status": "queued"
  },
  "request_id": "req_abc123"
}
```

This is illustrative, not a required envelope. Consistency matters more than adopting this exact shape.

## Compatibility

Before changing an API, consider existing clients, mobile or browser caches, integrations, generated SDKs, and asynchronous consumers. Prefer additive changes when possible. Make breaking changes explicit and provide a migration path.

## Review checklist

- Is the contract understandable without reading implementation code?
- Are invalid input and authorization failures defined?
- Are pagination and resource limits clear?
- Can clients safely retry the operation?
- Are compatibility and versioning addressed?

## References

- [Microsoft REST API Guidelines](https://github.com/microsoft/api-guidelines)
- [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

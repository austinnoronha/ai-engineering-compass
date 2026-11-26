# Error handling

**Status:** Recommended  
**Last reviewed:** 2026-11-26

Errors are part of the interface of a system. Good error handling helps a caller decide what to do next while preserving enough diagnostic detail for engineers to investigate.

## Separate caller information from diagnostics

A caller usually needs a stable error category, a safe message, and a request or correlation identifier. Engineers may need stack traces, provider responses, and contextual metadata. Keep the latter in protected logs or traces, not in public responses.

Example public response:

```json
{
  "error": {
    "code": "RESOURCE_NOT_FOUND",
    "message": "The requested resource was not found.",
    "request_id": "req_abc123"
  }
}
```

## Handle errors at the right boundary

- Validate untrusted input at system boundaries.
- Translate infrastructure and provider exceptions into stable application errors.
- Preserve causal context internally when translating exceptions.
- Do not catch and silently ignore unexpected exceptions.
- Avoid returning raw exception text or stack traces to clients.
- Retry only failures that are plausibly transient and safe to retry.

## Retry carefully

Retries can amplify load and duplicate side effects. Use bounded attempts, backoff with jitter, deadlines, and idempotency where needed. Make retry ownership explicit so multiple layers do not each retry independently.

## Review checklist

- Is the error code stable and documented?
- Does the caller know whether a retry may help?
- Are internal details kept out of the public response?
- Are logs correlated to the request or operation?
- Are retries bounded and safe for side effects?

## References

- [Google Cloud: Error handling](https://cloud.google.com/apis/design/errors)
- [AWS: Timeouts, retries, and backoff with jitter](https://aws.amazon.com/builders-library/timeouts-retries-and-backoff-with-jitter/)

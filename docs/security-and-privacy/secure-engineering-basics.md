# Secure engineering basics

**Status:** Recommended  
**Last reviewed:** 2026-11-26

Start by identifying what the system protects, who or what can access it, and where data crosses a trust boundary. Security controls should follow the threats and impact, not be copied mechanically from another system.

## Practical baseline

- Apply least privilege to users, services, jobs, and infrastructure roles.
- Validate and normalize untrusted input at boundaries.
- Store secrets in an approved secret manager; do not commit them to source control.
- Encrypt sensitive data in transit and at rest according to the threat model and applicable requirements.
- Log security-relevant events without leaking credentials or sensitive payloads.
- Keep dependencies and runtime images patched.
- Review authorization on the server, even when the UI hides unavailable actions.
- Define retention and deletion behaviour for personal or sensitive data.

## Think beyond input validation

Consider authentication, authorization, tenant isolation, SSRF, injection, unsafe file handling, insecure deserialization, replay, resource exhaustion, and supply-chain risk where relevant.

## AI-assisted systems

Treat model output and retrieved content as untrusted input. Do not let prompt text override platform authorization. Keep tool permissions narrow, validate tool arguments, and require human approval for high-impact actions where appropriate.

## Review checklist

- What are the protected assets and trust boundaries?
- Who can perform each sensitive action?
- Where are secrets stored and how are they rotated?
- Can user-controlled input reach privileged operations?
- What data is logged, retained, exported, or deleted?
- What happens when an external dependency is compromised or unavailable?

## References

- [OWASP Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
- [NIST Secure Software Development Framework](https://csrc.nist.gov/Projects/ssdf)

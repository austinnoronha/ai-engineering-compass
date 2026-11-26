# Observability foundations

**Status:** Recommended  
**Last reviewed:** 2026-11-26

Monitoring tells you whether known conditions are occurring. Observability helps you investigate system behaviour you did not anticipate.

## Three useful signals

- **Logs** record discrete events with contextual fields.
- **Metrics** describe aggregated measurements over time.
- **Traces** show how a request or operation moves across components.

They complement one another. A metric may show a latency spike; traces help locate the slow dependency; logs provide event detail around a particular request.

## Add useful context

Use structured logs with stable fields such as timestamp, service, environment, severity, operation, and correlation identifier. Avoid logging secrets, credentials, session tokens, or sensitive user content.

Measure outcomes and saturation as well as component activity. For asynchronous systems, queue age and processing delay can be more useful than queue depth alone.

## Alert on actionable conditions

Alerts should have an owner and a response path. Prefer signals tied to user impact, error budgets, capacity exhaustion, or failure to meet an operational objective. Avoid paging on noisy metrics with no clear action.

## Review checklist

- Can an operation be followed across service boundaries?
- Are logs structured and appropriately redacted?
- Do metrics represent user or workload outcomes?
- Are traces sampled and retained appropriately?
- Does each alert describe an action and an owner?

## References

- [OpenTelemetry documentation](https://opentelemetry.io/docs/)
- [Google SRE Book](https://sre.google/sre-book/table-of-contents/)

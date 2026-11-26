# Testing strategy

**Status:** Recommended  
**Last reviewed:** 2026-11-26

A useful test suite gives fast feedback on local behaviour and enough integration coverage to catch failures at important boundaries.

## Choose tests by risk

- **Unit tests** check focused logic with external dependencies replaced or controlled.
- **Integration tests** verify that components work together across real boundaries such as databases, queues, or filesystem adapters.
- **Contract tests** check assumptions between independently developed consumers and providers.
- **End-to-end tests** verify important user journeys through deployed components.

Use the fastest test that gives meaningful confidence for a particular risk. Not every behaviour needs every test type.

## Good test properties

Tests should be deterministic, isolated where practical, readable, and focused on observable behaviour. A test name should explain the scenario and expected result.

Avoid tests that merely mirror implementation details. They tend to fail during harmless refactoring and may not catch user-visible regressions.

## Test failure paths

Include validation errors, permission failures, timeouts, duplicate requests, partial failures, and recovery behaviour where these matter to the feature.

## Review checklist

- What risk does this test reduce?
- Does it verify behaviour rather than private implementation details?
- Is it deterministic and repeatable?
- Are important failure paths covered?
- Does the test give a useful failure message?

## References

- [Google Testing Blog](https://testing.googleblog.com/)
- [Martin Fowler: Test Pyramid](https://martinfowler.com/articles/practical-test-pyramid.html)

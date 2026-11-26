# Frontend state management

**Status:** Recommended  
**Last reviewed:** 2026-11-26

State management is primarily an ownership and lifecycle problem. A library can help, but it cannot decide which component or service should own a piece of state.

## Start by classifying state

- **Local UI state:** open panels, temporary input, selected tabs.
- **Shared client state:** information needed by multiple parts of the interface.
- **Server state:** data owned by a backend, with loading, freshness, caching, and error concerns.
- **URL state:** navigable state such as filters, search terms, and selected records.

Keep state as close as practical to the parts that need it. Promote it when ownership genuinely becomes shared.

## Prefer one source of truth

Avoid storing values that can be derived from other state unless there is a measured reason. Duplicated state can drift and create difficult-to-reproduce bugs.

## Model asynchronous states explicitly

A request may be idle, loading, successful, empty, or failed. Represent the states that matter to the user rather than relying on loosely related booleans that allow impossible combinations.

## Review checklist

- Who owns this state?
- Who can update it?
- Is it derived or independently stored?
- What happens when requests overlap or complete out of order?
- Does the UI handle loading, empty, error, and stale data?
- Should some of the state be encoded in the URL?

## References

- [React: Managing State](https://react.dev/learn/managing-state)
- [Angular: Signals](https://angular.dev/guide/signals)

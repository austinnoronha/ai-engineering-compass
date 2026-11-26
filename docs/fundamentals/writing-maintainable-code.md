# Writing maintainable code

**Status:** Recommended  
**Last reviewed:** 2026-11-26  
**Scope:** General software development; examples are illustrative.

Readable code reduces the effort needed to understand behaviour and makes change safer. Maintainability is not achieved by making every function tiny or by following a rigid style rule. It comes from making intent, boundaries, and behaviour easy to see.

## Start with intent

Names should explain the role of a value or operation in the domain. Prefer names that describe why something exists over names that merely repeat its type.

```python
# Less clear
def process(items):
    return [x for x in items if x["active"]]

# Clearer
def get_active_accounts(accounts):
    return [account for account in accounts if account["active"]]
```

The example assumes each item is a mapping with an `active` field. In production code, define and validate that shape explicitly.

## Keep responsibilities cohesive

A function should have a clear purpose. Split code when doing so gives a useful name to a meaningful step, isolates a change boundary, or makes behaviour easier to test. Avoid splitting every expression into a new function without a reason.

## Make hidden assumptions visible

- Validate input at trust boundaries.
- Make side effects clear from names and interfaces.
- Prefer explicit parameters over distant mutable state.
- Keep configuration outside business logic.
- Make error paths understandable and intentional.

## Avoid cleverness that hides behaviour

Compact expressions can be useful, but not when they force readers to mentally decode several operations at once. Optimise for the next engineer who must debug or change the code.

## Verification

Review the code with these questions:

- Can a new team member understand the purpose from names and surrounding context?
- Are the important assumptions explicit?
- Are side effects and failure cases visible?
- Can the main behaviour be tested without unnecessary infrastructure?
- Did abstraction remove duplication or just move complexity elsewhere?

## Trade-offs

There is no single ideal function length or abstraction level. A short function can still be confusing; a longer function can be clear when its steps form one cohesive operation. Use complexity, change frequency, and testability to guide refactoring.

## References

- [Google Engineering Practices: readability](https://google.github.io/eng-practices/)
- [The Pragmatic Programmer](https://pragprog.com/titles/tpp20/the-pragmatic-programmer-20th-anniversary-edition/)

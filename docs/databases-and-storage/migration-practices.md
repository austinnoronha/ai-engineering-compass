# Database migration practices

**Status:** Recommended  
**Last reviewed:** 2026-11-26

Database migrations change persistent state and can affect running application versions. Plan them for compatibility, data volume, locking, and recovery, not only for whether the SQL executes.

## Expand and contract

For changes that must coexist with old and new application versions:

1. Add the new schema in a backward-compatible way.
2. Deploy application code that can work with both old and new forms.
3. Backfill or transform data in controlled batches when needed.
4. Switch reads and writes to the new representation.
5. Remove obsolete schema only after old code paths are gone.

Not every change needs this sequence. Small, low-risk changes in a controlled maintenance window may be simpler.

## Operational concerns

- Estimate data volume and migration duration.
- Understand lock behaviour for the database engine and version.
- Make long-running backfills resumable and observable.
- Take and verify backups according to the recovery plan.
- Coordinate application deployment order.
- Avoid assuming that a down migration can safely reverse data loss.

## Review checklist

- Is the migration compatible with currently running application versions?
- Does it lock or rewrite a large table?
- Can a partial backfill resume safely?
- Is there a tested recovery plan?
- Are deployment and rollback steps documented?

## References

- [PostgreSQL: ALTER TABLE](https://www.postgresql.org/docs/current/sql-altertable.html)
- [Martin Fowler: Parallel Change](https://martinfowler.com/bliki/ParallelChange.html)
